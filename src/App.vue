<template>
  <p class="text-6xl font-bold underline underline-offset-8 mb-8">
    {{ title }}
  </p>
  <p class="text-gray-500 mb-2">Welcome</p>
  <Teleport to="#Modal" v-if="showModal">
    <Modal :header="header" :text="text" @close="toggleModal">
      <p class="text-6xl font-bold">{{ header }}</p>
      <p class="text-2xl">{{ text }}</p>
      <template v-slot:links>
        <a href="#" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800 ml-4">subscribe</a>
        <a href="#" class="text-white bg-blue-700 hover:bg-blue-800 focus:ring-4 focus:ring-blue-300 font-medium rounded-lg text-sm px-5 py-2.5 mr-2 mb-2 dark:bg-blue-600 dark:hover:bg-blue-700 focus:outline-none dark:focus:ring-blue-800 ml-4 ">unsubscribe</a>
      </template>
    </Modal>
  </Teleport>
  <button @click="toggleModal" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full">Show
    Modal</button>
</template>

<script>
import Modal from './components/Modal.vue'

export default {
  name: 'App',
  components: {
    Modal
  },
  data() {
    return {
      header: 'Hi, Saifullah here!',
      text: 'please Subscribe me',
      title: 'Hello World',
      showModal: false,
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
