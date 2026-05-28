# CosFan Spec Kit - DATA_MODEL

- 문서 버전: v0.1 Final
- 목적: App MVP 설계 전 데이터 개념과 관계를 정리한다.
- 기준: CosFan PRD v0.4, Spec Kit v0.1 Final Candidate
- 주의: 실제 DB 설계, 스토리지 구현, API 구현을 확정하는 문서가 아니다.
- 원칙: 개인정보/민감정보는 최소 수집한다. 법무 검토가 필요한 정보는 원문 보관을 지양하고 상태값 중심으로 저장한다.

---

## 1. Data Principles

| 원칙 | 기준 |
|---|---|
| 최소 수집 | App MVP 운영에 필요한 정보만 수집한다. |
| 상태값 중심 | 신분, 계좌, 권리 증빙 원본 저장은 법무 검토 전까지 지양하고 확인 상태값 중심으로 관리한다. |
| 결제 원본 비저장 | 카드번호, 계좌 원본 등 결제 민감정보는 저장하지 않는다. 결제사는 provider_reference_id 중심으로 참조한다. |
| 미디어 참조값 사용 | MediaAsset의 storage_ref, thumbnail_ref는 실제 공개 URL이 아니라 내부 저장소 참조값이다. 접근 가능한 URL은 권한 확인 후 임시 생성한다. |
| 콘텐츠 등급 분리 | MediaAsset과 콘텐츠에는 content_rating을 연결해 Level 0~3 노출 기준을 통제한다. |
| 포토카드 비거래 원칙 | 포토카드는 거래 가능한 자산이 아니라 팬덤 기록이다. |
| 운영자 접근 통제 | 민감 정보, 신고/제재, 권리 요청, 정산 정보 접근은 OperatorRole과 DataAccessLog로 통제한다. |
| 18+ 처리 | MVP에서는 18+ 콘텐츠를 제공하지 않는다. Future 18+ Review는 메인 앱과 분리된 별도 검토 트랙으로만 관리한다. |

---

## 2. Entity Definitions

| Entity | Purpose | Key Fields | Privacy / Sensitivity | Retention Notes |
|---|---|---|---|---|
| User | 팬/크리에이터/운영자 계정의 기본 정보를 관리한다. | user_id, email, display_name, role, interest_tags, created_at, status | email은 개인정보 | 계정 삭제/비활성화 정책 필요. 이메일은 인증/고객지원 목적 최소 보관 |
| FanProfile | 팬의 팔로우, 구독, 포토카드 보유 기록, 알림 설정을 관리한다. | user_id, followed_creator_ids, subscription_ids, photocard_holding_ids, notification_preferences | 이용행태 정보 | 분석 시 집계 단위 사용. 외부 공유 금지 |
| CreatorProfile | 크리에이터 공개 프로필과 운영 상태를 관리한다. | creator_id, user_id, display_name, bio, category_tags, sns_links, verification_status, content_rating_allowed, membership_plan_ids, profile_asset_id, status | sns_links는 계정 연결 정보 | 공개/비공개 필드 분리 필요 |
| CreatorVerification | 크리에이터 최소 확인 상태를 관리한다. | creator_id, sns_ownership_status, contract_eligibility_status, settlement_account_check_status, rights_confirmation_status, policy_agreement_status, verified_at, reviewed_by | 계약/정산 관련 민감 운영 정보 | 신분증/계좌 원본 저장 지양. 상태값 중심 저장. 법무 검토 필요 |
| OperatorRole | 운영자의 접근 권한을 관리하는 개념 모델이다. | role_id, role_name, permissions, created_at, status | 내부 권한 정보 | 실제 권한 시스템 구현은 App MVP 설계 단계에서 확정한다. 향후 다중 역할이 필요하면 OperatorUserRole 개념을 검토한다. |
| MembershipPlan | 크리에이터별 월 멤버십 가격과 혜택을 관리한다. | plan_id, creator_id, price, benefits, minimum_delivery_rules, billing_cycle, status | 낮음 | 혜택 변경 이력 필요 |
| Subscription | 팬의 월 구독 상태를 관리한다. | subscription_id, user_id, creator_id, plan_id, status, started_at, next_billing_at, canceled_at | 결제/구독 정보 | 결제 원본 정보 저장 지양. 결제사 참조값 중심 |
| PaymentTransaction | 월 구독 결제 성공/실패/환불 연동의 기준이 되는 결제 이벤트를 관리한다. | transaction_id, subscription_id, user_id, creator_id, amount, currency, payment_provider, provider_reference_id, provider_status, status, paid_at, failed_at, refunded_at, created_at | 결제 관련 정보 | 카드번호 등 결제 민감정보 저장 금지. provider_reference_id 중심 관리 |
| SettlementRecord | 크리에이터별 월 정산 내역을 관리한다. | settlement_id, creator_id, period, gross_amount, platform_fee, refund_amount, adjustment_amount, payout_amount, status, created_at, reviewed_at, paid_at, reviewed_by | 정산/수익 정보 | 초기 수동 정산이어도 개념 모델에 포함. 환불/분쟁/혜택 미제공 조정 이력 필요 |
| MediaAsset | 룩북, 메시지 첨부, 포토카드 이미지, 프로필 이미지, 행사 이미지 등 파일 자산의 등급, 공개 범위, 권리 상태, 썸네일, 숨김 처리를 관리한다. | asset_id, owner_type, owner_id, file_type, storage_ref, thumbnail_ref, content_rating, visibility, rights_status, created_at, status | 이미지/파일에 인물 정보, 권리 정보, 민감 콘텐츠가 포함될 수 있음 | storage_ref, thumbnail_ref는 실제 공개 URL이 아니라 내부 저장소 참조값이다. 접근 가능한 URL은 권한 확인 후 임시 생성한다. 실제 스토리지 구현 방식은 확정하지 않는다. Level 2/3 공개 노출 금지 |
| Lookbook | 구독자 전용 룩북 콘텐츠를 관리한다. | lookbook_id, creator_id, title, media_asset_ids, content_rating, visibility, published_at, status | 인물/저작권 관련 정보 포함 가능 | 포함된 MediaAsset 중 가장 높은 위험 등급을 기준으로 content_rating을 산정한다. 권리 확인 및 콘텐츠 등급 이력 필요 |
| CreatorMessage | 크리에이터 1:N 메시지를 관리한다. | message_id, creator_id, audience_scope, body, attachment_asset_ids, published_at, status | 사용자 생성 텍스트 | 연결된 MediaAsset 또는 텍스트 검토 결과를 기준으로 ContentRatingReview를 가질 수 있다. 외부 링크/금지 문구 검수 필요 |
| FanReply | 팬의 짧은 답장을 관리한다. | reply_id, message_id, user_id, body, created_at, status | 사용자 생성 텍스트 | 신고/차단/삭제 처리 가능해야 함 |
| Reaction | 메시지/룩북/포토카드 보유 기록에 대한 팬 리액션을 기록한다. | reaction_id, target_type, target_id, user_id, reaction_type, created_at | 이용행태 정보 | 공개 순위형 랭킹에 직접 사용하지 않음 |
| PhotocardTemplate | 크리에이터가 발급하는 포토카드 원본/시리즈 정보를 관리한다. | template_id, creator_id, series_name, card_number, issue_month, image_asset_id, default_share_permission, status, created_at | 이미지 자산과 크리에이터 콘텐츠 정보 포함 | 연결된 MediaAsset 또는 텍스트 검토 결과를 기준으로 ContentRatingReview를 가질 수 있다. 거래/희소성/가격 정보 저장 금지 |
| PhotocardHolding | 특정 팬에게 발급된 포토카드 보유 기록을 관리한다. | holding_id, template_id, user_id, issued_at, acquisition_source, acquisition_ref_type, acquisition_ref_id, holder_alias, watermark_state, share_permission, transferability, market_value, status | user_id, holder_alias는 식별 가능 정보 | transferability는 non-transferable, market_value는 none 고정. acquisition_ref_type과 acquisition_ref_id는 subscription, event_notice, manual_grant 등 획득 출처를 추적하기 위한 선택 필드다. |
| EventNotice | 촬영회·행사 공지를 관리한다. | event_id, creator_id, title, organizer, date_time, location, participation_terms, external_link_ids, image_asset_ids, link_review_status, status | 장소/일정 정보 | MVP에서는 primary external_link 1개만 허용할 수 있다. 개념 모델에서는 EventNotice 1:N ExternalLinkReview를 허용한다. 모든 외부 링크는 공개 전 ExternalLinkReview를 거쳐야 한다. 공개 행사만 허용하며 사적 만남 유도 금지 |
| Report | 신고 접수와 처리 상태를 관리한다. | report_id, reporter_user_id, target_type, target_id, reason, status, created_at, reviewed_at, action_taken | 신고자/대상자 정보 포함 | 접근 권한 제한. 처리 이력 보존 필요 |
| Block | 사용자 차단 관계를 관리한다. | block_id, blocker_user_id, blocked_target_type, blocked_target_id, created_at | 사용자 관계 정보 | 차단 해제 가능해야 함 |
| RightsRequest | 권리자 삭제 요청을 관리한다. | request_id, claimant_type, target_content_type, target_content_id, claim_reason, status, created_at, resolved_at | 권리자 정보 및 주장 내용 | 증빙 자료 원문 보관은 법무 검토 필요 |
| BenefitDeliveryLog | 월 최소 혜택 제공 여부를 관리한다. | log_id, creator_id, plan_id, month, promised_benefits, delivered_benefits, status | 낮음 | 환불/정산과 연결될 수 있으므로 변경 이력 필요 |
| RefundCase | 환불/보상 검토 케이스를 관리한다. | refund_case_id, subscription_id, transaction_id, reason, status, amount, created_at, resolved_at | 결제/분쟁 정보 | 결제 원본 저장 지양. PaymentTransaction과 결제사 참조값 사용 |
| ExternalLinkReview | 행사 공지 외부 링크 검토 상태를 관리한다. | review_id, event_id, url, link_type, review_status, reviewed_by, reviewed_at | URL에 개인정보 포함 가능성 있음 | 모든 외부 링크는 공개 전 검수를 거쳐야 한다. 우회 결제/만남 유도 링크 검출 필요 |
| ContentRatingReview | 콘텐츠 Level 0~3 등급 분류 이력을 관리한다. | review_id, target_content_type, target_content_id, rating_level, reason, reviewed_by, reviewed_at, action_taken | 콘텐츠 민감도 정보 | Level 2/3 판단 이력 보존. 접근 권한 제한 |
| DataAccessLog | 민감 정보와 신고/제재 로그 접근 이력을 관리한다. | access_log_id, actor_user_id, target_entity, target_id, access_reason, action_type, result, accessed_at | 내부 운영 민감 정보 | action_type은 view, update, export, approve, reject, hide, delete 등을 표현한다. result는 success, denied, failed 등을 표현한다. 운영자 접근 감사 목적. 보관 기간 법무 검토 필요 |

---

## 3. OperatorRole Examples

| role_name | Purpose | Example Permissions |
|---|---|---|
| owner | 전체 운영/정책/정산 관리 | all_access, policy_update, settlement_review |
| admin | 운영자 관리와 주요 검토 승인 | creator_review, report_review, rights_review, access_log_view |
| ops_reviewer | 신고, 콘텐츠 등급, 외부 링크 검토 | report_review, content_rating_review, external_link_review |
| finance_reviewer | 결제, 환불, 정산 검토 | payment_review, refund_review, settlement_review |
| support_reviewer | 고객지원, 신고 접수 상태 확인 | support_view, report_limited_view, subscription_limited_view |

> 실제 권한 시스템 구현은 App MVP 설계 단계에서 확정한다.  
> 향후 한 운영자가 여러 역할을 동시에 가져야 하는 경우 `OperatorUserRole` 개념을 별도로 검토할 수 있다.

---

## 4. MediaAsset Rules

| 항목 | 기준 |
|---|---|
| storage_ref | 실제 공개 URL이 아니라 내부 저장소 참조값이다. 접근 가능한 URL은 권한 확인 후 임시 생성한다. |
| thumbnail_ref | 실제 공개 URL이 아니라 내부 썸네일 참조값이다. 접근 가능한 URL은 권한 확인 후 임시 생성한다. |
| content_rating | Level 0, Level 1, Level 2, Level 3 중 하나로 관리한다. |
| visibility | public, member_only, hidden, under_review 등으로 관리한다. |
| rights_status | confirmed, pending, disputed, takedown_requested 등으로 관리한다. |
| 공개 노출 | Level 0만 공개 영역에 노출 가능하다. |
| 구독자 영역 | Level 1까지만 허용한다. |
| 검토 필요 | Level 2는 운영자 검토 후 제한 또는 반려한다. |
| 금지 | Level 3는 즉시 숨김 또는 삭제 검토 대상이다. |

---

## 5. MediaAsset Linking Rule

| 항목 | 기준 |
|---|---|
| owner_type / owner_id | 자산의 주 소유 대상을 표현하는 다형 참조 개념이다. |
| 주요 사용 관계 | Relationship Draft의 Lookbook 1:N MediaAsset, CreatorMessage 1:N MediaAsset 등은 주요 사용 관계를 설명하기 위한 개념 관계다. |
| 구현 방식 | 실제 구현 시에는 별도 join table 또는 명시적 foreign key 중 하나를 선택한다. |
| 공개 URL | storage_ref와 thumbnail_ref는 공개 URL이 아니다. 접근 가능한 URL은 권한 확인 후 임시 생성한다. |
| 권리/등급 | MediaAsset은 content_rating, visibility, rights_status를 통해 노출 가능 여부를 통제한다. |

---

## 6. Content Rating Calculation Rule

| 항목 | 기준 |
|---|---|
| MediaAsset.content_rating | 개별 이미지/파일 단위 등급이다. |
| Lookbook.content_rating | 포함된 MediaAsset 중 가장 높은 위험 등급을 기준으로 산정한다. |
| CreatorMessage | 연결된 MediaAsset 또는 텍스트 검토 결과를 기준으로 ContentRatingReview를 가질 수 있다. |
| EventNotice | 연결된 MediaAsset, 외부 링크, 텍스트 검토 결과를 기준으로 ContentRatingReview를 가질 수 있다. |
| PhotocardTemplate | 연결된 MediaAsset 또는 텍스트 검토 결과를 기준으로 ContentRatingReview를 가질 수 있다. |
| 공개 영역 | Level 0만 노출한다. |
| 구독자 영역 | Level 1까지만 노출한다. |
| Level 2 | 운영자 검토 후 제한 또는 반려한다. |
| Level 3 | 즉시 숨김 또는 삭제 검토 대상이다. |

---

## 7. Photocard Rules

| 항목 | 기준 |
|---|---|
| 구조 | PhotocardTemplate + PhotocardHolding + MediaAsset |
| PhotocardTemplate | 크리에이터가 발급하는 카드 원본/시리즈 |
| PhotocardHolding | 특정 팬에게 발급된 보유 기록 |
| MediaAsset | 카드 이미지 자산 |
| acquisition_ref_type | subscription, event_notice, manual_grant 등 획득 출처 유형을 선택적으로 기록한다. |
| acquisition_ref_id | 획득 출처에 해당하는 참조 ID를 선택적으로 기록한다. |
| transferability | non-transferable 고정 |
| market_value | none 고정 |
| 거래 기능 | 판매, 교환, 양도, 가격 표시 금지 |
| 표현 원칙 | 포토카드는 거래 가능한 자산이 아니라 팬덤 기록이다. |

---

## 8. Event External Link Rules

| 항목 | 기준 |
|---|---|
| EventNotice.external_link_ids | EventNotice와 연결된 외부 링크 검토 기록 ID 목록이다. |
| MVP 허용 범위 | MVP에서는 primary external_link 1개만 허용할 수 있다. |
| 개념 모델 | 개념 모델에서는 EventNotice 1:N ExternalLinkReview를 허용한다. |
| 공개 전 검수 | 모든 외부 링크는 공개 전 ExternalLinkReview를 거쳐야 한다. |
| 허용 링크 | 공개 행사 안내, 신청 폼, 공식 SNS, 크리에이터 공식 페이지 등 |
| 금지 링크 | 우회 결제, 개인 간 비공개 만남, 대가성 만남, 1:1 사적 약속, 성적 서비스 암시 링크 |

---

## 9. Payment / Settlement Rules

| 항목 | 기준 |
|---|---|
| PaymentTransaction | 결제 성공/실패/환불 연동의 기준 이벤트다. |
| provider_reference_id | 결제사 참조 ID이며 결제 원본 정보 대신 사용한다. |
| provider_status | 결제사에서 전달한 상태를 내부 상태와 구분해 기록한다. |
| status | 내부 운영 상태로 paid, failed, refunded, partially_refunded 등을 사용한다. |
| created_at | 결제 이벤트 생성 시각을 기록한다. |
| refunded_at | 환불 완료 시각이 있을 경우 기록한다. |
| SettlementRecord | 크리에이터별 월 정산 내역이다. |
| created_at | 정산 기록 생성 시각을 기록한다. |
| reviewed_at | 정산 검토 완료 시각을 기록한다. |
| paid_at | 정산 지급 완료 시각을 기록한다. |
| reviewed_by | 정산 검토 운영자 user_id를 기록한다. |
| 결제 원본 | 카드번호, 계좌 원본 등은 저장하지 않는다. |

---

## 10. Relationship Draft

### User / Profile

- User 1:1 FanProfile
- User 1:0..1 CreatorProfile
- User 1:N Subscription
- User 1:N FanReply
- User 1:N Reaction
- User 1:N Report
- User 1:N Block
- User 1:N PhotocardHolding
- User 1:N DataAccessLog as actor_user_id

### Creator

- CreatorProfile 1:1 CreatorVerification
- CreatorProfile 1:N MembershipPlan
- CreatorProfile 1:N Lookbook
- CreatorProfile 1:N CreatorMessage
- CreatorProfile 1:N PhotocardTemplate
- CreatorProfile 1:N EventNotice
- CreatorProfile 1:N BenefitDeliveryLog
- CreatorProfile 1:N SettlementRecord
- CreatorProfile 1:1 MediaAsset as profile image

### Membership / Subscription / Payment

- MembershipPlan 1:N Subscription
- MembershipPlan 1:N BenefitDeliveryLog
- Subscription N:1 User
- Subscription N:1 CreatorProfile
- Subscription N:1 MembershipPlan
- Subscription 1:N PaymentTransaction
- Subscription 1:N RefundCase
- PaymentTransaction N:1 Subscription
- RefundCase N:1 PaymentTransaction 또는 RefundCase N:1 Subscription
- SettlementRecord N:1 CreatorProfile

### Media / Content

- Lookbook 1:N MediaAsset
- CreatorMessage 1:N MediaAsset as attachments
- EventNotice 1:N MediaAsset as image assets
- CreatorProfile 1:1 MediaAsset as profile image
- PhotocardTemplate 1:1 MediaAsset as card image
- Lookbook 1:N Reaction
- CreatorMessage 1:N FanReply
- CreatorMessage 1:N Reaction

### Photocard

- PhotocardTemplate 1:N PhotocardHolding
- PhotocardTemplate 1:1 MediaAsset as card image
- PhotocardHolding N:1 User
- PhotocardHolding N:1 PhotocardTemplate
- FanProfile 1:N PhotocardHolding
- PhotocardHolding 1:N Reaction

### Event / Link

- EventNotice 1:N ExternalLinkReview
- EventNotice 1:N ContentRatingReview

### Policy / Moderation

- Report N:1 User
- Report N:1 Target Content or Target Account
- RightsRequest N:1 Target Content
- ContentRatingReview N:1 MediaAsset or Target Content
- ContentRatingReview N:1 Lookbook
- ContentRatingReview N:1 CreatorMessage
- ContentRatingReview N:1 EventNotice
- ContentRatingReview N:1 PhotocardTemplate
- DataAccessLog N:1 User as actor_user_id
- DataAccessLog N:1 Target Entity

### Operator

- OperatorRole 1:N User where User.role is operator-type
- User 1:N DataAccessLog as actor_user_id

> 향후 한 운영자에게 복수 역할이 필요한 경우 `OperatorUserRole` 개념을 검토할 수 있다.