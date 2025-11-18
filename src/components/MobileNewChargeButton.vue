<template>
  <div class="mobile-new-charge-button-container">
    <button class="new-charge-button">
      <span>Nova cobrança</span>
      <div class="plus-icon">
        <IconPlus />
      </div>
    </button>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import IconPlus from './icons/IconPlus.vue';

export default defineComponent({
  name: 'MobileNewChargeButton',
  components: {
    IconPlus
  }
});
</script>

<style scoped>
.mobile-new-charge-button-container {
  display: none;
  padding: 0 16px;
  margin-top: 16px;
  width: 100%;
}

@media (max-width: 768px) {
  .mobile-new-charge-button-container {
    display: block;
  }
}

.new-charge-button {
  width: 100%;
  height: 56px;
  border-radius: 28px;
  background: linear-gradient(180deg, #2A2E33 0%, #1A1D21 100%);
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  color: white;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 12px 0 24px;
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-weight: 600;
  font-size: 16px;
  border: 3px solid #2A2E3324
}

.plus-icon {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.plus-icon :deep(svg) {
  width: 26px;
  height: 26px;
}
</style>
