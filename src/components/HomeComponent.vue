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

