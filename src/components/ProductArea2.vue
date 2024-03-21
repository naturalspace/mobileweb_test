<template>
    <div class="product-area2">
      <!-- 모바일 최적화 레이아웃 -->
      <div class="mobile-optimized">
        <h2>모바일 최적화 상품</h2>
        <!-- 모바일 최적화 상품 내용 -->
      </div>
  
      <!-- 태블릿 최적화 레이아웃 -->
      <div class="tablet-optimized">
        <h2>태블릿 최적화 상품</h2>
        <!-- 태블릿 최적화 상품 내용 -->
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ProductArea2',
  };
  </script>
  
  <style>
  /* 모바일 뷰 */
  @media (max-width: 600px) {
    .tablet-optimized {
      display: none;
    }
    .mobile-optimized {
      /* 모바일 최적화 스타일 */
    }
  }
  
  /* 태블릿 뷰 */
  @media (min-width: 601px) {
    .mobile-optimized {
      display: none;
    }
    .tablet-optimized {
      /* 태블릿 최적화 스타일 */
    }
  }
  </style>
  