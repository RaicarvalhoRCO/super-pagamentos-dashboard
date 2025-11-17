<template>
    <div class="main-dashboard">
        <DashboardHeader></DashboardHeader>
    </div>
</template>

<script>
import { defineComponent } from 'vue';
import DashboardHeader from './DashboardHeader.vue';

export default defineComponent({
    name: 'MainDashboard',
    components: {
        DashboardHeader,
    },
});
</script>

<style scoped>
.main-dashboard {
    padding: 100px 160px;
}

@media (max-width: 768px) {
    .main-dashboard {
        padding: 10px;
    }
}
</style>