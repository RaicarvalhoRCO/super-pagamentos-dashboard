<template>
  <div class="main-dashboard">
    <DashboardHeader></DashboardHeader>

    <!-- Card de Faturamento -->
    <VRow class="mt-6">
      <VCol cols="12">
        <FaturamentoCard />
      </VCol>
    </VRow>

    <!-- Cards de Status -->
    <VRow class="mt-6">
      <VCol cols="12">
        <StatusCobrancas />
      </VCol>
    </VRow>

    <!-- Conversão e Bandeiras -->  
    <VRow class="mt-6">
      <VCol cols="12" md="6">
        <ConversaoModalidade />
      </VCol>
      <VCol cols="12" md="6">
        <BandeirasUtilizadas />
      </VCol>
    </VRow>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import DashboardHeader from './DashboardHeader.vue';
import FaturamentoCard from './FaturamentoCard.vue';
import StatusCobrancas from './StatusCobrancas.vue';
import ConversaoModalidade from './ConversaoModalidade.vue';
import BandeirasUtilizadas from './BandeirasUtilizadas.vue';

export default defineComponent({
  name: 'MainDashboard',
  components: {
    DashboardHeader,
    FaturamentoCard,
    StatusCobrancas,
    ConversaoModalidade,
    BandeirasUtilizadas,
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
