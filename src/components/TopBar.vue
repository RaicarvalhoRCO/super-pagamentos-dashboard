<template>
    <header class="topbar d-flex align-items-center justify-content-between p-3">
        <img src="/src/assets/logo.png" alt="Logo">
        <div class="super_topbar d-flex gap-2">
            <span>Super central de gestão</span>
            <img src="/src/assets/super_gestao_icon.png" alt="">
        </div>
        <div class="user-info d-flex align-items-center">
            <div class="icons d-flex align-items-center ms-3">
                <div class="d-flex gap-4 mx-4">
                    <IconCircle />
                    <IconSettings />
                    <IconBell />
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
import IconBell from './icons/IconBell.vue';
import IconSettings from './icons/IconSettings.vue';

export default {
    name: 'TopBar',
    components: {
        IconCircle,
        IconBell,
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
    font-size: 1.5rem;
    font-weight: bold;
}

.super_topbar {
    font-family: Plus Jakarta Sans;
    font-weight: 700;
    font-size: 20px;
    line-height: 100%;
    margin-right: 45%;
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
</style>