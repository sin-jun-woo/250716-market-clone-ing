<script>
  // 1. 페이지 컴포넌트 가져오기
  // 애플리케이션의 각 페이지를 담당하는 Svelte 컴포넌트들을 불러옵니다.
  import Main from "./pages/Main.svelte";
  import Signup from "./pages/Signup.svelte";
  import Write from "./pages/Write.svelte";
  import Login from "./pages/Login.svelte";

  // 2. 라우터 및 404 페이지 컴포넌트 가져오기
  // SPA(Single Page Application) 라우팅을 위한 라이브러리와
  // 일치하는 경로가 없을 때 보여줄 페이지를 불러옵니다.
  import Router from "svelte-spa-router";
  import Notfound from "./pages/Notfound.svelte";

  // 3. 전역 CSS 파일 가져오기
  // 앱 전체에 적용될 공통 스타일 시트를 불러옵니다.
  import "./css/style.css";

  // 4. 라우팅 규칙 정의
  // URL 경로와 해당 경로에서 보여줄 컴포넌트를 짝지어 정의하는 객체입니다.
  const routes = {
    // '/' 경로(메인 페이지)로 접속하면 Main 컴포넌트를 보여줍니다.
    "/": Main,
    // '/login' 경로로 접속하면 Login 컴포넌트를 보여줍니다.
    "/login": Login,
    // '/signup' 경로로 접속하면 Signup 컴포넌트를 보여줍니다.
    "/signup": Signup,
    // '/write' 경로로 접속하면 Write 컴포넌트를 보여줍니다.
    "/write": Write,
    // '*'는 와일드카드(wildcard)로, 위에서 정의한 경로 외의 모든 경로를 의미합니다.
    // 사용자가 잘못된 주소로 접속하면 Notfound 컴포넌트(404 페이지)를 보여줍니다.
    "*": Notfound,
  };
</script>

<!-- 5. 라우터 컴포넌트 렌더링 -->
<!-- Router 컴포넌트에 위에서 정의한 routes 객체를 props로 전달합니다. -->
<!-- Router는 현재 브라우저의 URL을 감지하여 routes 규칙에 맞는 페이지 컴포넌트를 이 위치에 렌더링합니다. -->
<Router {routes}></Router>
