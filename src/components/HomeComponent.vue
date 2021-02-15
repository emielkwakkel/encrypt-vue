<template>
  <h1>Home</h1>
  <h3>{{ message }}</h3>
</template>

<script>
const encrypt = {
  created() {
    this.hello2();
  },
  methods: {
    hello2() {
      console.log('Init home!');
    },
  }
};

export default {
  name: 'HomeComponent',
  props: {
    message: String
  },
  mixins: [encrypt],
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
