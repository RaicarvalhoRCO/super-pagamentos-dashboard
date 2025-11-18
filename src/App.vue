<script setup>
import TopBar from './components/TopBar.vue';
import SideBar from './components/SideBar.vue';
import MainDashboard from './components/MainDashboard.vue';
import MobileFooter from './components/MobileFooter.vue';
</script>

<template>
  <div class="app-container h-100 d-flex flex-column">

    <div class="content flex-grow-1">
      <SideBar />
      <TopBar />
      <MainDashboard />
    </div>
    <MobileFooter />
  </div>
</template>

<style scoped>
.app-container {
  height: 100vh;
  overflow-x: hidden;
}

.content {
  display: flex;
  flex-direction: column;
}
</style>
