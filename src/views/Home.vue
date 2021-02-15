<template>
  <section class="container">
    <HomeComponent message="Security, security, security!"/>
  </section>
</template>

<script>
import HomeComponent from '@/components/HomeComponent.vue'

export default {
  name: 'Home',
  components: {
    HomeComponent
  }
}
</script>
