<template>
  <h1>Encrypt</h1>
  <input v-model="password" type="password" /><br>
  <textarea v-model="content" /><br>
  <button v-if="state === 'encrypt'" @click="encrypt(password, content)">Encrypt</button>
  <button v-if="state === 'decrypt'" @click="decrypt(password, content)">Decrypt</button>
</template>

<script>
import CryptoJS from 'crypto-js'
const encrypt = {
  methods: {
    encrypt(password, content) {
      this.state = 'decrypt';
      this.content = CryptoJS.AES
        .encrypt(content, password)
        .toString();
    },
    decrypt(password, content) {
      this.state = 'encrypt';
      this.content = CryptoJS.AES
        .decrypt(content, password)
        .toString(CryptoJS.enc.Utf8);
    },
  }
};

export default {
  name: 'EncryptForm',
  mixins: [encrypt],
  data() {
    return {
      password: '',
      content: '',
      state: 'encrypt'
    }
  }
}
</script>
