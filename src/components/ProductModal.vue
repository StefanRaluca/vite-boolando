<script>
export default {
    props: {
        product: {
            type: Object,
            required: true
        }
    },
    methods: {
        // Metodo per chiudere modale
        closeModal() {
            this.$emit('closeModal');
        }
    }
}
</script>


<template>
    <div class="product-modal" v-if="product">
        <div class="modal">
            <!-- x  chiudere la modale -->
            <span class="close" @click="closeModal"><i class="fa fa-close" aria-hidden="true"></i></span>
            <!-- <h2>{{ product.title }}</h2> -->
            <div class="container_left">
                <img :src="product.imgSrc" alt="">
                <img :src="product.imgSrc.replace('.webp', 'b.webp')" alt="">
            </div>
            <div class="container_right">
                <h3>{{ product.title }}</h3>
                <h2>{{ product.brand }}</h2>
                <div class="price_before">{{ product.priceBefore }}</div>
                <div style="color: green">{{ product.sostenibilita }} </div>
                <div class="discount_modale" v-if="product.discount !== null">{{ product.discount }}</div>
                <strong> Price now : {{ product.priceNow }}</strong>
                <p> {{ product.hearts }}</p>

            </div>
        </div>
    </div>
</template>


<style scoped>
.fa-close {
    cursor: pointer;
    font-size: 1.5rem;
    position: absolute;
    top: 0px;
    left: 0px;
}


img {
    margin: 15px;
    width: 150px;
}

.modal {
    background-color: lightgrey;
    padding: 35px;
    display: flex;
    position: relative;
}

.container_right h2 {
    text-decoration: underline;

}

.discount_modale {
    color: red;
    margin-top: 10px;
    margin-bottom: 10px;
}
</style>