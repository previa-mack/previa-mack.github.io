<script lang="ts">
import {defineComponent} from "vue";

import TheHeader from "@/components/TheHeader.vue";
import TheFooter from "@/components/TheFooter.vue";

export default defineComponent({
  components: {
    TheFooter,
    TheHeader,
  },
})
</script>

<template>
  <the-header/>
  <router-view v-slot="{ Component }">
    <transition name="bounce">
      <component :is="Component"/>
    </transition>
  </router-view>
  <the-footer/>
</template>

<style lang="scss">
#app {
  font-family: Roboto, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  text-align: center;
  color: #2c3e50;

  // Global colors
  --color-primary: #ff2424;

  section {
    margin-bottom: 10rem;
  }

  img {
    width: 100%;
    max-width: 35rem;
    height: auto;
  }
}

.bounce-enter-active {
  animation: bounce-in .5s ease-out both;
}

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(0.80);
  }
  100% {
    transform: scale(1);
  }
}

::-webkit-scrollbar {
  width: 5px;
  height: 5px;
  background: transparent;

  border-radius: 33333px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

::-webkit-scrollbar-thumb {
  border-radius: 33333px;

  background: rgba(0, 0, 0, 0.5);
}

::-webkit-scrollbar-thumb:hover {
  background: #555555;
}
</style>
