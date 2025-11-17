<template>
    <div class="main-dashboard">
        <div class="stats-cards d-flex flex-wrap">
            <div class="card m-2 p-3">
                <h5>Faturamento</h5>
                <p class="value">R$ 1.060.551,14</p>
            </div>
            <div class="card m-2 p-3">
                <h5>Faturamento Recebido</h5>
                <p class="value">R$ 245.340,90</p>
            </div>
            <!-- Adicione mais cards conforme necessário -->
        </div>
        <div class="charts mt-4">
            <div class="chart">
                <!-- Placeholder para gráfico de faturamento -->
                <p>Gráfico de faturamento</p>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'MainDashboard',
};
</script>

<style scoped>
.main-dashboard {
    padding: 20px;
}

.stats-cards {
    display: flex;
    flex-wrap: wrap;
}

.card {
    background-color: #fff;
    border: 1px solid #ddd;
    border-radius: 8px;
    width: 300px;
}

.value {
    font-size: 1.5rem;
    font-weight: bold;
}

.chart {
    background-color: #f8f9fa;
    border: 1px solid #ddd;
    border-radius: 8px;
    height: 300px;
}

@media (max-width: 768px) {
    .main-dashboard {
        padding: 10px;
    }

    .stats-cards {
        flex-direction: column;
        align-items: center;
    }

    .card {
        width: 100%;
        margin: 10px 0;
    }

    .chart {
        width: 100%;
        height: auto;
    }
}
</style>