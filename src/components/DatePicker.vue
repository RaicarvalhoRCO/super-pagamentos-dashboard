<template>
  <div class="custom-date-picker">
    <VMenu v-model="menu" :close-on-content-click="false" offset-y>
      <template v-slot:activator="{ props }">
        <div class="date-display" v-bind="props">
          <span class="date-text">{{ formattedDate }}</span>
          <svg width="12" height="8" viewBox="0 0 12 8" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M1 1.5L6 6.5L11 1.5" stroke="#666666" stroke-width="1.5" stroke-linecap="round"
              stroke-linejoin="round" />
          </svg>
        </div>
      </template>
      <VDatePicker v-model="internalDate" @update:model-value="updateDate" />
    </VMenu>
  </div>
</template>

<script>
export default {
  name: 'DatePicker',
  props: {
    modelValue: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      menu: false,
      internalDate: null
    };
  },
  computed: {
    formattedDate() {
      if (!this.modelValue) return 'DD-MM-YYYY';
      const [year, month, day] = this.modelValue.split('-');
      return `${day}-${month}-${year}`;
    }
  },
  watch: {
    modelValue: {
      immediate: true,
      handler(newVal) {
        if (newVal) {
          this.internalDate = new Date(newVal);
        }
      }
    }
  },
  methods: {
    updateDate(date) {
      if (date) {
        const year = date.getFullYear();
        const month = String(date.getMonth() + 1).padStart(2, '0');
        const day = String(date.getDate()).padStart(2, '0');
        this.$emit('update:modelValue', `${year}-${month}-${day}`);
      }
      this.menu = false;
    }
  }
};
</script>

<style scoped>
.custom-date-picker {
  display: inline-block;
}

.date-display {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  user-select: none;
  padding: 2px 4px;
}

.date-text {
  font-family: 'Plus Jakarta Sans', sans-serif;
  font-weight: 600;
  font-size: 14px;
  color: #1A1A1A;
}

.date-display svg {
  flex-shrink: 0;
}

</style>
