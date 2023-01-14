<script>
import Video from "./Video.vue";
export default {
  data() {
    return {
      count: 0,
    };
  },
  components: { Video },
};
</script>

<template>
  <div class="card">
    <button @click="count++">You clicked me {{ count }} times.</button>
    <Video />
  </div>
</template>

<style scoped>
.card {
  width: 60vw;
  height: 75vh;
  padding: 15px;
  box-sizing: border-box;
  background-color: var(--COOL_LIGHT);
  border-radius: 10px;
}

button {
  width: 100%;
  
}
</style>
