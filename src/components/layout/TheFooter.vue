<template>
  <div class="footer-container">
    <ul class="social-list">
      <li class="social-item">
        <a target="_blank" href="#"
          ><img src="../../assets/images/icon-facebook.svg" alt="Facebook"
        /></a>
      </li>
      <li class="social-item">
        <a target="_blank" href="https://www.pinterest.ru/coolmara007/"
          ><img src="../../assets/images/icon-pinterest.svg" alt="Pinterest"
        /></a>
      </li>
      <li class="social-item">
        <a target="_blank" href="https://www.instagram.com/marat.chochaev/"
          ><img src="../../assets/images/icon-instagram.svg" alt="Instagram"
        /></a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.footer-container {
  background-image: url("../../assets/images/pattern-hills.svg");
  background-repeat: no-repeat;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 30vh;
}
.social-list {
  list-style: none;
  display: flex;
  justify-content: center;
  align-items: center;
}
.social-item {
  padding: 10px;
  margin: 0 10px;
}
</style>
