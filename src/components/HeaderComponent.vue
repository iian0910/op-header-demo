<template>
  <div class="header">
    <div class="left_icon">
      <img
        v-if="backControl"
        class="icon"
        src="../assets/back.png"
        width="20"
        @click="backEvent"
      />
    </div>
    <div>
      <div v-if="props.logoType">
        <img class="logo" src="../assets/openwallet.png">
      </div>
      <div v-if="props.titleType">{{ props.titleText }}</div>
    </div>
    <div class="right_icon">
      <img
        v-if="scanControl"
        class="icon"
        :class="{'mr-10': walletControl}"
        src="../assets/scanner.png"
        @click="scanEvent"
      >
      <img
        v-if="walletControl"
        class="icon"
        src="../assets/wallet.png"
        @click="walletEvent"
      >
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  logoType: {
    type: Boolean,
    default: false
  },
  titleType: {
    type: Boolean,
    default: false
  },
  titleText: {
    type: String,
    default: ''
  },
  backControl: {
    type: Boolean,
    default: false
  },
  scanControl: {
    type: Boolean,
    default: false
  },
  walletControl: {
    type: Boolean,
    default: false
  }
})

const emit = defineEmits(['backEvent', 'scanEvent', 'walletEvent'])

const backEvent = () => {
  emit('backEvent')
}

const scanEvent = () => {
  emit('scanEvent')
}

const walletEvent = () => {
  emit('walletEvent')
}

</script>

<style scoped>
.header {
  padding: 10px 20px;
  border: 1px solid black;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.left_icon {
  width: 20px;
}
.right_icon {
  display: flex;
}
.logo {
  display: block;
  width: 180px;
}
.icon {
  display: block;
  width: 20px;
  cursor: pointer;
}
.mr-10{
  margin-right: 10px;
}
</style>