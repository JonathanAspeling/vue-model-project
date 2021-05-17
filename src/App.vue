<template>
  <h1>{{ title }}</h1>
  <teleport to=".modals" v-if="showModal">
    <Model :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Heading</h1>
      <p>Text Body Here</p>
    </Model>
  </teleport>

  <teleport to=".modals" v-if="showModalTwo">
    <Model @close="toggleModalTwo">
      <slot> 
        <h1>It's not about the money</h1>
        <p>It's about sending a message</p>
      </slot>
    </Model>
  </teleport>
  <p></p>
  <button @click.alt="toggleModal">Open Model(Alt)</button>
  <button @click="toggleModalTwo">Suprise!</button>
</template>

<script>
import Model from "./components/Model.vue";


export default {
  name: "App",
  components: { Model },
  data() {
    return {
      title: "My first Vue App :)",
      theme: "sale",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
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
  padding-bottom: 10px;
}
button {
  margin: 10px;
}
</style>
