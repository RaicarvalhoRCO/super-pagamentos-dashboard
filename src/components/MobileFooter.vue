<template>
    <footer class="mobile-footer d-flex justify-content-around p-3">
        <button class="btn btn-link">
            <i class="bi bi-house"></i>
            <span>Dashboard</span>
        </button>
        <button class="btn btn-link">
            <i class="bi bi-wallet"></i>
            <span>Cobranças</span>
        </button>
        <button class="btn btn-link">
            <i class="bi bi-credit-card"></i>
            <span>Carteira</span>
        </button>
        <button class="btn btn-link">
            <i class="bi bi-menu-button"></i>
            <span>Menu</span>
        </button>
    </footer>
</template>

<script>
export default {
    name: 'MobileFooter',
};
</script>

<style scoped>
.mobile-footer {
    background-color: #fff;
    border-top: 1px solid #ddd;
    position: fixed;
    bottom: 0;
    width: 100%;
}

.btn-link {
    display: flex;
    flex-direction: column;
    align-items: center;
    color: #000;
}

.btn-link i {
    font-size: 1.5rem;
}

.btn-link span {
    font-size: 0.75rem;
}

/* Esconde o footer em telas maiores que 768px */
@media (min-width: 768px) {
    .mobile-footer {
        display: none !important;
    }
}
</style>