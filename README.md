# 기능 요구사항

## 1단계
### 쿠폰 생성, 조회 기능 구현
### 쿠폰
- 이름
  - [x] 이름은 반드시 존재해야 한다.
  - [x] 이름의 길이는 최대 30자 이하여야 한다.
- 할인 금액
  - [x] 할인 금액 제약
    -[x] 할인 금액은 1,000원 이상이어야 한다.
    -[x] 할인 금액은 10,000원 이하여야 한다.
    -[x] 할인 금액은 500원 단위로 설정할 수 있다.
- 할인율 제약
  - [x] 할인율은 할인금액 / 최소 주문 금액 식을 사용하여 계산하며, 소수점은 버림 한다.
  - [x] 할인율은 3% 이상이어야 한다.
  - [x] 할인율은 20% 이하여야 한다.
- 최소 주문 금액
  - [x] 최소 주문 금액은 5,000원 이상이어야 한다.
  - [x] 최소 주문 금액은 100,000원 이하여야 한다.
- 카테고리
  - [x] 서비스의 카테고리는 다음과 같이 네 종류가 있고, 이 중 하나의 카테고리만 선택할 수 있다.
    - 패션, 가전, 가구, 식품
- 발급 기간
  - [x] 시작일은 종료일보다 이전이어야 한다. 시작일과 종료일이 같다면, 해당 일에만 발급할 수 있는 쿠폰이 된다.
  - [x] 시작일 00:00:00.000000 부터 발급할 수 있다.
  - [x] 종료일 23:59:59.999999 까지 발급할 수 있다.

### 회원 쿠폰
- 회원에게 발급된 쿠폰 한 장을 관리한다. 다음 정보를 포함한다.
  - [x] 회원 쿠폰 PK
  - [x] 쿠폰 PK
  - [x] 회원 PK
  - [x] 사용 여부
  - [x] 발급 일시
  - [x] 만료 일시
    - [x] 회원에게 발급된 쿠폰은 발급일 포함 7일 동안 사용 가능하다. 만료 일의 23:59:59.999999 까지 사용할 수 있다.

### 복제 지연으로 인한 이슈 확인
- [x] 쿠폰을 생성한 후 즉시 조회했을 때 복제 지연으로 인해 데이터 조회에 실패하는 이슈를 확인한다.

### 복제 지연으로 인한 이슈 해결
- [x] 쿠폰을 생성했을 때, 의도한 대로 쿠폰이 생성됐는지 검증하도록 수정한다.