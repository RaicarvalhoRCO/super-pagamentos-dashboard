<template>
    <VRow>
        <VCol v-for="status in statusList" :key="status.tipo" cols="12" sm="6" md="3">
            <VCard class="status-card pa-4">
                <div class="d-flex justify-space-between align-center mb-2">
                    <h4 class="text-subtitle-2 font-weight-medium">{{ status.tipo }}</h4>
                    <VIcon size="small">mdi-percent</VIcon>
                </div>
                <div class="valor-principal mb-1">{{ status.valor }}</div>
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
    border-radius: 12px;
    border: 1px solid #e0e0e0;
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
}

.cobrancas {
    font-weight: 500;
}

.percentual {
    font-weight: 600;
}
</style>
