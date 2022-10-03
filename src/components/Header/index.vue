<script setup lang="ts">
import logoSrc from '@assets/vue.svg'
import init from '@wasm/fib.wasm?init'

type FibFunc = (num: number) => number

init({}).then(({ exports }) => {
  const fibFunc = exports.fib as FibFunc
  console.log('Fib result:', fibFunc(10))
})
</script>

<template>
  <p class="header-1">
    This is Header
  </p>
  <img :src="logoSrc" alt="">
</template>

<style scoped lang="scss">
@import url('./index.scss');
</style>
