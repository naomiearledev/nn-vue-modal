<template>

  <h1>{{ title }}</h1>

  <div v-if="showModal1">
    <Modal :theme="modalTheme1" @close="toggleModal1">
      <template v-slot:links>
        <a href="#">Sign up for piano lessons</a>
        <a href="#">Sign up for singing lessons</a>
      </template>
      <h1>Payday Sale!</h1>
      <p>Half price for all items purchased before 4pm on 31st September</p>
    </Modal>
  </div>

  <div v-if="showModal2">
    <Modal :theme="modalTheme2" @close="toggleModal2">
      <template v-slot:links>
        <a href="#">Click here to die!</a>
        <a href="#">Click here to live!</a>
      </template>
      <h1>Do you want to live or die?</h1>
      <p>Make your choice by clicking on of the buttons</p>
    </Modal>
  </div>

  <div class="buttons">
    <button @click="toggleModal1">Show Modal 1</button>
    <button @click="toggleModal2">Show Modal 2</button>
  </div>

</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first vue app',
      modalTheme1: 'sale',
      modalTheme2: 'dark',
      showModal1: false,
      showModal2: false
    }
  },
  methods: {
    toggleModal1() {
      this.showModal1 = !this.showModal1
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.buttons button {
  margin-left: 10px;
}
</style>
