<template>
  <VCard class="faturamento-card pa-6" elevation="0">
    <div class="d-flex justify-space-between align-center mb-4">
      <div>
        <div class="d-flex align-center">
          <h3 class="text-h6 font-weight-bold">Faturamento</h3>
          <VIcon size="small" class="ml-2">bi-eye-fill</VIcon>
        </div>
        <div class="d-flex align-center mt-2">
          <span class="text-h4 font-weight-bold">R$ {{ formatarValor(faturamentoTotal) }}</span>
          <div class="crescimento ml-3">
            <VIcon size="x-small">mdi-arrow-up</VIcon>
            <span>{{ crescimento }}%</span>
            <p style="color: #86898B; font-size: 12px;">
              Em crescimento
            </p>
          </div>
        </div>
      </div>
    </div>

    <div class="grafico-container">
      <div class="barras d-flex align-end" style="height: 200px;">
        <div v-for="(valor, index) in dadosGrafico" :key="index" class="barra-wrapper">
          <span class="label-dia">{{ valor.dia }}</span>
          <div class="barra" :style="{ height: calcularAltura(valor) + '%' }">
            <div class="barra-recebido" :style="{ height: (valor.recebido / valor.total * 100) + '%' }"></div>
            <div class="barra-previsto" :style="{ height: (valor.previsto / valor.total * 100) + '%' }"></div>
          </div>
        </div>
      </div>
    </div>

    <VRow class="metricas-resumo mt-6">
      <VCol cols="auto metricas">
        <div class="d-flex align-center">
          <div class="ml-3">
            <div class="metrica-label">Faturamento recebido</div>
            <div class="metrica-valor">
              <div class="d-flex mr-2">
                <div class="legenda-menor azul"></div>
                <div class="legenda-maior azul"></div>
              </div>
              <div>R$ {{ formatarValor(faturamentoRecebido) }}</div>
            </div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto metricas">
        <div class="d-flex align-center">
          <div class="ml-3">
            <div class="d-flex align-center gap-2 mb-1">
              <div class="metrica-label">Faturamento previsto</div>
              <VChip size="x-small" variant="outlined" color="black" class="px-2 chip-d2">D+2</VChip>
            </div>
            <div class="metrica-valor">
              <div class="d-flex mr-2">
                <div class="legenda-menor roxo"></div>
                <div class="legenda-maior roxo"></div>
              </div>
              <div>R$ {{ formatarValor(faturamentoPrevisto) }}</div>
            </div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto metricas">
        <div class="d-flex align-center">
          <div class="ml-3">
            <div class="metrica-label">Vendas pendentes</div>
            <div class="metrica-valor">
              <div class="d-flex mr-2">
                <div class="legenda-menor laranja"></div>
                <div class="legenda-maior laranja"></div>
              </div>
              <div>R$ {{ formatarValor(vendasPendentes) }}</div>
            </div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto metricas">
        <div class="d-flex align-center">
          <div class="ml-3">
            <div class="metrica-label">Ticket médio</div>
            <div class="metrica-valor">
              <div class="d-flex mr-2">
                <div class="legenda-menor rosa"></div>
                <div class="legenda-maior rosa"></div>
              </div>
              <div>R$ {{ formatarValor(ticketMedio) }}</div>
            </div>
          </div>
        </div>
      </VCol>
      <VCol cols="auto metricas">
        <div class="d-flex align-center">
          <div class="ml-3">
            <div class="metrica-label">Número de cobranças</div>
            <div class="metrica-valor">
              <div class="d-flex mr-2">
                <div class="legenda-menor cinza"></div>
                <div class="legenda-maior cinza"></div>
              </div>
              <div>{{ numeroCobrancas.toLocaleString('pt-BR') }}</div>
            </div>
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
      crescimento: 123.9,
      faturamentoRecebido: 245340.90,
      faturamentoPrevisto: 815210.24,
      d2: 15332.18,
      vendasPendentes: 192.30,
      ticketMedio: 192.30,
      numeroCobrancas: 12349,
      dadosGrafico: Array.from({ length: 31 }, (_, i) => {
        const dia = i + 1;
        const recebido = Math.floor(Math.random() * 50000) + 20000;
        const previsto = Math.floor(Math.random() * 15000) + 5000;
        return {
          dia,
          recebido,
          previsto,
          total: recebido + previsto
        };
      })
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
  align-items: flex-end;
  justify-content: space-around;
}

.barra-wrapper {
  display: flex;
  flex-direction: column-reverse;
  align-items: center;
  flex: 1;
  height: 100%;
  max-width: 8px;
  background-color: #F5F5F5;
  border-radius: 16px
}

.barra {
  width: 100%;
  max-width: 24px;
  min-height: 20px;
  background: #f0f0f0;
  border-radius: 4px;
  overflow: hidden;
  position: relative;
  display: flex;
  flex-direction: column;
}

.barra-recebido {
  background: #0641FC;
  width: 100%;
  min-height: 5px;
  order: 2;
}

.barra-previsto {
  background: #9D5CFF;
  width: 100%;
  min-height: 5px;
  order: 1;
}

.label-dia {
  font-size: 11px;
  color: #666;
  margin-top: 8px;
}

.metricas-resumo {
  gap: 10px;
  padding-top: 16px;
  border-top: 1px solid #e0e0e0;
}

.metricas {
  width: 230px;
  height: 80px;
  border-radius: 16px;
  border: 1px solid #EEEEEE;
}

.legenda-menor {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  margin: auto;
}

.legenda-maior {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  margin: auto;
}

.legenda-menor.azul {
  background: #0641FC;
}

.legenda-menor.roxo {
  background: #9D5CFF;
}

.legenda-menor.laranja {
  background: #FF9500;
}

.legenda-menor.verde {
  background: #34C759;
}

.legenda-menor.rosa {
  background: #B882FE;
}

.legenda-menor.cinza {
  background: #2A2E33;
}

.legenda-maior.azul {
  background: #0641FC73;
  margin: 4px 2px;
  position: absolute;
}

.legenda-maior.roxo {
  background: #9D5CFF73;
  margin: 4px 2px;
  position: absolute;
}

.legenda-maior.laranja {
  background: #FF950073;
  margin: 4px 2px;
  position: absolute;
}

.legenda-maior.verde {
  background: #34C75973;
  margin: 4px 2px;
  position: absolute;
}

.legenda-maior.rosa {
  background: #B882FE73;
  margin: 4px 2px;
  position: absolute;
}

.legenda-maior.cinza {
  background: #8E9373;
  margin: 4px 2px;
  position: absolute;
  z-index: -1;
}

.metrica-label {
  font-size: 12px;
  margin-bottom: 4px;
  color: #86898B;
}

.metrica-valor {
  color: #000;
  display: flex;
  font-family: Plus Jakarta Sans;
  font-weight: 700;
  gap: 5px;
  font-size: 20px;
  line-height: 100%;
  margin-top: 15px;
}

.chip-d2 {
  background: transparent !important;
  border: 1px solid #D9D9D9;
}

.crescimento span,
.crescimento i {
  color: #34A853;
  font-family: Plus Jakarta Sans;
  font-weight: 800;
  font-size: 12px;
}

@media (max-width: 768px) {
  .faturamento-card {
    display: none;
  }
}

@media (max-width: 1300px) {
  .faturamento-card {
    margin-left: 20%;
  }
}
</style>
