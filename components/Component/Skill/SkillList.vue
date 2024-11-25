<template>
  <div class="skill-box">
    <div class="skill-list">
      <span 
        class="cursorHover" 
        v-for="(skill, index) in skills" 
        :key="index" 
        @mouseover="showLevel(index)" 
        @mouseleave="hideLevel"
      >
        {{ skill }}
      </span>
    </div>
    <div class="skill-level">
      <p 
        v-for="(level, index) in skillLevels" 
        :key="index" 
        :class="{ active: isActive(index) }"
      >
        {{ level }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    skills: {
      type: Array,
      required: true,
    },
    skillLevels: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      activeIndex: 0, // 첫 번째 인덱스 활성화
    };
  },
  methods: {
    showLevel(index) {
      this.activeIndex = index === this.skills.length - 1 ? this.skillLevels.length - 1 : index; // 마지막 skill일 경우 마지막 level 활성화
    },
    hideLevel() {
      this.activeIndex = 0; // 마우스가 떠날 때 첫 번째 인덱스 활성화
    },
    isActive(index) {
      return index === this.activeIndex; // 현재 인덱스가 활성화된 인덱스인지 확인
    },
  },
};
</script>