# 🌱 Spring Boot 블로그 · 게시판 · 포트폴리오

Spring Boot로 만든 개인 포트폴리오 웹사이트입니다. 부트스트랩 포트폴리오 템플릿 위에 **블로그, 게시판, 회원 관리** 기능을 붙였고, 수업에서 주차별로 기능을 하나씩 추가하며 완성했습니다.

## 주요 기능

- **포트폴리오 메인**: 소개, 프로젝트, 팀, 상세 소개 페이지 (핑크 테마)
- **블로그(Article)**: 글 작성·조회·수정·삭제(CRUD), 존재하지 않는 글 접근 시 에러 페이지
- **게시판(Board)**: 페이징, 키워드 검색, 글 작성·조회·수정·삭제, 로그인한 사용자만 접근
- **회원(Member)**: 회원가입, 이메일 중복 검사, BCrypt 비밀번호 암호화
- **로그인·보안 (Spring Security)**
  - 폼 로그인, remember-me, 로그인 성공/실패 핸들러
  - 세션 만료 페이지, 세션 시간 제한
  - CSRF 보호 (dev 프로필에서는 비활성화), XSS 보호 헤더
- **메일 내용 업로드**: 문의 내용을 `.txt` 파일로 저장

## 사용 기술

`Java 17` `Spring Boot 3.5` `Spring Data JPA` `Spring Security` `Thymeleaf` `MySQL` `Lombok` `Bootstrap 5` `Maven`

## 프로젝트 구조

```text
demo/src/main/java/com/example/demo/
├── Controller/   # Blog, BlogRest, Member, File, Demo 컨트롤러
├── config/       # SecurityConfig, UserDetails
└── model/
    ├── domain/      # Article, Board, Member 엔티티
    ├── repository/  # JPA Repository
    └── service/     # 비즈니스 로직, DTO
demo/src/main/resources/
├── templates/    # Thymeleaf 화면 (board_*, article_*, login, join_*)
└── static/       # CSS, JS, 이미지
```

## 실행 방법

1. MySQL에 `spring` 데이터베이스 생성
2. DB 비밀번호를 환경변수 `DB_PASSWORD`로 설정 (`application.properties`에서 읽어옵니다)
3. `demo` 폴더에서 실행

```bash
./mvnw spring-boot:run
```

4. 브라우저에서 `http://localhost:8080` 접속

> 로컬(http)에서 로그인 유지가 안 되면 `server.servlet.session.cookie.secure`를 `false`로 바꾸세요.

## 주차별 진행 내용

| 주차 | 내용 |
|---|---|
| 2주차 | 개발 환경 구축, 프로젝트 생성, 컨트롤러·뷰 연결, GitHub 연동 |
| 3주차 | 부트스트랩 포트폴리오 템플릿 적용, 상세 소개 페이지 추가 |
| 4주차 | MySQL 연동, MVC 패키지 구조화 |
| 5주차 | 블로그 글 조회·작성, DTO 도입 |
| 6주차 | 글 수정·삭제, 에러 페이지 처리 |
| 이후 | 게시판 페이징·검색, 회원가입·로그인, Spring Security, 세션, 파일 업로드 |
