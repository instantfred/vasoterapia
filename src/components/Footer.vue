<template>
  <footer>
    <a href="https://www.facebook.com/VasoLLenoCR/"><img class="facebook" :src="facebookSvg" /></a>
  </footer>
</template>

<script>

  export default {
    name: 'Container',
    components: {
    },
    data() {
      return {
        facebookSvg: require('./../assets/facebook-svgrepo.svg')
      }
    }
  }
</script>

<style>
  footer {
    background-color: #eee;
    bottom: 0;
    position: fixed;
    right: 0;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .facebook {
    height: 30px;
    width: 25px;
  }
</style>