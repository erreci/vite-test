<template>
    <div class="about-container">
        <h1>Ciao {{ id }}</h1>
        <p>We are a leading company in our industry, with a strong commitment to providing high-quality products and services to our customers. Our team is made up of experienced professionals who are passionate about what they do and are dedicated to delivering the best results.</p>
        <img src="https://via.placeholder.com/350" alt="Placeholder image">
    </div>

</template>

<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();
const id = route.params.id;
</script>


<style scoped>
.about-container {
    padding: 20px;
    text-align: center;
}

h1 {
    margin-bottom: 20px;
}

img {
    margin-top: 20px;
    max-width: 100%;
}
</style>