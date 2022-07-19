<template>
  <div class="hero-container">
    <div class="wrapper">
      <h1 class="hero-title">We're Launching Soon</h1>
      <HeroTimer />
    </div>
  </div>
</template>

<script>
import HeroTimer from "../components/hero/HeroTimer.vue";
export default {
  components: {
    HeroTimer,
  },
};
</script>

<style scoped>
.hero-container {
  background-image: url("../assets/images/bg-stars.svg");
  background-position: center center;
  height: 70vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.hero-title {
  text-align: center;
  margin-bottom: 100px;
  text-transform: uppercase;
  font-size: 30px;
  letter-spacing: 8px;
}
/* Адаптив */
@media only screen and (max-width: 768px) {
  .hero-title {
    font-size: 24px;
  }
}
</style>
