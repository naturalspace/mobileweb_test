<template>
  <div class="drawer-menu">
    <!-- 닫기 버튼 -->
    <button class="close-button" @click="closeDrawer">X</button>
    <!-- 드로어 메뉴 내용 -->
    <div>내용</div>
    <div>내용</div>
    <div>내용</div>
  </div>
</template>

<script>
export default {
  props: {
    isVisible: Boolean
  },
  methods: {
    closeDrawer() {
      this.$emit('close');
    }
  }
};
</script>

<style>
.drawer-menu {
  position: fixed;
  z-index: 1000; /* 다른 컨텐츠를 덮도록 z-index 설정 */
  left: 0;
  top: 0;
  width: 50%; /* 화면 너비의 50% */
  height: 100%; /* 전체 화면 높이 */
  background: #eee;
}

.close-button {
  position: absolute;
  top: 0;
  right: 0;
}

/* 드로어 메뉴가 나타날 때 초기 위치 */
.slide-enter {
  transform: translateX(-100%);
}

/* 드로어 메뉴가 나타날 때 적용되는 애니메이션을 정의합니다. */
.slide-enter-active {
  transition: transform 0.3s ease;
}

/* 드로어 메뉴가 사라질 때 적용되는 애니메이션을 정의합니다. */
.slide-leave-active {
  transition: transform 0.3s ease;
}

/* 드로어 메뉴가 사라진 후의 최종 위치 */
.slide-leave-to {
  transform: translateX(-100%);
}


/* 애니메이션 관련 스타일은 그대로 유지 */
</style>
