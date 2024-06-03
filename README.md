# 1. 주제

## 올룸골룸  : 부동산 중개 서비스

# 2. 팀 소개

## 올룸골룸
* 팀장 : 이경섭
* 팀원 : 서용욱, 김세호, 김동환

# 3. 개발 사항

1. 데이터 크롤링을 배우기 전이므로 데이터는 default 데이터를 무작위로 저장한다. (시퀀스 데이터 포함.)
2. JDBC 결과를 콘솔화면에 구현하는 것을 중점으로 한다. : 예전 PC통신 느낌이 나도록 만들어 봤습니다.
3. 프론트엔드를 배우기 전에 Sub_Side_Language인 thymeleaf로 간단한 웹페이지를 구현해본다.

# 4. 프로젝트 진행

https://docs.google.com/spreadsheets/d/1PHxGOc3YHsZqQTuzGfzHkA2f34ExoHbKAJ8qmyVLs-0/edit?usp=sharing

# 5. 개발환경

 <img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white">
      <img src="https://img.shields.io/badge/Oracle-F80000?style=for-the-badge&logo=Oracle&logoColor=white">
      <img src="https://img.shields.io/badge/Thymeleaf-%23005C0F.svg?style=for-the-badge&logo=Thymeleaf&logoColor=white">
      <img src="https://img.shields.io/badge/HTML-239120?style=for-the-badge&logo=html5&logoColor=white">
  <img src="https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white">

# 6. 구현 결과

## Console 구현
    
https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/ce484707-cde6-4550-b1f1-d0f59350cb09

## thymeleaf 구현

https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/cdb5e2c4-6503-446f-a0b7-5641ce9ddb18

# 7. 역할 분담

- **요구사항 영역별 정리**
    - 검색기능(지역검색, 거래방식, 평 수, 층 수), 검색 목록 페이지, 사용자 방페이지(찜기능: Update))까지 구현 : 김세호
    - 방 등록 페이지(테이블 생성, 데이터입력) 방과 관련된 역할 서포트 : 이경섭
    - 로그인과 회원가입 및 회원테이블 관련 기능 구현 : 김동환
    - 마이페이지 기능(찜목록, 방 관리목록, 회원정보 수정 및 탈퇴, 로그아웃) 구현 : 서용욱
    - 관리자 페이지 구현
- **ERD 및 테이블/시퀀스 구성**
    - 테이블 제작 및 상세 기능 설계 : 이경섭, 서용욱, 김동환, 김세호
    - 샘플 데이터 입력
        - 1. 회원(MEMBER) 테이블 데이터 : 김동환
        - 2. 방 등록(ROOMINFO) 테이블 데이터 : 김세호
        - 3. 마이페이지(MY_PAGE) 테이블 데이터 : 서용욱
        - 4. 찜한 방 목록(LOVE ROOM)테이블 데이터 : 이경섭
        - 5. 관리자 계정(ADMIN INFO)테이블 데이터 : 이경섭, 김동환
    - 시퀀스 구성
        - RoomInfo 테이블의 house_num , Love Room 테이블의 Shouse_num 시퀀스 적용 : 이경섭
- **쿼리 작성**
    - INFO :  김동환
    - ROOMINFO : 이경섭
    - MY_PAGE : 서용욱
    - LOVE ROOM : 김세호
    - ROOM SEARCH : 김세호
    - ADMIN INFO : 김동환
- **JDBC**
    - Common
        - Util :  이경섭
    - VO
        - InfoVo :  김동환
        - RoomInfoVo : 이경섭
        - MyPageVo: 서용욱
        - LoveRoomVo : 김세호
        - RoomSearchVo : 김세호
        - AdminInfoVo : 김동환
    - DAO
        - InfoDAO :  김동환
        - RoomInfoDAO : 이경섭
        - MyPageDAO: 서용욱
        - LoveRoomDAO : 김세호
        - RoomSearchDAO : 김세호
        - AdminInfoDAO : 김동환
    - Main : 이경섭
- **Thymeleaf**
    - RoomInfo select/insert : 김세호
    - RoomInfo insert/select + css :  이경섭
    - MyPage select/update/delete : 서용욱
    - AdminInfo select/insert : 김동환
    - Login select : 김동환
- **PPT 협업**

https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/94364018-f821-4db9-98bc-824a984407d1

[올룸골룸 발표자료.pdf](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/files/15060384/1.pdf)

# 8. 진행 순서

## [1단계] 요구사항 분석(External Schema)

1. **검색 기능**: 사용자는 지역, 가격대, 크기, 시설 등을 기준으로 부동산을 검색
2. **매물 정보**: 부동산의 사진, 가격, 위치, 설명 등에 대한 자세한 정보가 제공
3. **저장 기능**: 사용자가 관심 있는 매물을 저장하거나 북마크 기능
4. **사용자 프로필**: 사용자는 개인 프로필을 설정 및 관리
5. **보안**: 개인정보 보호 및 결제 시스템
6. **사용자 경험**: 사용자가 쉽게  검색하고 필요한 정보를 얻을 수 있는 직관적인 인터페이스

## [2단계] 개념적 설계 (Conceptual Schema)

1. **사용자 관리 시스템**:
    - 사용자 등록 및 로그인 기능
    - 사용자 프로필 관리
2. **매물 관리 시스템**:
    - 부동산 매물 정보 데이터베이스
    - 매물 등록 및 수정 기능
    - 매물 검색 및 필터링 기능
3. **보안 및 개인정보 보호**:
    - 안전한 로그인 및 데이터 전송을 위한 보안 시스템
4. **사용자 경험 개선을 위한 UI/UX**:
    - 직관적이고 사용하기 쉬운 인터페이스 디자인
    - 모바일 및 데스크톱 버전의 호환성 고려

## [3단계] 논리적 설계  (Logical Schema)

- **[로그인 페이지]**
    - [로그인 페이지] ID(이메일 형식), PASSWORD 입력 후 일치 여부, 확인(SELECT).
    - [회원가입 페이지] ID, 이름, PASSWORD, 기타 개인정보 확인 후 입력완료하면 마이페이지에 데이터를 생성하고 로그인 페이지로 이동(INSERT).
    - 로그인 성공시 올룸/골룸(Insert/Select) 선택 페이지로 이동.
- **[방 입력 페이지]**
    - [방 등록 페이지] 판매할 방 데이터 추가(방 사진, 거래방식, 가격대, 옵션 등) 후 방 등록 완료 → 메인페이지 이동(INSERT)
- **[마이페이지]**
    - [개인정보 수정] PASSWORD, 핸드폰 번호, 주소, 닉네임 수정 및 탈퇴(UPDATE,DELETE)
    - [골룸 목록] 찜한방 목록 테이블에서 매물번호로 방정보를 연결 후 거래 방식, 가격 , 주소, 비고 데이터로 방 정보 표시 후 사용자 방 페이지로 이동 (SELECT)
    - [올룸 목록] roominfo테이블에서 유저id로 올린 1.방데이터 2. 옵션 데이터 수정 및 삭제(SELECT, Update, DELECT)
    - [로그아웃] 로그인 페이지로 이동.
    - 메인페이지 이동.
- **[검색 페이지]**
    - [1단계] 지역 검색 : 방 테이블에서 주소를 보고 행정구역상 ‘구’ 까지 검색(SELECT)
    - [2단계] 거래방식: 월세, 전세, 매매 선택 후 월세(보증금, 월세), 전세(전세금), 매매(매매가) 로 검색(SELECT),
    - [3단계] 면적 검색 : 단위 평 수로 검색(SELECT)
    - [4단계] 층수 검색 : 반지층, 지층, 루프탑 선택 검색(SELECT)
    - 검색완료를 누르면 검색 목록 페이지 이동
    - 메인페이지 이동.
- **[검색 목록 페이지]**
    - [방 목록] 거래 방식, 가격 , 주소, 비고로 방 정보 표시 후 사용자 방 페이지로 이동(SELECT)
- **[사용자 방 페이지]**
    - 해당되는 방 테이블 정보를 불러오기(SELECT), 찜하기(Update)
- **[관리자 페이지]**
    - [관리권한] 회원 관리와 방 테이블 관리( SELECT, INSERT,UPDATE,DELETE)
    - 관리자 계정, 전화번호 표시

## [4단계] 물리적 설계

- **[테이블생성]**
- **[데이터 입력]**
- **[쿼리문 작성]**
- **[JDBC와 연결]**

## [5단계] 구현

- Console 구현

- thymeleaf 구현

# 9. DB 테이블 구성

## **초기 구현 단계**

### <03월 26일 : 주제 선정 후 프로젝트 Flow 초안>

![20240326_171913](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/95adeddc-0ca9-4f53-acac-814e300e03be)

### <03월 27일 : 테이블 ERD로 표현 후 관계 연결>

![올룸골룸](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/7b5dda68-5090-435c-890c-ea1797840146)

### <03월 28일 : 1차 회의 후 불필요 테이블 삭제>

![올룸골룸 EDR(03 28)](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/69dc9652-a663-407d-97ca-7e952d85024d)

### <03월 29일 : 데이터, 연결 관계 수정>

![올룸골룸 (1)](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/db55a93a-b8ec-41fa-acf7-3366131acef7)

###  ERD 최종

![erd최종 PNG (1)](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/95610e20-2bc5-4623-8813-9047b2f9c540)

###  스토리 보드

![555555555555555555555555555555 (1)](https://github.com/Leegyeongseob/jdbc_thymeleaf_PR/assets/67867076/ee89294f-9e4b-4301-9159-eae2a08052a3)

# 10. 참고자료 및 링크

## GitHub url

## Team
|<img src="https://avatars.githubusercontent.com/u/67867076?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/161570998?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/161570977?v=4" width="150" height="150"/>|<img src="https://avatars.githubusercontent.com/u/49334905?v=4" width="150" height="150"/>|
|:-:|:-:|:-:|:-:|
|Neo.경섭<br/>[@Leegyeongseob](https://github.com/Leegyeongseob)|[@tjdyddnr1](https://github.com/tjdyddnr1)|kimfjd<br/>[@kimfjd](https://github.com/kimfjd)|[@tpgh1554](https://github.com/tpgh1554)|

## Git Bash 참고 사이트

https://shortcuts.tistory.com/8

## ERD 참고 사이트

https://www.erdcloud.com/

# 11. 피드백

1. DB에서 테이블 간의 relation을 좀더 명확하게 했으면 좋았겠다고 생각이 들었습니다.
2. 데이터 크롤링을 배우기 전이라 default 데이터로만 개발해서 아쉬웠습니다.
3. 5일이라는 제작기간에 비해 기능을 너무 많이 넣어서 개발시간이 너무 촉박했습니다.(기획 단계 중요!)
4. html, css를 아직 배우지 않아 웹 화면을 표현하는데 쉽지 않았고 퀄리티도 만족스럽지 못했습니다.
5. javascript를 아직 배우지 않아 관리자모드마다 새로운 html페이지를 만들어야 했습니다.(페이지량 + 1.5배) 프론트엔드의 중요성을 뼈저리게 느꼈습니다.
6. 최대한 에러처리와 예외처리를 하려고 했습니다. 회원가입시 타입일치, 로그인 가능/불가, 테이블 reference 데이터 삭제시 자식 노드먼저 삭제, try ~catch구문 사용 등.
