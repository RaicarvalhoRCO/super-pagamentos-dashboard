<template>
  <VRow class="status-container">
    <VCol v-for="status in statusList" :key="status.tipo">
      <VCard class="status-card pa-4" elevation="0">
        <div class="d-flex justify-space-between align-center mb-2">
          <h4 class="status-card-text font-weight-medium">{{ status.tipo }}</h4>
          <div v-if="status.tipo === 'Chargebacks'" class="warning-badge">
            <VIcon icon="mdi-exclamation" color="black" size="12" />
          </div>
          <div class="icon-circle">
            <VIcon size="small">bi-percent</VIcon>
          </div>
        </div>

        <div class="valor-principal mb-1">{{ status.valor }}</div>
        <VDivider />

        <div class="info-adicional">
          <span class="cobrancas">{{ status.cobrancas }} cobranças</span>
          <span class="percentual ml-2">{{ status.percentual }}</span>

        </div>
      </VCard>
    </VCol>
  </VRow>
</template>

<script>
export default {
  name: 'StatusCobrancas',
  data() {
    return {
      statusList: [
        { tipo: 'Reembolsos', valor: 'R$ 8.260,10', cobrancas: '233', percentual: '4,5%' },
        { tipo: 'Chargebacks', valor: 'R$ 1.260,10', cobrancas: '5', percentual: '0,3%' },
        { tipo: 'Cancelados', valor: 'R$ 3.120,60', cobrancas: '32', percentual: '1,5%' },
        { tipo: 'Não autorizado', valor: 'R$ 6.120,60', cobrancas: '122', percentual: '3,1%' }
      ]
    };
  }
};
</script>

<style scoped>
.status-card {
  width: 305px;
  height: 165px;
  border-radius: 12px;
  border: 1px solid #e0e0e0;
}

.status-card-text {
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 16px;
  line-height: 100%;

}

.icon-circle {
  width: 46px;
  height: 46px;
  border-radius: 50%;
  background-color: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 1px solid black;
}

.valor-principal {
  font-size: 20px;
  font-weight: 700;
  color: #000;
}

.info-adicional {
  display: flex;
  align-items: center;
  font-size: 13px;
  color: #666;
  justify-content: space-between;
  position: relative;
}

.cobrancas {
  font-weight: 500;
}

.percentual {
  font-weight: 600;
}

.warning-badge {
  position: absolute;
  right: 0;
  top: 25px;
  left: 130px;
  width: 20px;
  height: 20px;
  background-color: #FFC107;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

@media (max-width: 768px) {
  .status-card {
    display: none;
  }
}

@media (max-width: 1300px) {
    .status-container {
        margin-left: 20%;
    }
}
</style>
