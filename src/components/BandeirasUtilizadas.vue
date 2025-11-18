<template>
    <VCard class="bandeiras-card pa-6">
        <div class="d-flex justify-space-between align-center mb-6">
            <h3 class="text-h6 font-weight-bold">Bandeiras mais utilizadas</h3>
            <VIcon size="small">mdi-information-outline</VIcon>
        </div>

        <div class="grafico-barras">
            <div v-for="bandeira in bandeiras" :key="bandeira.nome" class="bandeira-item mb-4">
                <div class="d-flex justify-space-between align-center mb-2">
                    <img :src="bandeira.logo" :alt="bandeira.nome" class="bandeira-logo" />
                    <span class="bandeira-percentual">{{ bandeira.percentual }}%</span>
                </div>
                <div class="barra-progresso">
                    <div class="barra-preenchida"
                        :style="{ width: bandeira.percentual + '%', backgroundColor: bandeira.cor }"></div>
                </div>
            </div>
        </div>
    </VCard>
</template>

<script>
export default {
    name: 'BandeirasUtilizadas',
    data() {
        return {
            bandeiras: [
                { nome: 'VISA', logo: '/logos/visa.svg', percentual: 45, cor: '#1A1F71' },
                { nome: 'Mastercard', logo: '/logos/mastercard.svg', percentual: 38, cor: '#EB001B' },
                { nome: 'Elo', logo: '/logos/elo.svg', percentual: 25, cor: '#FFCB05' },
                { nome: 'Hipercard', logo: '/logos/hipercard.svg', percentual: 18, cor: '#EC1C24' },
                { nome: 'Amex', logo: '/logos/amex.svg', percentual: 12, cor: '#006FCF' },
                { nome: 'Google Pay', logo: '/logos/gpay.svg', percentual: 8, cor: '#4285F4' },
                { nome: 'Banricompras', logo: '/logos/banricompras.svg', percentual: 6, cor: '#00A859' },
                { nome: 'Apple Pay', logo: '/logos/applepay.svg', percentual: 5, cor: '#000000' },
                { nome: 'Cabal', logo: '/logos/cabal.svg', percentual: 3, cor: '#003DA5' }
            ]
        };
    }
};
</script>

<style scoped>
.bandeiras-card {
    border-radius: 12px;
}

.bandeira-item {
    width: 100%;
}

.bandeira-logo {
    height: 20px;
    width: auto;
}

.bandeira-percentual {
    font-size: 14px;
    font-weight: 600;
    color: #000;
}

.barra-progresso {
    width: 100%;
    height: 8px;
    background: #f0f0f0;
    border-radius: 4px;
    overflow: hidden;
}

.barra-preenchida {
    height: 100%;
    border-radius: 4px;
    transition: width 0.3s ease;
}
</style>
