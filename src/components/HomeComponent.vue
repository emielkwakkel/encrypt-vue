<template>
  <h1>Home</h1>
  <div class="card">
    <div class="card-body">
      <h3>{{ message }}</h3>
      <p v-if="info">
        Eur: {{info.EUR.rate}}<br/>
        Usd: {{info.USD.rate}}
      </p>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
const homeMixin = {
  created() {
    this.init();
  },
  methods: {
    init() {
      axios
        .get('https://api.coindesk.com/v1/bpi/currentprice.json')
        .then(response => (this.info = response.data.bpi))
    },
  }
};

export default {
  name: 'HomeComponent',
  props: {
    message: String
  },
  mixins: [homeMixin],
  data() {
    return {
      info: null
    }
  }
}
</script>

