<template>
  <div class="container">
    <div class="row">
      <div class="col">
        <currency-table :rates=currencies></currency-table>
      </div>
    </div>   
  </div>
</template>

<script>
  import axios from 'axios';
  import CurrencyTable from './components/CurrencyTable.vue';

  export default {
    data: () => ({
      currencies: null
    }),
    mounted: function() {
      axios
        .get('http://api.nbp.pl/api/exchangerates/tables/a')
        .then((result) => {
            this.currencies = result.data[0].rates;
        })
        .catch(() => {
          console.log('Error while connecting to NBP API');
        })
    },
    components: {
        CurrencyTable
    }
  }
</script>
