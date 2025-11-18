<template>
  <div class="main-dashboard">
    <DashboardHeader></DashboardHeader>

    <!-- Card de Faturamento -->
    <VRow class="mt-6">
      <VCol cols="12">
        <FaturamentoCard />
      </VCol>
    </VRow>

    <!-- Alerta de Transferência Pendente -->
    <VRow class="mt-4">
      <VCol cols="12">
        <TransferenciaPendente />
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
import TransferenciaPendente from './TransferenciaPendente.vue';
import StatusCobrancas from './StatusCobrancas.vue';
import ConversaoModalidade from './ConversaoModalidade.vue';
import BandeirasUtilizadas from './BandeirasUtilizadas.vue';

export default defineComponent({
  name: 'MainDashboard',
  components: {
    DashboardHeader,
    FaturamentoCard,
    TransferenciaPendente,
    StatusCobrancas,
    ConversaoModalidade,
    BandeirasUtilizadas,
  },
});
</script>

<style scoped>
.main-dashboard {
  padding: 100px 5% 100px 20%;
  background-color: #EDEFF4;
}

@media (max-width: 768px) {
  .main-dashboard {
    padding: 10px;
  }
}
</style>
