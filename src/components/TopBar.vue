<template>
    <header class="topbar d-flex align-items-center justify-content-between p-3">
        <img src="/src/assets/logo.png" alt="Logo" class="logo">
        <div class="super_topbar d-flex gap-2">
            <span>Super central de gestão</span>
            <img src="/src/assets/super_gestao_icon.png" alt="">
        </div>
        <div class="user-info d-flex align-items-center">
            <div class="icons d-flex align-items-center ms-3">
                <div class="d-flex gap-4 mx-4">
                    <IconCircle />
                    <IconSettings />
                    <IconBellBlack />
                </div>
            </div>
            <div class="d-flex gap-2 align-items-center">
                <div class="avatar">AP</div>
                <div class="d-flex flex-column align-items-start">
                    <span class="user-name mb-1">Empresarial</span>
                    <span class="company-name">Astra Pagamentos</span>
                </div>
                <i class="bi bi-chevron-down"></i>
            </div>
        </div>
    </header>
</template>

<script>
import IconCircle from './icons/IconCircle.vue';
import IconSettings from './icons/IconConfiguracoes.vue';
import IconBellBlack from './icons/IconBellBlack.vue';

export default {
    name: 'TopBar',
    components: {
        IconCircle,
        IconBellBlack,
        IconSettings,
    },
};
</script>

<style scoped>
.topbar {
    background-color: #fff;
    border-bottom: 1px solid #ddd;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    z-index: 1000;
}

.user-name {
    font-family: Plus Jakarta Sans;
    font-weight: 600;
    font-size: 12px;
    line-height: 100%;
}

.logo {
    cursor: pointer;
    padding-left: 16px;
}

.super_topbar {
    font-family: Plus Jakarta Sans;
    font-weight: 700;
    font-size: 20px;
    line-height: 100%;
    margin-right: 45%;
    @media (max-width: 1400px) {
      margin-right: 25%;
    }
}


.avatar {
    width: 36px;
    height: 36px;
    border-radius: 50%;
    background-color: #0641FC;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 0.9rem;
    font-weight: bold;
}

.icons i {
    cursor: pointer;
    color: #000;
}

.company-name {
    font-family: Plus Jakarta Sans;
    font-weight: 600;
    font-size: 12px;
    line-height: 100%;
    color: #86898B;
}

@media (max-width: 768px) {
    .topbar {
        display: none !important;
    }
}
</style>
