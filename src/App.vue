<!-- index.vue -->
<template>
  <div>
      <h1 :class="{ highlight: inputText.length > 0 }">{{ title }}</h1>
      <p :style="{ color: inputText.length > 0 ? 'blue' : 'black' }">{{ message }}</p>
      <input v-model="inputText" type="text" placeholder="Masukkan Nama Anda">
      <button @click="updateName">Ubah Nama</button>
      <button @click="clearInput">Hapus</button>
      <p>{{ inputText }}</p>
  </div>
</template>

<script>
export default {
  data() {
      return {
          title: 'Selamat Datang',
          message: 'Ini Contoh Halaman Web Sederhana Saya',
          inputText: ''
      }
  },
  methods: {
      updateName() {
          this.inputText = 'Nama Saya ' + this.inputText;
      },
      clearInput() {
          this.inputText = '';
      }
  }
}
</script>

<style>
.highlight {
  background-color: #cf1111;
  padding: 10px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
  font-size: 24px;
  font-weight: bold;
  text-align: center;
}

input[type="text"] {
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  width: 100%;
  font-size: 18px;
}

button[type="button"] {
  background-color: #4CAF50;
  color: #fff;
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 18px;
  font-weight: bold;
}

button[type="button"]:hover {
  background-color: #3e8e41;
}

p {
  font-size: 18px;
  font-weight: bold;
  margin-bottom: 20px;
}

input[type="text"]:focus {
  border-color: #4CAF50;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}

input[type="text"]:invalid {
  border-color: #ff0000;
  box-shadow: 0 0 10px rgba(255, 0, 0, 0.2);
}
</style>