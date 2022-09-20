<template>
  <h1>{{ title }}</h1>
  <p>Welcome ...</p>
  <teleport  to=".modals" v-if="showModal">
    <Modal theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Gibveway</h1>
      <p>Ninja Gibveway</p>
    </Modal>
  </teleport>
  <div v-if="showModalTwo">
    <Modal @close="toggleModalTwo">
      <h1>Sign up to the newsletter</h1>
      <p>for updates and promo codes</p>
    </Modal>
  </div>
  <button @click.alt="toggleModal">open modal(alt)</button>
  <button @click.alt="toggleModalTwo">open modal two(alt)</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  components: { Modal },
  name: "App",
  // components: {
  //   HelloWorld
  // },
  data() {
    return {
      text: "text",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app, .modals {
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
  scroll-padding-bottom: 10px;
}
</style>
