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
    <headerCom />
    <!-- logo   -->
    <div
      class="w-[1220px] mt-[60px] m-[10px] max-w-full h-[90vh] p-8 rounded-3xl bg-white/10 backdrop-blur-xl border border-white/20 shadow-lg flex flex-col overflow-hidden"
    >
      <!-- Title -->
      <div class="h-8 flex items-center justify-between mb-6 px-6">
        <h1 class="text-2xl font-extrabold tracking-wide drop-shadow-md">{{currentAppName}}</h1>
      </div>

      <!-- Main Content with Element Plus Scrollbar -->
       <div class="flex-1 overflow-hidden">
        <el-scrollbar class="h-full  rounded-lg bg-white/20 p-6 backdrop-blur-md border border-white/30 shadow-inner relative">
          <RouterView />
        </el-scrollbar>
       </div>
    </div>
  </div>
</template>
<style>
.logo {
  font-family: 'Caveat', cursive;
}
.el-scrollbar__thumb {
  background-color: rgba(255, 255, 255, 0.87);
  border-radius: 4px;
}
</style>