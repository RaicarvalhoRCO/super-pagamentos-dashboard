<template>
    <header class="topbar d-flex align-items-center justify-content-between p-3">
        <div class="logo">Super</div>
        <div class="user-info d-flex align-items-center">
            <span class="user-name">Empresarial</span>
            <img src="/path/to/avatar.png" alt="User Avatar" class="avatar ms-2" />
        </div>
    </header>
</template>

<script>
export default {
    name: 'TopBar',
};
</script>

<style scoped>
.topbar {
    background-color: #fff;
    border-bottom: 1px solid #ddd;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
}

.avatar {
    width: 32px;
    height: 32px;
    border-radius: 50%;
}
</style>