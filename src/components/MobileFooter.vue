<template>
  <footer class="mobile-footer">
    <div class="footer-content">
      <button class="footer-item">
        <IconSimule />
        <span>Simule</span>
      </button>
      <button class="footer-item">
        <IconCobrancas />
        <span>Cobranças</span>
      </button>
      <div class="fab-placeholder"></div>
      <button class="footer-item">
        <IconCarteira />
        <span>Carteira</span>
      </button>
      <button class="footer-item">
        <IconMenu />
        <span>Menu</span>
      </button>
    </div>
    <div class="fab-container">
      <button class="fab">
        <IconPlusFooter />
      </button>
    </div>
  </footer>
</template>

<script>
import { defineComponent } from 'vue';
import IconSimule from './icons/IconSimule.vue';
import IconCobrancas from './icons/IconCobrancas.vue';
import IconCarteira from './icons/IconCarteira.vue';
import IconMenu from './icons/IconMenu.vue';
import IconPlusFooter from './icons/IconPlusFooter.vue';

export default defineComponent({
  name: 'MobileFooter',
  components: {
    IconSimule,
    IconCobrancas,
    IconCarteira,
    IconMenu,
    IconPlusFooter
  }
});
</script>

<style scoped>
.mobile-footer {
  display: none;
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 80px;
  background-color: white;
  border-top: 1px solid #E5E7EB;
  z-index: 1000;
}

@media (max-width: 768px) {
  .mobile-footer {
    display: block;
  }
}

.footer-content {
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 100%;
  padding: 0 16px;
}

.footer-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  background: none;
  border: none;
  color: #86898B;
  font-size: 12px;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-weight: 500;
  gap: 4px;
}

.footer-item :deep(svg path) {
  stroke: #86898B;
}

.footer-item svg {
  height: 24px;
}

.fab-placeholder {
  width: 64px;
}

.fab-container {
  position: absolute;
  top: -32px;
  left: 50%;
  transform: translateX(-50%);
  width: 64px;
  height: 80px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

.fab {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  background-color: #0641FC;
  border: 4px solid white;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.15);
}

.fab-container::after {
  content: '';
  display: block;
  width: 6px;
  height: 6px;
  background-color: #0641FC;
  border-radius: 50%;
  margin-top: 12px;
}
</style>
