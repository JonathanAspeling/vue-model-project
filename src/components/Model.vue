<template>
  <div class="backdrop">
      <div class="model">
          <p>Model Content</p>
      </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.model{
    width: 400px;
    padding: 20px;
    margin: 100px auto;
    background: white;
    border-radius: 10px;
    }
    .backdrop{
        top:0;
        left: 0;
        position: fixed;
        background: rgba(0,0,0,0.5);
        width: 100%;
        height: 100%;
    }

</style>