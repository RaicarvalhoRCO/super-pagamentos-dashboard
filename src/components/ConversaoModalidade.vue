<template>
    <VCard class="conversao-card pa-6">
        <h4 class="title font-weight-bold mb-6">Conversão por modalidade</h4>
        <VRow class="conversao-container">
            <VCol v-for="modalidade in modalidades" :key="modalidade.nome" cols="6" md="3">
                <div class="modalidade-item text-center">
                    <div class="grafico-circular"
                        :style="{ background: gerarGraficoConico(modalidade.percentual, modalidade.cor) }">
                        <div class="grafico-center">
                            <span class="percentual-texto">{{ modalidade.percentual }}%</span>
                        </div>
                    </div>
                    <div class="modalidade-nome mt-3">{{ modalidade.nome }}</div>
                </div>
            </VCol>
        </VRow>
    </VCard>
</template>

<script>
export default {
    name: 'ConversaoModalidade',
    data() {
        return {
            modalidades: [
                { nome: 'Crédito', percentual: 92, cor: '#0641FC' },
                { nome: 'Débito', percentual: 95, cor: '#852DF6' },
                { nome: 'Boleto', percentual: 42, cor: '#B882FE' },
                { nome: 'Pix', percentual: 98, cor: '#9DB5FF' }
            ]
        };
    },
    methods: {
        gerarGraficoConico(percentual, cor) {
            return `conic-gradient(${cor} ${percentual}%, #f0f0f0 ${percentual}%)`;
        }
    }
};
</script>

<style scoped>

.title{
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 16px;
}

.conversao-card {
    width: 620px;
    height: 230px;
    border-radius: 12px;

}

.conversao-container{
  border: 1px solid #EEEEEE;
  border-radius: 8px;
}

.modalidade-item {
    display: flex;
    flex-direction: column;
    padding: 10px;
    align-items: center;
}

.grafico-circular {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
}

.grafico-center {
    width: 60px;
    height: 60px;
    border-radius: 50%;
    background: white;
    display: flex;
    align-items: center;
    justify-content: center;
}

.percentual-texto {
    color: #2A2E33;
    font-family: Plus Jakarta Sans;
    font-weight: 400;
    font-style: Regular;
    font-size: 16px;
    line-height: 140%;
}

.modalidade-nome {
    font-size: 14px;
    font-weight: 600;
    color: #666;
}
</style>
