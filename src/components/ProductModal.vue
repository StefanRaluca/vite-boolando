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
            <span class="close" @click="closeModal">✖️</span>
            <h2>{{ product.title }}</h2>
            <p>{{ product.discount }}</p>

        </div>
    </div>
</template>


<style></style>