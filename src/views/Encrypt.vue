<template>
  <section class="container">
    <h1>Encrypt</h1>
    <EncryptForm/>
  </section>
</template>
<script>
import EncryptForm from '@/components/EncryptForm.vue'

export default {
  name: 'Encrypt',
  components: {
    EncryptForm
  }
}
</script>
