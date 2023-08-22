<template>
    
    <select v-model="operacao">
        <option value="soma">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
    </select>

</template>

<script setup> 

    import { ref } from 'vue';
    const operacao = ref('soma');

</script>
