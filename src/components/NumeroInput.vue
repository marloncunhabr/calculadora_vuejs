<template>

    <input v-model.number="valor" type="number" />
    
</template>


<script setup>

    import { ref } from 'vue';
    const valor = ref(0);

</script>