<script setup>
import { ref } from "vue";
const pessoas = ref("");
const preço = ref("");
const gorgeta = ref("");
</script>
<template>
  <div class="outer">
    <h1>Calculadora de Gorjeta</h1>
    <div class="inputs">
      <div>
        <input type="text" v-model="preço" placeholder="Valor da conta" />
      </div>

      <select name="Qualidade de serviço" id="asd" v-model="gorgeta">
        <option value="" disable>Porcentagem</option>
        <option value="5">5%</option>
        <option value="10">10%</option>
        <option value="15">15%</option>
        <option value="20">20%</option>
        <option value="25">25%</option>
      </select>
      <div>
      <input type="text" placeholder="Quantidade de amigos" v-model="pessoas" />
      </div>

      <p>
        Valor para cada um pagar: R$
        {{ (preço * (1 + gorgeta / 100)) / pessoas }}
      </p>
    </div>
  </div>
</template>
