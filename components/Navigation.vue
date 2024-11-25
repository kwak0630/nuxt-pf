<!-- Please remove this file from your project -->
<template>
	<div :class="{ 'nav-wrap': true, 'active': isActive }">
    <div class="dim"></div>
    <button type="button" class="btn-close" @click="closeNav">close</button>
    <div class="nav-list">
      <ul>
        <li>
          <button type="button" class="cursorHover" @click="handleClick('/main#intro')">Home</button>
        </li>
        <li>
          <button type="button" class="cursorHover" @click="handleClick('/main#profile')">Profile</button>
        </li>
        <li>
          <button type="button" class="cursorHover" @click="handleClick('/main#skill')">Skill</button>
        </li>
        <li>
          <button type="button" class="cursorHover" @click="handleClick('/main#portfolio')">Portfolio</button>
        </li>
        <li>
          <button type="button" class="cursorHover" @click="handleClick('/main#contact')">Contact</button>
        </li>
      </ul>
    </div>
  </div>
</template>
  
<script>
export default {
	name: 'Navigation',
  
  props: {
    isActive: {
      type: Boolean,
      default: false,
    },
  },

  methods: {
    closeNav() {
      this.$emit('closeNav'); 
    },
    handleClick(path) {
      this.closeNav();

      setTimeout(() => {
        this.$router.push(path);
      }, 100);
    },
  },
}
</script>