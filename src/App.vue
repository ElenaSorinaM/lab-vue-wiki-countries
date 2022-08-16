<template>
<Navbar />

<!-- Container -->

      <div class="container">
        <!-- Bootstrap row wrapper div -->
        <div class="row">
          <!-- Countries List (Bootstrap column) -->
          <div class="col-5" style="max-height: 90vh; overflow: scroll">
            <CountriesList />
          </div>

          <!-- Country Details (Bootstrap column) -->
          <div class="col-7">
            <CountryDetails />
          </div>
        </div>
      </div>
   

</template>

<script>
import Navbar from './components/Navbar.vue';
import CountriesList from './pages/CountriesList.vue';
import CountryDetails from './pages/CountryDetails.vue';
export default {
  components : {
    Navbar,
    CountriesList,
    CountryDetails
}
}
</script>

<style>
</style>
