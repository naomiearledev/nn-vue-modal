<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :header="header" :text="text" :theme="modalTheme" @close="toggleModal" />
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
