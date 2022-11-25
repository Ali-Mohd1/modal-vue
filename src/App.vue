<template>
  <div>
    <h1>{{ title }}</h1>
    <teleport to=".modals" v-if="showModal">
      <Modal @close="toggleModal">
        <template v-slot:links>
          <a href="#">Log in</a>
        </template>
        <h1>Log In</h1>
        <form>
          <input type="email" placeholder="Email " />
          <input type="password" placeholder="......." />
        </form>
      </Modal>
    </teleport>
    <teleport to=".modals" v-if="showModalTwo">
      <Modal @close="toggleModalTwo">
        <template v-slot:links>
          <a href="#">Get Started</a>
        </template>
        <h1>Create Account</h1>
        <form>
          <input type="text" placeholder="Full Name" />
          <input type="email" placeholder="Email " />
          <input type="password" placeholder="......." />
        </form>
      </Modal>
    </teleport>
    <div>
      <button @click="toggleModal">Log In</button>
      <button @click="toggleModalTwo">Sign Up</button>
    </div>
  </div>
</template>

<script>
import Modal from "./components/Modal.vue";
export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      title: "Modal Created Using Vue.Js",
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
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  padding-bottom: 10px;
  margin-bottom: 10px;
}
button {
  background: rgba(38, 71, 241);
  padding: 10px 15px;
  border: none;
  border-radius: 10px;
  font-size: 16px;
  color: #fff;
  margin: 10px 5px;
  cursor: pointer;
}
</style>
