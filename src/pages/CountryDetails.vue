<template>
  <div v-if="store.currentCountry.capital">
    <img
      v-bind:src="`https://flagpedia.net/data/flags/icon/72x54/
${store.currentCountry.alpha2Code.toLowerCase()}.png`"
      alt="country flag"
      style="width: 300px"
    />
    <h1>{{ store.currentCountry.name.common }}</h1>
    <table class="table">
      <thead></thead>
      <tbody>
        <tr>
          <td style="width: 30%">Capital</td>
          <td>{{ store.currentCountry.capital[0] }}</td>
        </tr>
        <tr>
          <td>Area</td>
          <td>{{ store.currentCountry.area }} km <sup>2</sup></td>
        </tr>
        <tr>
          <td>Borders</td>
          <td>
            <ul>
              <li v-for="border in store.currentCountry.borders">
                <a href="/">{{ border }}</a>
              </li>
            </ul>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
import { useCountryStore } from "../stores/country";
const store = useCountryStore();
</script>

<style></style>
