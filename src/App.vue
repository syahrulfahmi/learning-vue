<template>
  <h1>{{ title }}</h1>
  <div v-if="isShowModal">
    <Modal theme="sale" @close="toggleModal">
      <h1>{{ header }}</h1>
      <p>{{ content }}</p>
      <template v-slot:links>
        <a href="#">Sign Up</a>
        <a href="#">Sign In</a>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Open Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components : {
    Modal
  },
  data () {
    return {
      title: "Aplikasi Vue Pertama Saya",
      header: "Header of the component",
      content: "Content of the component",
      isShowModal: false
    }
  },
  methods : {
    toggleModal() {
      this.isShowModal = !this.isShowModal
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
