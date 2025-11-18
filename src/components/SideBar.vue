<template>
  <aside class="sidebar d-flex flex-column">
    <nav class="flex-grow-1">
      <ul class="nav flex-column">
        <li class="nav-section">Menu</li>
        <li class="nav-item" v-for="item in menuItems" :key="item.name" :class="{ active: activeItem === item.name }"
          @click="setActive(item.name)">
          <div class="icon-circle">
            <component :is="item.icon" class="icon" />
          </div>
          <span class="nav-text">{{ item.name }}</span>
        </li>
        <li class="nav-section">GERAL</li>
        <li class="nav-item" v-for="item in generalItems" :key="item.name" :class="{ active: activeItem === item.name }"
          @click="setActive(item.name)">
          <div class="icon-circle">
            <component :is="item.icon" class="icon" />
          </div>
          <span class="nav-text">{{ item.name }}</span>
        </li>
      </ul>
    </nav>
    <div class="logout-section w-100 d-flex align-center justify-center">
      <div class="nav-item logout-item d-flex">
        <span class="nav-text">Deslogar da conta</span>
          <IconLogout class="icon" />
      </div>
    </div>
  </aside>
</template>

<script>
import IconDashboard from './icons/IconDashboard.vue';
import IconClientes from './icons/IconClientes.vue';
import IconCobrancas from './icons/IconCobrancas.vue';
import IconCarteira from './icons/IconCarteira.vue';
import IconVendedores from './icons/IconVendedores.vue';
import IconAntecipacoes from './icons/IconAntecipacoes.vue';
import IconGestao from './icons/IconGestao.vue';
import IconIntegracoes from './icons/IconIntegracoes.vue';
import IconConfiguracoes from './icons/IconConfiguracoes.vue';
import IconPerfil from './icons/IconPerfil.vue';
import IconLogout from './icons/IconLogout.vue';

export default {
  name: 'SideBar',
  components: {
    IconLogout
  },
  data() {
    return {
      activeItem: 'Dashboard',
      menuItems: [
        { name: 'Dashboard', icon: IconDashboard },
        { name: 'Clientes', icon: IconClientes },
        { name: 'Cobranças', icon: IconCobrancas },
        { name: 'Carteira', icon: IconCarteira },
        { name: 'Vendedores', icon: IconVendedores },
        { name: 'Antecipações', icon: IconAntecipacoes },
        { name: 'Gestão', icon: IconGestao },
        { name: 'Integrações', icon: IconIntegracoes },
      ],
      generalItems: [
        { name: 'Configurações', icon: IconConfiguracoes },
        { name: 'Perfil', icon: IconPerfil },
      ],
    };
  },
  methods: {
    setActive(item) {
      this.activeItem = item;
    }
  },
};
</script>

<style scoped>
.sidebar {
  background-color: #f8f9fa;
  height: 100vh;
  width: 250px;
  border-right: 1px solid #ddd;
  padding-top: 64px;
  position: fixed;
}

.nav {
  list-style: none;
  padding: 0;
  margin: 0;
}

.nav-section {
  color: #86898B;
  padding: 0px 32px;
  text-transform: uppercase;
  margin: 16px 0 8px 0px;
  font-family: Plus Jakarta Sans;
  font-weight: 700;
  font-size: 12px;
  letter-spacing: 2px;
}

.nav-item {
  display: flex;
  align-items: center;
  padding: 8px 32px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.nav-item.active .icon-circle {
  background-color: #D1DCFF;
}

.nav-item:hover {
  background-color: #f1f1f1;
}

.icon-circle {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  background-color: #F5F5F5;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-right: 12px;
  transition: background-color 0.3s;
}

.icon {
  width: 20px;
  height: 20px;
  transition: fill 0.3s;
}

.nav-text {
  font-size: 0.9rem;
  font-weight: 500;
  color: #000;
}

.logout-section {
  height: 46px;
  margin-bottom: 24px;
}
.logout-item{
  height: 46px;
  width: 230px;
  border: 1px solid #D9D9D9;
  border-radius: 32px;
  background-color: white;
}

.logout-item svg{
  margin-left: 10px;
}

</style>
