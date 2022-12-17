<template>
  <img src="#" alt="country flag" style="width: 300px" />
  <h1>{{ store?.currentCountry?.name?.common }}</h1>
  <table class="table">
    <thead></thead>
    <tbody>
      <tr>
        <td style="width: 30%">Capital</td>
        <td>{{ store?.currentCountry?.capital[0] }}</td>
      </tr>
      <tr>
        <td>Area</td>
        <td>{{ store?.currentCountry?.area }} km <sup>2</sup></td>
      </tr>
      <tr>
        <td>Borders</td>
        <td>
          <ul>
            <li>
              <a href="/">Borders</a>
            </li>
          </ul>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script setup>
import { useCountryStore } from "../stores/country";
const store = useCountryStore();
</script>

<style></style>
