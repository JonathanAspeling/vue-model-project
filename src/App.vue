<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Model :theme="theme" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Sign up now</a>
        <a href="#">More info</a>
      </template>
      <h1>Heading</h1>
      <p>Text Body Here</p>
    </Model>
  </div>
  <p></p>
  <button @click.alt="toggleModal">Open Model(Alt)</button>
</template>

<script>
import Model from "./components/Model.vue";

export default {
  name: "App",
  components: { Model },
  data() {
    return {
      title: "My first Vue App :)",
      header: "Sign-up for the give away!",
      text: "Grab your ninja swag for half price",
      theme: "sale",
      showModal: false,
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
  },
};
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
