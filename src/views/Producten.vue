<template>
    <div class="producten">
        <h1>Producten</h1>
        <div class="producten-lijst">
            <div class="product-kaart"
                 v-for="product of producten"
                 :key="product.id"
            >
                <header class="product-header">
                    {{product.naam}}
                </header>
                <figure class="img-container">
                    <img :src="maakAfbeeldingUrl(product)" :alt="`Afbeelding van ${product.naam}`">
                </figure>
                <footer class="product-prijs">
                    &euro;{{product.prijs}}
                </footer>
            </div>
        </div>
    </div>
</template>

<script>
// @ is een alias voor de rootmap (src)
// Destructuring wordt gebruikt om variabelen te maken
// van de eigenschappen van het geëxporteerde object
import {producten,categories} from '@/producten.js'

export default {
    data() {
        return {
            // waarde van eigenschappen komt uit geïmporteerde variabelen
            producten,
            // dit is eigenlijk producten: producten
            categories
        }
    },
    methods: {
        maakAfbeeldingURL(product) {
            
        }
    }
}
</script>

<style scoped>
    .producten {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding-top: 5rem;
    }

    h1 {
        font-size: 7rem;
        color: #40b782;
    }
</style>
