<template>
  <div id="app">
    <!-- 탑헤더 영역 -->
    <header class="top-header">
      <button class="drawer-button" @click="toggleDrawer">☰</button>
      <img src="path/to/your/logo.png" alt="CI Logo" class="ci-logo">
      <button class="login-button">로그인</button>
    </header>

    <transition name="slide">
      <DrawerMenu v-if="isDrawerVisible" @close="toggleDrawer"/>
    </transition>    

    <!-- 콘텐츠 표현 영역 -->
    <main class="content">
      <section class="slide-banner">슬라이드 배너 영역</section>
      <section class="product-area1">
        <div v-for="n in 1000" :key="n">상품 {{ n }} 정보</div>
      </section>
      <section class="product-area2">상품 영역 2</section>

      <ProductArea2/>
    </main>

    <!-- 바텀 영역 -->
    <footer class="bottom-area">
      <div class="site-map">사이트 맵</div>
      <div class="site-creator">사이트 제작자 정보</div>
    </footer>

    <!-- 플로팅 네비게이션 영역 -->
    <nav class="floating-nav">
      <button>홈</button>
      <button>검색</button>
      <button>설정</button>
    </nav>


  </div>
</template>

<script>
import ProductArea2 from './components/ProductArea2.vue';
import DrawerMenu from './components/DrawerMenu.vue';

export default {
  name: 'App',
  components: {
    ProductArea2,
    DrawerMenu
  },
  data() {
    return {
      isDrawerVisible: false,
    };
  },
  methods: {
    toggleDrawer() {
      this.isDrawerVisible = !this.isDrawerVisible;
    },
  },
};
</script>

<style>
/* 간단한 스타일링 예시입니다. 실제 프로젝트에서는 필요에 맞게 조정하세요. */
.top-header {
  display: flex;
  justify-content: space-between;
  padding: 10px;
  background-color: #f0f0f0;
}

.content {
  padding: 20px;
}

.bottom-area {
  background-color: #d9d9d9;
  padding: 20px;
  width: 100%;
  text-align: center;
  padding-bottom: 50px; /* 플로팅 네비게이션 높이만큼 추가 */
}

.floating-nav {
  position: fixed;
  bottom: 0;
  width: 100%;
  display: flex;
  justify-content: space-around;
  background-color: #e0e0e0;
  padding: 10px 0;
}

/* 추가적인 스타일은 프로젝트 요구사항과 디자인 가이드에 따라 달라질 수 있습니다. */
</style>
