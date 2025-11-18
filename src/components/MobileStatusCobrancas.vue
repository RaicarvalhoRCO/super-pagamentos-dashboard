<template>
    <div class="mobile-status-container">
        <VCard class="status-card pa-4" elevation="0">
            <VRow>
                <VCol v-for="(status, index) in statusList" :key="status.tipo" cols="6" class="status-item">
                    <div class="status-title">{{ status.tipo }}</div>
                    <div class="status-value">{{ status.valor }}</div>
                    <div class="d-flex align-center justify-space-between mt-1">
                        <span class="status-percentage" :style="{ color: status.cor }">{{ status.percentual }}</span>
                        <IconSparkline :path="status.sparkline" :color="status.cor" />
                    </div>
                </VCol>
            </VRow>
        </VCard>
    </div>
</template>

<script>
import { defineComponent } from 'vue';
import IconSparkline from './icons/IconSparkline.vue';

export default defineComponent({
    name: 'MobileStatusCobrancas',
    components: {
        IconSparkline
    },
    data() {
        return {
            statusList: [
                { tipo: 'Reembolsos', valor: 'R$ 8.260,10', percentual: '4,5%', cor: '#F97316', sparkline: 'M1 8.5L8.5 5L16 10L23.5 6L31 11.5L38.5 8L46 10.5' },
                { tipo: 'Chargebacks', valor: 'R$ 1.160,10', percentual: '0,5%', cor: '#EF4444', sparkline: 'M1 9.5L8.5 12L16 7L23.5 10L31 5L38.5 8.5L46 6' },
                { tipo: 'Cancelados', valor: 'R$ 3.120,60', percentual: '1,5%', cor: '#86898B', sparkline: 'M1 7L8.5 9.5L16 6L23.5 11L31 7.5L38.5 10L46 5' },
                { tipo: 'Não autorizado', valor: 'R$ 6.120,10', percentual: '0,5%', cor: '#EF4444', sparkline: 'M1 10L8.5 6.5L16 9L23.5 5.5L31 10.5L38.5 7L46_9' }
            ]
        };
    }
});
</script>

<style scoped>
.mobile-status-container {
    display: none;
    margin-top: 24px;
}

@media (max-width: 768px) {
    .mobile-status-container {
        display: block;
    }
}

.status-card {
    border-radius: 16px;
    background-color: white;
}

.status-item {
    padding: 12px;
}

.status-item:nth-child(1),
.status-item:nth-child(2) {
    border-bottom: 1px solid #F3F4F6;
}

.status-item:nth-child(1),
.status-item:nth-child(3) {
    border-right: 1px solid #F3F4F6;
}

.status-title {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 500;
    font-size: 14px;
    color: #86898B;
}

.status-value {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 700;
    font-size: 20px;
    color: #2A2E33;
    margin-top: 4px;
}

.status-percentage {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 600;
    font-size: 14px;
}
</style>
