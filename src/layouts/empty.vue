<script setup>
import { RouterView,useRoute  } from 'vue-router'
import {getMenuName} from '@/router/menu'

const route = useRoute()
const currentAppName = computed(()=>getMenuName(route.path) ?? '')

</script>

<template>
  <div
    class="h-screen w-screen text-white flex items-center justify-center overflow-hidden"
  >
    <!-- logo   -->
     <main
        class="flex-1 overflow-auto p-6relative"
      >
        <RouterView />
      </main>
  </div>
</template>
<style>
.logo {
  font-family: 'Caveat', cursive;
}
</style>