# Swagger 연동 실습 (프론트)

Swagger 강의 PPT의 실습 코드예요. Vite + React + Tailwind로 세팅되어 있어요.

## 실행

```bash
npm install
npm run dev
```

→ http://localhost:5173

## 파일

| 파일 | 내용 |
| --- | --- |
| `src/api/config.js` | 서버 주소 (BASE_URL) · PPT 직접 쓰기 1 |
| `src/api/posts.js` | GET · POST · PATCH · DELETE 요청 함수 · PPT 직접 쓰기 2 |
| `src/App.jsx` | 게시글 목록 + 작성·수정 입력창 + 삭제 버튼 |
| `src/index.css` | Tailwind 세팅(과제용) + 실습 화면 기본 간격 |

- 서버 주소는 `src/api/config.js`에서 바꿔요. 현재는 강의의 Railway 서버를 사용해요.
- 페이지를 열면 `GET /posts`로 제목·내용·작성자 목록을 불러와요. `조회하기`로 다시 조회할 수 있어요.
- `글 쓰기`를 누르면 입력창이 열려요. 제목·내용·작성자를 입력하고 `등록`을 누르면 `POST /posts`로 저장해요.
- 게시글의 `수정`을 누르면 기존 제목·내용이 입력창에 채워져요. `수정 저장`을 누르면 `PATCH /posts/{postId}`로 저장해요. 작성자는 그대로 유지해요.
- `삭제`를 누르고 확인하면 `DELETE /posts/{postId}`로 지워요. 작성·수정·삭제 후 목록을 다시 불러와요.
- 제목은 100자, 내용은 1,000자, 작성자는 20자까지 입력할 수 있어요. 요청이 실패하면 기본 알림창을 띄우고, 작성·수정 중 입력값은 유지해요.
- 강의 서버는 함께 쓰는 실습 서버예요. 작성자에는 본인 이름을 입력하고 본인 글을 수정·삭제해 주세요.
- Tailwind의 기본 초기화(preflight)는 빼고 불러와서 버튼 테두리와 목록 점이 그대로 보여요. 과제에서 `className="..."`으로 꾸미면 그게 우선 적용돼요.

입력값은 `FormData`로 읽어요. React 상태는 게시글 목록, 열린 입력창, 요청 중 여부만 관리해요.
버튼은 Swagger 색상을 사용해요: GET 파랑, POST 초록, PATCH 청록, DELETE 빨강.
