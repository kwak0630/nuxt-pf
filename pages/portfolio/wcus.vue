<template>
  <div class="wrap">
    <CustomCursor />

    <div class="container portfolio">
      <div class="btn-wrap">
        <button type="button" class="btn-back">
          <i class="ico-arrow"></i> 
          <span class="cursorHover">Go Back</span>
        </button>
      </div>
      
      <div class="work-detail">
        <div class="title-box">
          <h3 class="title cursorHover">W Concept US</h3>
          <p class="date">2023.04 - 2024.01</p>
        </div>
        <div class="info-box">
          <div class="logo-box">
            <img :src="require('../../assets/images/portfolio/wcus.svg')">
          </div>
          <div class="desc-box">
            
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import CustomCursor from '@/components/Component/CustomCursor/CustomCursor.vue';

export default {
  components: {
    CustomCursor,
  },
}
</script>