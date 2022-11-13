<template>
  <header class="header">
    <div class="header__logo"></div>
    <div class="header__menu"><slot></slot></div>
  </header>
</template>
<script>
export default {
  name: 'HeaderVue'
}
</script>