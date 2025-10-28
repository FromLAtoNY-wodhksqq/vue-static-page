<template>
  <div class="min-h-screen flex flex-col items-center justify-center bg-gradient-to-b from-yellow-50 to-amber-100 text-gray-800">
    <!-- 달 -->
    <div class="relative">
      <div class="w-40 h-40 bg-yellow-300 rounded-full shadow-lg animate-pulse"></div>
      <div class="absolute -top-10 -left-10 w-20 h-20 bg-yellow-200 rounded-full opacity-60 blur-lg"></div>
    </div>

    <!-- 타이틀 -->
    <h1 class="mt-8 text-4xl font-bold tracking-wide text-amber-700">
      🌕 한가위 잘 보내세요 🌾
    </h1>

    <!-- 서브 문구 -->
    <p class="mt-4 text-lg text-amber-600 font-medium">
      가족과 함께 따뜻한 마음 나누는 명절 되세요 💛
    </p>

    <!-- 버튼 -->
    <button
        class="mt-8 px-6 py-3 rounded-full bg-amber-500 text-white font-semibold hover:bg-amber-600 transition-all shadow-md"
        @click="bless"
    >
      복 받기 🎁
    </button>

    <!-- 복 메시지 -->
    <transition name="fade">
      <p v-if="showBless" class="mt-6 text-2xl text-amber-700 font-semibold animate-bounce">
        🎉 복이 도착했어요! 🎉
      </p>
    </transition>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

const showBless = ref(false)

function bless() {
  showBless.value = true
  setTimeout(() => (showBless.value = false), 2500)
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.8s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
