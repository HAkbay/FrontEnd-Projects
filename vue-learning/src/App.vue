<template>
  <h1>{{ message }}</h1>
  <p>{{ text }}</p>
  <div v-if="showModal">
    <Modal @close="onClick" theme="dark">
      <h1>{{ header }}</h1>
      <p>{{ text }}</p>
      <template v-slot:buttons>
        <a href="#">A</a>
        <a href="#">B</a>
      </template>
    </Modal>
  </div>
  <button @click="onClick">Click</button>
</template>

<script>
  import Modal from './components/Modal.vue'
  export default {
    name: 'App',
    components: { Modal },
    data(){
      return {
        header: 'This Is a Header',
        text: 'This Is a Text',
        message: 'Wassup',
        showModal: false
      }
    },
    methods: {
      onClick(){
        this.showModal = !this.showModal
      }
    }
  }
</script>

<style scoped>
  h1{
    border-bottom: 1px solid rgb(0, 255, 255);
    display: inline-block;
    padding-bottom: 1px;
  }
</style>
