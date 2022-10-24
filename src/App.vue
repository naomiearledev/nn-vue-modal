<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :theme="modalTheme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up for piano lessons</a>
        <a href="#">Sign up for singing lessons</a>
      </template>
      <h1>Payday Sale!</h1>
      <p>Half price for all items purchased before 4pm on 31st September</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">Show Modal (option)</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My first vue app',
      header: 'Sign up for the Giveaway!',
      text: 'Join us on patreon or locals to enter',
      modalTheme: 'dark',
      showModal: false
    }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
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
</style>
