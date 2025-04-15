<template>
  <h1>{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal theme="" @close="toggleModal">
      <template v-slot:links>
      <a href="#">Sign up now!</a>
      <a href="#">more info</a>
      </template>
      <h1>Giveaway Day!</h1>
      <p>Claim your SmartPhone!</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">Open modal (pressed key: alt)</button>
</template>

<script>
import Modal from './components/Modal.vue';

export default {
  name: 'App',
  components: { Modal },
  data() {
    return {
      title: 'My First Vue App',
      header: 'Sign up for Giveaway!',
      text: 'Claim your Smartphone',
      showModal: false
      }
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal
    }
  },
  mounted() {
    const elements = document.querySelectorAll('[fdprocessedid]');
    elements.forEach(el => el.removeAttribute('fdprocessedid'));
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
h1 {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
