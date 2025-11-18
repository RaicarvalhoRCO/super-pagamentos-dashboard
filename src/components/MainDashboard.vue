<template>
  <div class="main-dashboard">
    <MobileTopBar />
    <DashboardHeader></DashboardHeader>
    <MobileNewChargeButton />
    <MobileStatsChart />
    <MobileMetricsCarousel />
    <MobileTransferenciaPendente />
    <MobileStatusCobrancas />

    <!-- Card de Faturamento -->
    <VRow class="mt-6 desktop-only">
      <VCol cols="12">
        <FaturamentoCard />
      </VCol>
    </VRow>

    <!-- Alerta de Transferência Pendente -->
    <VRow class="mt-4 desktop-only">
      <VCol cols="12">
        <TransferenciaPendente />
      </VCol>
    </VRow>

    <!-- Cards de Status -->
    <VRow class="mt-6 desktop-only">
      <VCol cols="12">
        <StatusCobrancas />
      </VCol>
    </VRow>

    <!-- Conversão e Bandeiras -->
    <VRow class="mt-6 justify-center align-center">
      <div class="d-flex bottom-container">
        <VCol cols="12" md="6" class="d-flex justify-center">
          <ConversaoModalidade />
        </VCol>
        <VCol cols="12" md="6">
          <BandeirasUtilizadas />
        </VCol>
      </div>

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
import MobileTopBar from './MobileTopBar.vue';
import MobileNewChargeButton from './MobileNewChargeButton.vue';
import MobileStatsChart from './MobileStatsChart.vue';
import MobileMetricsCarousel from './MobileMetricsCarousel.vue';
import MobileTransferenciaPendente from './MobileTransferenciaPendente.vue';
import MobileStatusCobrancas from './MobileStatusCobrancas.vue';

export default defineComponent({
  name: 'MainDashboard',
  components: {
    DashboardHeader,
    FaturamentoCard,
    TransferenciaPendente,
    StatusCobrancas,
    ConversaoModalidade,
    BandeirasUtilizadas,
    MobileTopBar,
    MobileNewChargeButton,
    MobileStatsChart,
    MobileMetricsCarousel,
    MobileTransferenciaPendente,
    MobileStatusCobrancas,
  },
});
</script>

<style scoped>
.main-dashboard {
  padding: 100px 5% 100px 20%;
  background-color: #EDEFF4;
  width: 100%;
}

@media (max-width: 768px) {
  .main-dashboard {
    padding: 220px 16px 100px 16px;

  }

  .desktop-only {
    display: none;
  }
}

@media (max-width: 1600px) {
  .bottom-container {
    flex-direction: column;
  }
}


</style>
