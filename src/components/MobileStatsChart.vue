<template>
    <div class="mobile-stats-chart-container">
        <VCard class="stats-card pa-4" elevation="0">
            <div class="d-flex justify-space-between align-start p-2">
                <div>
                    <h4 class="card-title">Estatísticas do período</h4>
                    <span class="total-value">R$ {{ formatarValor(total) }}</span>
                    <div class="growth">
                        <VIcon size="x-small" color="#34A853">mdi-arrow-up</VIcon>
                        <span>{{ crescimento }}%</span>
                    </div>
                </div>
                <button class="filter-button">
                    <IconFilter />
                </button>
            </div>

            <div class="chart-container">
                <div v-for="(item, index) in chartData" :key="index" class="bar-wrapper">
                    <div class="bar" :style="{ height: item.height + '%', background: getBarColor(item.height) }"></div>
                </div>
            </div>

            <div class="date-range">
                De 15 de Dez. de 2024 à 07 de Fev. de 2025
            </div>
        </VCard>
    </div>
</template>

<script>
import { defineComponent } from 'vue';
import IconFilter from './icons/IconFilter.vue';

export default defineComponent({
    name: 'MobileStatsChart',
    components: {
        IconFilter
    },
    data() {
        return {
            total: 760102.06,
            crescimento: 123.9,
            chartData: Array.from({ length: 28 }, () => ({
                height: Math.random() * 80 + 5, // Altura entre 5% e 85%
            })),
        };
    },
    methods: {
        formatarValor(valor) {
            return valor.toLocaleString('pt-BR', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
        },
        getBarColor(height) {
            if (height > 60) return 'linear-gradient(180deg, #34C759 0%, #34A853 100%)';
            if (height > 30) return 'linear-gradient(180deg, #4C82F7 0%, #0641FC 100%)';
            return '#0641FC';
        }
    }
});
</script>

<style scoped>
.mobile-stats-chart-container {
    display: none;
    padding: 0 16px;
    margin-top: 24px;
    width: 100%;
}

@media (max-width: 768px) {
    .mobile-stats-chart-container {
        display: block;
    }
}

.stats-card {
    border-radius: 24px;
    background-color: white;
}

.card-title {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 600;
    font-size: 16px;
    color: #2A2E33;
}

.total-value {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 700;
    font-size: 28px;
    color: #2A2E33;
    line-height: 1.2;
}

.growth {
    display: flex;
    align-items: center;
    gap: 4px;
    color: #34A853;
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 700;
    font-size: 14px;
}

.filter-button {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    border: 1px solid #E5E7EB;
    background-color: white;
    display: flex;
    align-items: center;
    justify-content: center;
}

.chart-container {
    height: 120px;
    display: flex;
    align-items: flex-end;
    gap: 6px;
    margin-top: 24px;
    padding: 0 8px;
}

.bar-wrapper {
    flex: 1;
    height: 100%;
    display: flex;
    align-items: flex-end;
}

.bar {
    width: 100%;
    border-radius: 4px;
}

.date-range {
    background-color: #F3F4F6;
    border-radius: 16px;
    padding: 8px 12px;
    text-align: center;
    font-size: 12px;
    color: #6B7280;
    margin-top: 16px;
    display: inline-block;
    width: 100%;
}
</style>
