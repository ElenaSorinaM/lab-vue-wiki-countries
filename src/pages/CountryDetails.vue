<template>
      <img 
      :src="`https://flagcdn.com/w320/${country.flag.toLowerCase()}.png`" 
      alt="country flag" style="width: 300px"/>
            <h1>{{country.name}}</h1>
            <table class="table">
              <thead></thead>
              <tbody>
                <tr>
                  <td style="width: 30%">Capital</td>
                  <td>{{country.capital}}</td>
                </tr>
                <tr>
                  <td>Area</td>
                  <td>
                    {{country.area}}<sup>2</sup>
                  </td>
                </tr>
                <tr>
                  <td>Borders</td>
                  <td>
                    <ul>
                      <li v-for="borders in country.borders"
                      :key="borders.id">
                        <a href="/" >{{ border }}</a>
                        </li>
                    </ul>  
                  </td>
                </tr>
              </tbody>
            </table>
</template>

<script>

import { useCountryStore } from '../components/stores/country';
export default {

    setup () {
        const country = useCountryStore();
        return { country }
    },
    mounted () {
        this.country
    }
}
</script>
