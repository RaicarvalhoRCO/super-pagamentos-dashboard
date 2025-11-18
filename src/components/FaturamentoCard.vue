<template>
  <VCard class="faturamento-card pa-6">
    <div class="d-flex justify-space-between align-center mb-4">
      <div>
        <div class="d-flex align-center">
          <h3 class="text-h6 font-weight-bold">Faturamento</h3>
          <VIcon size="small" class="ml-2">mdi-information-outline</VIcon>
        </div>
        <div class="d-flex align-center mt-2">
          <span class="text-h4 font-weight-bold">R$ {{ formatarValor(faturamentoTotal) }}</span>
          <VChip size="small" color="success" class="ml-3">
            <VIcon size="x-small" start>mdi-arrow-up</VIcon>
            {{ crescimento }}% Encrececimento
          </VChip>
        </div>
      </div>
    </div>

    <div class="grafico-container">
      <div class="barras d-flex align-end" style="height: 200px;">
        <div v-for="(valor, index) in dadosGrafico" :key="index" class="barra-wrapper">
          <div class="barra" :style="{ height: calcularAltura(valor) + '%' }">
            <div class="barra-recebido" :style="{ height: (valor.recebido / valor.total * 100) + '%' }"></div>
            <div class="barra-previsto" :style="{ height: (valor.previsto / valor.total * 100) + '%' }"></div>
          </div>
          <span class="label-dia">{{ valor.dia }}</span>
        </div>
      </div>
    </div>

    <VRow class="metricas-resumo mt-6">
      <VCol cols="auto">
        <div class="d-flex align-center">
          <div class="legenda-cor azul"></div>
          <div class="ml-3">
            <div class="metrica-label">Faturamento recebido</div>
            <div class="metrica-valor">R$ {{ formatarValor(faturamentoRecebido) }}</div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto">
        <div class="d-flex align-center">
          <div class="legenda-cor roxo"></div>
          <div class="ml-3">
            <div class="metrica-label">Faturamento previsto</div>
            <div class="metrica-valor">R$ {{ formatarValor(faturamentoPrevisto) }}</div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto">
        <div class="d-flex align-center">
          <div class="legenda-cor laranja"></div>
          <div class="ml-3">
            <div class="metrica-label">D+2</div>
            <div class="metrica-valor">R$ {{ formatarValor(d2) }}</div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto">
        <div class="d-flex align-center">
          <div class="legenda-cor verde"></div>
          <div class="ml-3">
            <div class="metrica-label">Vendas pendentes</div>
            <div class="metrica-valor">R$ {{ formatarValor(vendasPendentes) }}</div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto">
        <div class="d-flex align-center">
          <div class="legenda-cor rosa"></div>
          <div class="ml-3">
            <div class="metrica-label">Ticket médio</div>
            <div class="metrica-valor">R$ {{ formatarValor(ticketMedio) }}</div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto">
        <div class="d-flex align-center">
          <div class="legenda-cor cinza"></div>
          <div class="ml-3">
            <div class="metrica-label">Número de cobranças</div>
            <div class="metrica-valor">{{ numeroCobrancas.toLocaleString('pt-BR') }}</div>
          </div>
        </div>
      </VCol>
    </VRow>
  </VCard>
</template>

<script>
export default {
  name: 'FaturamentoCard',
  data() {
    return {
      faturamentoTotal: 1060551.14,
      crescimento: 83.9,
      faturamentoRecebido: 245340.90,
      faturamentoPrevisto: 815210.24,
      d2: 15332.18,
      vendasPendentes: 192.30,
      ticketMedio: 192.30,
      numeroCobrancas: 12349,
      dadosGrafico: [
        { dia: 1, recebido: 20000, previsto: 5000, total: 25000 },
        { dia: 2, recebido: 40000, previsto: 8000, total: 48000 },
        { dia: 3, recebido: 25000, previsto: 7000, total: 32000 },
        { dia: 4, recebido: 30000, previsto: 10000, total: 40000 },
        { dia: 5, recebido: 70000, previsto: 15000, total: 85000 },
        // ...adicione mais dados conforme necessário
      ]
    };
  },
  methods: {
    formatarValor(valor) {
      return valor.toLocaleString('pt-BR', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
    },
    calcularAltura(valor) {
      const max = Math.max(...this.dadosGrafico.map(d => d.total));
      return (valor.total / max) * 100;
    }
  }
};
</script>

<style scoped>
.faturamento-card {
  background: white;
  border-radius: 12px;
}

.grafico-container {
  width: 100%;
  overflow-x: auto;
}

.barras {
  display: flex;
  gap: 8px;
  padding: 16px 0;
}

.barra-wrapper {
  display: flex;
  flex-direction: column;
  align-items: center;
  flex: 1;
  min-width: 20px;
}

.barra {
  width: 100%;
  max-width: 24px;
  background: #f0f0f0;
  border-radius: 4px;
  overflow: hidden;
  position: relative;
  display: flex;
  flex-direction: column-reverse;
}

.barra-recebido {
  background: #0641FC;
  width: 100%;
}

.barra-previsto {
  background: #9D5CFF;
  width: 100%;
}

.label-dia {
  font-size: 11px;
  color: #666;
  margin-top: 8px;
}

.metricas-resumo {
  padding-top: 16px;
  border-top: 1px solid #e0e0e0;
}

.legenda-cor {
  width: 8px;
  height: 8px;
  border-radius: 50%;
}

.legenda-cor.azul {
  background: #0641FC;
}

.legenda-cor.roxo {
  background: #9D5CFF;
}

.legenda-cor.laranja {
  background: #FF9500;
}

.legenda-cor.verde {
  background: #34C759;
}

.legenda-cor.rosa {
  background: #FF2D55;
}

.legenda-cor.cinza {
  background: #8E8E93;
}

.metrica-label {
  font-size: 12px;
  color: #666;
  margin-bottom: 4px;
}

.metrica-valor {
  font-size: 14px;
  font-weight: 600;
  color: #000;
}
</style>
