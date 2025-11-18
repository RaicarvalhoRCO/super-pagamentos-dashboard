<template>
  <VRow class="p-3 rounded dashboard-header" cols="12" md="12">
    <VCol>
      <VRow class="no-gutters">
        <VBtn rounded height="46" class="new_bill_button">
          <span>Nova cobrança</span>
          <IconPlus />
        </VBtn>

        <VDivider vertical class="mx-3" />

        <div class="selector_container d-flex align-center">
          <IconCalendar class="icon-calendar" />
          <VSelect :items="periodoItems" v-model="periodoSelecionado" label="Período" variant="text"
            density="comfortable" class="selector" />
        </div>

        <div class="d-flex align-center border rounded-pill px-4 selector_date mx-3">
          <IconCalendar class="icon-calendar" />
          <DatePicker v-model="dataDe" />
          <span class="separator">|</span>
          <DatePicker v-model="dataAte" />
        </div>
      </VRow>
    </VCol>
    <VCol cols="auto">
      <VRow align="center" class="no-gutters">
        <div class="selector_container d-flex align-center">
          <VSelect :items="tipoCobrancaItems" v-model="tipoCobrancaSelecionado" label="Tipo de cobrança" variant="text"
            density="comfortable" />
        </div>
        <VBtn icon variant="flat" class="ml-3 download-btn">
          <i class="bi bi-download"></i>
        </VBtn>
      </VRow>
    </VCol>
  </VRow>
</template>

<script>
import IconPlus from './icons/IconPlus.vue';
import IconCalendar from './icons/IconCalendar.vue';
import DatePicker from './DatePicker.vue';

export default {
  name: "DashboardHeader",
  components: {
    IconPlus,
    IconCalendar,
    DatePicker,
  },
  data() {
    return {
      periodoItems: ['Período: Específico', 'Mês atual', 'Últimos 30 dias'],
      periodoSelecionado: 'Período: Específico',
      dataDe: '2020-06-10',
      dataAte: '2025-01-30',
      tipoCobrancaItems: ['Tipo de cobrança', 'PIX', 'Boleto', 'Cartão'],
      tipoCobrancaSelecionado: 'Tipo de cobrança',
    };
  },
};
</script>

<style scoped>
.dashboard-header {
  background-color: transparent;
}

@media (max-width: 768px) {
  .dashboard-header {
    display: none !important;

  }
}


@media (max-width: 1300px) {
  .dashboard-header {
    margin: 5% 0% 0% 20%;
  }
}

@media (max-width: 1400px) {
  .dashboard-header {
    flex-wrap: inherit;
  }
}


.filters {
  display: flex;
  align-items: center;
  justify-content: flex-end;
}

.filter-item {
  margin-right: 16px;
}

.new_bill_button {
  width: 160px;
  height: 46px;
  border-radius: 32px;
  letter-spacing: 0;
  background-color: #0641FC;
  color: white;

}

.new_bill_button span {
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 14px;
  line-height: 100%;
  margin-right: 10px;
  text-transform: none;
}

.selector_container {
  height: 48px;
  border: 1px solid #D9D9D9;
  border-radius: 32px;
  background-color: white;
}

.selector_container svg {
  margin-left: 14px;
}

.selector_container .v-input {
  margin-top: 6px;
  font-size: 14px;
  font-weight: 600;
}

.selector_date {
  background-color: white;
  position: relative;
  height: 48px;
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 14px;
  border-color: #D9D9D9;
  gap: 12px;
}

.selector_date .separator {
  color: #D9D9D9;
  font-weight: 400;
  margin: 0 8px;
}

.download-btn {
  width: 48px;
  height: 48px;
  border: 1px solid #D9D9D9;
  background-color: white;
}
</style>
