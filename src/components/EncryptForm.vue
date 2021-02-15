<template>
  <div class="card">
    <div class="card-body">
      <label for="passwordFormControl"/>Password
      <input id="passwordFormControl" class="form-control" v-model="password" type="password" />
      <label class="pt-4" for="contentFormControl"/>Content
      <textarea id="contentFormControl" class="form-control" v-model="content" rows="6" /><br>
      <button v-if="state === 'encrypt'" class="btn col btn-success btn-primary" type="button" @click="encrypt(password, content)">Encrypt</button>
      <button v-if="state === 'decrypt'" class="btn col btn-danger btn-primary" type="button" @click="decrypt(password, content)">Decrypt</button>
    </div>
  </div>
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
