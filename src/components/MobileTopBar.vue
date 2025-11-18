<template>
    <header class="mobile-topbar">
        <div class="top-section d-flex justify-content-between align-items-center p-3">
            <div class="user-info d-flex align-items-center gap-2 p-2">
                <div class="avatar">
                    <img src="/src/assets/super_avatar.png" alt="Logo">
                </div>
                <div class="d-flex flex-column align-items-start">
                    <span class="user-name">Empresarial</span>
                    <span class="company-name">Astra Pagamentos</span>
                </div>
                <i class="bi bi-chevron-down"></i>
            </div>
            <div class="notification-icon">
                <IconBell color="white" />
            </div>
        </div>
        <div class="faturamento-section p-3">
            <div class="faturamento-title">Faturamento</div>
            <div class="d-flex justify-content-between align-items-center">
                <span class="faturamento-valor">R$ {{ formatarValor(faturamento) }}</span>
                <div class="icon-circle">
                    <i class="bi bi-eye"></i>
                </div>

            </div>
        </div>
        <div class="carteira-link p-3 d-flex justify-content-between align-items-center">
            <span>Ir para a carteira</span>
            <i class="bi bi-chevron-right"></i>
        </div>
    </header>
</template>

<script>
import { defineComponent } from 'vue';
import IconBell from './icons/IconBell.vue';

export default defineComponent({
    name: 'MobileTopBar',
    components: {
        IconBell,
    },
    data() {
        return {
            faturamento: 1249651.14,
        };
    },
    methods: {
        formatarValor(valor) {
            return valor.toLocaleString('pt-BR', { minimumFractionDigits: 2, maximumFractionDigits: 2 });
        },
    }
});
</script>

<style scoped>
.mobile-topbar {
    display: none;
    background-color: #0641FC;
    color: white;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
    border-bottom-left-radius: 24px;
    border-bottom-right-radius: 24px;
}

@media (max-width: 768px) {
    .mobile-topbar {
        display: block;
    }
}


.icon-circle {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  background-color: #3364FF;
  display: flex;
  align-items: center;
  margin-right: 5px;
  justify-content: center;
}

.user-info {
    background-color: white;
    color: black;
    border-radius: 32px;
}

.avatar {
    width: 32px;
    height: 32px;
    border-radius: 50%;
    background-color: #000;
    display: flex;
    align-items: center;
    justify-content: center;
}

.avatar img {
    width: 32px;
    height: 32px;
}

.user-name {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 700;
    font-size: 12px;
}

.company-name {
    font-family: 'Plus Jakarta Sans', sans-serif;
    font-weight: 500;
    font-size: 10px;
    color: #86898B;
}

.faturamento-title {
    font-size: 14px;
    font-weight: 500;
    opacity: 0.8;
}

.faturamento-valor {
    font-size: 28px;
    font-weight: 700;
}

.carteira-link {
    border-top: 1px solid rgba(255, 255, 255, 0.2);
    font-size: 14px;
    font-weight: 600;
}

.top-section{
    margin-right: 10px;
}

</style>
