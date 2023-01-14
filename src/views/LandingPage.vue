<template>
  <div class="page">
    <Game />
  </div>
</template>
<script>
import Game from '../components/Game.vue';
export default {
  name: "LandingPage",
  components: { Game},
};
</script>
<style>
.page {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--LIGHT);
}
</style>
