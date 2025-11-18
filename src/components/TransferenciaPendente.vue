  <template>
  <VCard class="transferencia-pendente">
    <VCardText class="d-flex align-center justify-space-between">
      <div class="d-flex align-center">
        <div class="icon-container">
          <VIcon icon="mdi-arrow-up" color="black" size="24" />
          <div class="warning-badge">
            <VIcon icon="mdi-exclamation" color="black" size="12" />
          </div>
        </div>
        <div class="ml-4">
          <div class="title">Solicitação de transferência pendente</div>
          <div class="subtitle">
            A transação no valor de R$ 29.119,19 está aguardando a sua aprovação.
          </div>
        </div>
      </div>
      <VBtn color="primary" variant="flat" class="autorizar-btn">
        Autorizar transferência
        <VIcon icon="mdi-arrow-right" class="ml-2" size="20" />
      </VBtn>
    </VCardText>
  </VCard>
</template>

<script>
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'TransferenciaPendente',
});
</script>

<style scoped>
.transferencia-pendente {
  background-color: white;
  border-radius: 32px;
  box-shadow: none;
}

.icon-container {
  position: relative;
  width: 48px;
  height: 48px;
  background-color: #E6E3DC;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
}

.warning-badge {
  position: absolute;
  bottom: -2px;
  right: -2px;
  width: 20px;
  height: 20px;
  background-color: #F97316;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  border: 2px solid #F5F7FA;
}

.title {
  font-size: 16px !important;
  color: #2A2E33;
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 16px;
}

.subtitle {
  font-size: 12px !important;
  color: #86898B;
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 16px;
}

.autorizar-btn {
  background-color: #2563EB !important;
  color: white;
  text-transform: none;
  font-family: Plus Jakarta Sans;
  font-weight: 500;
  font-size: 16px;
  padding: 12px 24px;
  border-radius: 32px;
  letter-spacing: 0;
  height: 46px !important;
}

.autorizar-btn:hover {
  background-color: #1D4ED8 !important;
}

@media (max-width: 960px) {
  .transferencia-pendente :deep(.v-card-text) {
    flex-direction: column;
    align-items: flex-start !important;
    gap: 16px;
  }

  .autorizar-btn {
    width: 100%;
  }
}
</style>
