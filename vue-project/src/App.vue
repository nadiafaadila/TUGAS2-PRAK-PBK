<template>
    <div>
      <p v-bind:class="titleclass">
      Hi, I am Nadia Fadila.
      </p>
      <h3 v-bind:class="titleclass">
      I'm an Informatics Engineering student of Riau Islamic University.  </h3>
  
      <h1>Event Listener</h1>
      <button @click="changeColor">Change Color Here</button>
      <div :style="{ backgroundColor: bgColor, padding: '20px' }">{{ message }}</div>
  
    </div>

  <div>
    <h4 v-bind:class="titleclass">
      Visitors
    </h4>
    <!-- Input teks -->
    <input type="text" v-model="inputText" placeholder="Masukkan teks">

    <!-- Tombol untuk menambahkan elemen -->
    <button @click="addElement">Tambahkan</button>

    <!-- Daftar elemen yang ditambahkan -->
    <ul>
      <li v-for="(element, index) in elements" :key="index">{{ element }}</li>
    </ul>
  </div>

  </template>

<script>
export default {
  data() {
    return {
      inputText: '', // Variabel untuk menyimpan nilai input teks
      elements: []   // Array untuk menyimpan elemen-elemen yang ditambahkan
    };
  },
  methods: {
    addElement() {
      // Tambahkan nilai input teks ke dalam array elemen
      this.elements.push(this.inputText);
      // Kosongkan input teks setelah ditambahkan
      this.inputText = '';
    }
  }
};
</script>
  
  <script setup>
  import { ref, reactive } from 'vue'
  
  const titleclass = ref("class")
  
  const message = ref('Klik tombol di atas untuk mengubah warna!');
  const bgColor = ref('black'); 
  
  const changeColor = () => {
    bgColor.value = '#' + Math.floor(Math.random()*16777215).toString(16);
  };
  </script>
  
  <style scoped>
  .class {
    font-size: 25px;
    color:rgb(197, 76, 116);
  }
  </style>