<template>
  <header class="header-wrap">
    <button type="button" class="logo cursorHover" @click="toggleNav">Sally Portfolio</button>
    <Navigation :isActive="isNavActive" @closeNav="closeNav" />
  </header>
</template>

<script>
export default {
  name: 'Header',
  
  data() {
    return {
      isNavActive: false
    };
  },
  methods: {
    toggleNav() {
      this.isNavActive = !this.isNavActive;
    },
    closeNav() {
      this.isNavActive = false;
    },
  },
};
</script>