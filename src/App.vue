<script setup>
import { ref } from "vue";
const pessoas = ref("");
const preço = ref("");
const gorgeta = ref("");
</script>
<template>
  <div class="inputs">
    <input type="text" v-model="preço" placeholder="Valor da conta" />

    <select name="Qualidade de serviço" id="asd" v-model="gorgeta">
    <option value="" disable>Porcentagem</option>
      <option value="5">5%</option>
      <option value="10">10%</option>
      <option value="15">15%</option>
      <option value="20">20%</option>
      <option value="25">25%</option>
    </select>

    <input type="text" placeholder="Quantidade de amigos" v-model="pessoas" />

    <p>
      Valor para cada um pagar: R$ {{ (preço * (1 + gorgeta / 100)) / pessoas }}
    </p>
  </div>
</template>
