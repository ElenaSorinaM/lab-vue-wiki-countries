<template>
  <div class="list-group">
              <div class="list-group-item list-group-item-action" 
              v-for="country in countries"
              @click="showCountry(country)"
              :key="country.id">
                <img :src='`https://flagpedia.net/data/flags/icon/72x54/${country.alpha2Code?.toLowerCase()}.png`' />
                <p>{{country.name.official}}</p>
              </div>
            
            </div>
</template>

<script>
import { useCountryStore } from '../components/stores/country';
export default {
    setup() {
    const country = useCountryStore();
    return { country };
  },
    data () {
        return {
           countries: [], 
        };
    },
    methods: {
        async getCountries() {
            const res = await fetch ('https://ih-countries-api.herokuapp.com/countries');
            const finalRes = await res.json();
            this.countries = finalRes;
        },
    
    showCountry(country) {
        this.country.officialName = country.name.official;
        this.country.capital = country.capital[0];
        this.country.borders = country.borders;
        this.country.code = country.alpha3Code;
        this.country.area = country.area;
        this.country.flag = country.alpha2Code;
    }, 
    },
    mounted() {
        this.getCountries();
    },
};
</script>

<style>

</style>