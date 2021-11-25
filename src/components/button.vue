<template>
  <button class="button">
    <slot />
  </button>
</template>

<script>
</script>

<style scoped>
.button {
  border-radius: 5px;
  background-color: white;
  color: black;
  border: 2px solid #3c71ff;
  padding: 13px 10px;
  width: 100%;
  text-align: center;
  text-decoration: none;
  display: block;
  font-size: 13px;
  margin: 4px 2px;
  cursor: pointer;
  transition: all 0.3s ease;
}
.button:hover {
  background-color: #3c71ff;
  color: #fff;
}
</style>