<template>
  <h1>Home</h1>
  <h3>{{ message }}</h3>
</template>

<script>
const homeMixin = {
  created() {
    this.init();
  },
  methods: {
    init() {
      console.log('Init home!');
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
      counter: 1,
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
