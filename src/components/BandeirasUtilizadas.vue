<template>
  <VCard class="bandeiras-card pa-6">
    <div class="d-flex align-center">
      <h3 class="mr-2 bandeiras-card-title mb-4">Bandeiras mais utilizadas</h3>
      <VIcon size="small" class="mb-3">mdi-information-outline</VIcon>
    </div>

    <div class="grafico-barras">
      <div v-for="bandeira in bandeiras" :key="bandeira.nome" class="bandeira-item">
        <div class="barra-vertical-container">
          <div class="barra-vertical" :style="{ height: bandeira.percentual + '%' }">
          </div>
        </div>
        <img :src="bandeira.logo" :alt="bandeira.nome" class="bandeira-logo" />
      </div>
    </div>
  </VCard>
</template>

<script>
import visaLogo from '/src/assets/flags/visa.png';
import mastercardLogo from '/src/assets/flags/mastercard.png';
import eloLogo from '/src/assets/flags/elo.png';
import hipercardLogo from '/src/assets/flags/hipercard.png';
import amexLogo from '/src/assets/flags/amex.png';
import gpayLogo from '/src/assets/flags/gpay.png';
import applepayLogo from '/src/assets/flags/apple.png';
import hiperLogo from '/src/assets/flags/hiper.png';
import samsungLogo from '/src/assets/flags/samsung.png';

export default {
  name: 'BandeirasUtilizadas',
  data() {
    return {
      bandeiras: [
        { nome: 'VISA', logo: visaLogo, percentual: 45 },
        { nome: 'Mastercard', logo: mastercardLogo, percentual: 38 },
        { nome: 'Elo', logo: eloLogo, percentual: 15 },
        { nome: 'Hipercard', logo: hipercardLogo, percentual: 10 },
        { nome: 'Amex', logo: amexLogo, percentual: 5 },
        { nome: 'Google Pay', logo: gpayLogo, percentual: 8 },
        { nome: 'Samsung Pay', logo: samsungLogo, percentual: 8 },
        { nome: 'Apple Pay', logo: applepayLogo, percentual: 15 },
        { nome: 'Hiper', logo: hiperLogo, percentual: 8 }
      ]
    };
  }
};
</script>

<style scoped>
.bandeiras-card {
  height: 230px;
  width: 630px;
  border-radius: 12px;
  padding: 10px 24px !important;
}

@media (max-width: 768px) {
  .bandeiras-card {
      margin-left: 0px !important;
  }
}

@media (max-width: 1300px) {
  .bandeiras-card {
      margin-left: 61%;
      width: 100%;
  }
}


.bandeiras-card-title{
  font-family: Plus Jakarta Sans;
  font-weight: 600;
  font-size: 16px;
}

.grafico-barras {
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  gap: 8px;
  border: 1px solid #EEEEEE;
  border-radius: 16px;
  height: 170px;
  @media (max-width: 768px) {
      gap: 0px;
}
}

.bandeira-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 12px;
  height: 150px;
  flex: 1;
}

.barra-vertical-container {
  width: 8px;
  background-color: #F5F5F5;
  height: 150px;
  display: flex;
  align-items: flex-end;
  justify-content: center;
}

.barra-vertical {
  width: 8px;
  border-radius: 32px;
  transition: height 0.3s ease;
  min-height: 4px;
  background-color: #0641FC;
}

.bandeira-logo {
  height: 24px;
  width: auto;
  object-fit: contain;
}
</style>
