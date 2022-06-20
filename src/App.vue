<template>
  <h1>{{ title }}</h1>
  <p>Welcome....</p>
  <teleport to=".modals" v-if="showModal">
     <Modal theme="" @close="tonggleModal">
      <template v-slot:links>
        <a href="#">Sign Up Now</a>
        <a href="#">More info</a>
      </template>
      <h1>Ninja giveawey!</h1>
      <p>Grab half of the price of the product</p>
     </Modal>
  </teleport>

    <teleport to=".modals" v-if="showModalTwo">
     <Modal @close="tonggleModalTwo">
      <h1>Sign Up to the new Latter</h1>
      <p>for upadte to promo codes </p>
     </Modal>
    </teleport>


  <button @click.passive="tonggleModal">Open modal (passive)</button>
  <button @click.passive="tonggleModalTwo">Open modal</button>
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
        title: 'My first app vue js : )',
        showModal: false,
        showModalTwo: false
      }
    },
    methods: {
      tonggleModal() {
        this.showModal = !this.showModal
      },
      tonggleModalTwo() {
        this.showModalTwo = !this.showModalTwo
      },
    }
  }
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
    border-bottom: 1px solid #ccc;
    display: inline-block;
    padding-bottom: 10px;
  }
</style>