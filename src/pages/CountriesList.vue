<template>
  <div class="list-group">
    <div
      class="list-group-item list-group-item-action"
      v-for="el in countries"
      @click="showCountry(el)"
    >
      <img
        :src="`https://flagpedia.net/data/flags/icon/72x54/
${el.alpha2Code.toLowerCase()}.png`"
      />
      <p>{{ el.name.common }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
import { useCountryStore } from "../stores/country";
const countryStore = useCountryStore();
const countries = ref(null);

async function getCountries() {
  const res = await fetch("https://ih-countries-api.herokuapp.com/countries");
  const finalRes = await res.json();
  countries.value = finalRes;
  countryStore.currentCountry = finalRes[0];
}

function showCountry(el) {
  countryStore.currentCountry = el;
}

getCountries();
</script>

<style></style>
