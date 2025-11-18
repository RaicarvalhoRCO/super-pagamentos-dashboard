<template>
    <VCard class="conversao-card pa-6">
        <h3 class="text-h6 font-weight-bold mb-6">Conversão por modalidade</h3>
        <VRow>
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
                { nome: 'Débito', percentual: 95, cor: '#9D5CFF' },
                { nome: 'Boleto', percentual: 42, cor: '#C4B5FD' },
                { nome: 'Pix', percentual: 98, cor: '#E0E7FF' }
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
.conversao-card {
    border-radius: 12px;
}

.modalidade-item {
    display: flex;
    flex-direction: column;
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
    font-size: 16px;
    font-weight: 700;
    color: #000;
}

.modalidade-nome {
    font-size: 14px;
    font-weight: 600;
    color: #666;
}
</style>
