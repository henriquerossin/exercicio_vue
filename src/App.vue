<template>
  <div id="app" class="container">
    <Cabecalho />
    <Calculadora />
  </div>
</template>

<script setup>
import Cabecalho from './components/Cabecalho.vue';
import Calculadora from './components/Calculadora.vue';
</script>

<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}

.container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
}
</style>
