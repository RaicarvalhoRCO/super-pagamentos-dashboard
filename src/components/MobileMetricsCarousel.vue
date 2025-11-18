<template>
    <div class="mobile-metrics-carousel-container">
        <div class="carousel">
            <VCard v-for="(metrica, index) in metrics" :key="index" class="metrica-card" elevation="0">
                <div class="metrica-label">{{ metrica.label }}</div>
                <div class="metrica-valor">
                    <div class="d-flex mr-2">
                        <div class="legenda-menor" :style="{ backgroundColor: metrica.color }"></div>
                        <div class="legenda-maior" :style="{ backgroundColor: metrica.color + '73' }"></div>
                    </div>
                    <div>{{ formatValue(metrica.value, metrica.type) }}</div>
                </div>
            </VCard>
        </div>
    </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'MobileMetricsCarousel',
    data() {
        return {
            metrics: [
                { label: 'Faturamento recebido', value: 245340.90, color: '#0641FC', type: 'currency' },
                { label: 'Faturamento previsto', value: 815210.24, color: '#9D5CFF', type: 'currency' },
                { label: 'Vendas pendentes', value: 192.30, color: '#FF9500', type: 'currency' },
                { label: 'Ticket médio', value: 192.30, color: '#B882FE', type: 'currency' },
                { label: 'Número de cobranças', value: 12349, color: '#2A2E33', type: 'number' }
            ]
        };
    },
    methods: {
        formatValue(value, type) {
            if (type === 'currency') {
                return 'R$ ' + value.toLocaleString('pt-BR', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
            }
            return value.toLocaleString('pt-BR');
        }
    }
});
</script>

<style scoped>
.mobile-metrics-carousel-container {
    display: none;
    margin-top: 24px;
}

@media (max-width: 768px) {
    .mobile-metrics-carousel-container {
        display: block;
    }
}

.carousel {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
    gap: 12px;
    padding: 0 16px;
    -ms-overflow-style: none;
    /* IE and Edge */
    scrollbar-width: none;
    /* Firefox */
}

.carousel::-webkit-scrollbar {
    display: none;
    /* Chrome, Safari, Opera*/
}

.metrica-card {
    flex: 0 0 240px;
    scroll-snap-align: start;
    border-radius: 16px;
    padding: 16px;
    background-color: white;
}

.metrica-label {
    font-size: 14px;
    color: #86898B;
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 500;
}

.metrica-valor {
    display: flex;
    align-items: center;
    font-size: 24px;
    font-weight: 700;
    color: #2A2E33;
    font-family: 'Plus Jakarta Sans', sans-serif;
    margin-top: 8px;
    gap: 8px;
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
    position: absolute;
    margin: -2px 4px;
}
</style>
