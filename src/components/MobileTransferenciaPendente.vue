<template>
    <div class="mobile-transferencia-container">
        <VCard class="transferencia-card" elevation="0">
            <div class="d-flex align-center pl-3">
                <div class="icon-container">
                    <VIcon icon="mdi-arrow-up" color="black" size="24" />
                    <div class="warning-badge">
                        <VIcon icon="mdi-exclamation" color="white" size="12" />
                    </div>
                </div>
                <div class="ml-4">
                    <div class="title">Solicitação de transferência pendente</div>
                    <div class="subtitle">
                        A transação no valor de R$ 29.119,13 está aguardando a sua aprovação.
                    </div>
                </div>
            </div>
            <VBtn color="#0641FC" variant="flat" class="autorizar-btn mt-4" block>
                Autorizar transferência
                <VIcon icon="mdi-chevron-right" class="ml-2" size="20" />
            </VBtn>
        </VCard>
    </div>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
    name: 'MobileTransferenciaPendente',
});
</script>

<style scoped>
.mobile-transferencia-container {
    display: none;
    margin-top: 24px;
}

@media (max-width: 768px) {
    .mobile-transferencia-container {
        display: block;
    }
}

.transferencia-card {
    background-color: white;
    border-radius: 16px;
    padding-top: 16px;
}

.icon-container {
    position: relative;
    width: 48px;
    height: 48px;
    background-color: #F3F4F6;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-shrink: 0;
}

.warning-badge {
    position: absolute;
    bottom: -2px;
    right: -2px;
    width: 20px;
    height: 20px;
    background-color: #F97316;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    border: 2px solid white;
}

.title {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 600;
    font-size: 16px;
    color: #2A2E33;
}

.subtitle {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 500;
    font-size: 14px;
    color: #86898B;
    margin-top: 4px;
}

.autorizar-btn {
    background-color: #0641FC !important;
    color: white;
    text-transform: none;
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 600;
    font-size: 16px;
    border-radius: 0px 0px 16px 16px;
    height: 48px !important;
    justify-content: space-between;
    padding: 0 16px;
}
</style>
