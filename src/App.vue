<template>
  <div class="container">
    <HeaderComponent
      back-control
      scan-control
      wallet-control
      logo-type
      :title-text="'我是 Title Text'"
      @backEvent="backEvent"
      @scanEvent="scanEvent"
      @walletEvent="walletEvent"
    />
  </div>
</template>

<script setup>
import HeaderComponent from './components/HeaderComponent.vue'

const backEvent = () => {
  console.log('元件外部執行 backEvent !')
}

const scanEvent = () => {
  console.log('元件外部執行 scanEvent !')
}

const walletEvent = () => {
  console.log('元件外部執行 walletEvent !')
}

</script>

<style scoped>
.container {
  width: 760px;
  height: 100vh;
  margin: 0 auto;
  background-color: #fff;
}
</style>

