<template>
    <div class="producten">
        <h1>Producten</h1>
        <div class="producten-lijst">
            <!-- directive tag bij router-link verandert het gegenereerde element
                 naar het gekozen element(ipv standaar een a-element te worden) -->
            <router-link class="product-kaart"
                 v-for="product of producten"
                 :key="product.id"
                 :to="`producten/${product.id}`"
                 tag="div"
            >
                <header class="product-header">
                    {{product.naam}}
                </header>
                <figure class="img-container">
                    <img :src="maakAfbeeldingUrl(product)"
                         :alt="`Afbeelding van ${product.naam}`">
                    <figcaption class="product-prijs">
                        &euro;{{product.prijs}}
                    </figcaption>
                </figure>
            </router-link>
        </div>
    </div>
</template>

<script>
// @ is een alias voor de rootmap (src)
// Destructuring wordt gebruikt om variabelen te maken
// van de eigenschappen van het geëxporteerde object
import {categories} from '@/producten.js'
import axios from 'axios'

export default {
    data() {
        return {
            // waarde van eigenschappen komt uit geïmporteerde variabelen
            producten: [],
            // dit is eigenlijk producten: producten
            categories,
            // process.env geeft ons toegang tot omgevingsvariabelen van het project
            // de eigenschap BASE_URL wordt door Vue ingevuld met het absolute adres van de webapplicatie
            baseUrl: process.env.BASE_URL
        }
    },
    methods: {
        maakAfbeeldingUrl(product) {
            return `${this.baseUrl}producten/${product.categorie}/${product.afbeelding}`;
        }
    },
    async created() {
        try {
            const {data} = await axios.get("http://localhost:3333/producten");
            this.producten = data;
        } catch (ex) {
            console.log(ex);
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

    .product-kaart {
        text-align: center;
    }

    .producten-lijst {
        display: grid;
        width: 80%;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        column-gap: 5rem;
        row-gap: 5rem;
    }

    .img-container img {
        height: 250px;
    }
</style>
