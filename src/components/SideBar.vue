<template>
    <aside class="sidebar d-flex flex-column">
        <nav>
            <ul class="nav flex-column">
                <li class="nav-item">
                    <a class="nav-link active" href="#">Dashboard</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Clientes</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Cobranças</a>
                </li>
            </ul>
        </nav>
    </aside>
</template>

<script>
export default {
    name: 'SideBar',
};
</script>

<style scoped>
.sidebar {
    background-color: #f8f9fa;
    height: 100vh;
    width: 250px;
    border-right: 1px solid #ddd;
    padding-top: 64px;
}

.nav-link {
    color: #000;
    font-weight: 500;
}

.nav-link.active {
    color: #007bff;
}
</style>