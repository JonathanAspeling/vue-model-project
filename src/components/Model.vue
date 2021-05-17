<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="model" :class="{ sale: theme === 'sale' }">
      <slot> default content</slot>
      <div class="actions">
        <slot name="links"> </slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
};
</script>

<style>
.model {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
.backdrop {
  top: 0;
  left: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.model h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}
.model p {
  font-style: normal;
}
.model .actions{
    text-align: center;
    margin: 30px 0 10px 0;
}
.model .actions a{
    color: #333;
    padding: 8px;
    border: 1px solid #eee;
    border-radius: 4px;
    text-decoration: none;
    margin: 10px;
}

.model.sale {
  background: crimson;
  color: white;
}
.model.sale h1 {
  color: white;
}
.model.sale .actions {
  background: crimson;
  color: white;
}
.model.sale .actions a{
  background: crimson;
  color: white;
}

</style>