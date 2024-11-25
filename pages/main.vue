<template>
  <div class="wrap">
    <Header />
    <CustomCursor />

    <div class="container main">
      <div class="sec-intro" id="intro">
        <div class="memoji"><img :src="require('../assets/images/sallyemoji.png')"></div>
        <span class="text1 cursorHover">#publisher</span>
        <span class="text2 cursorHover">#esfp</span>
        <span class="text3 cursorHover">#speed</span>
        <span class="text4 cursorHover">#detail</span>
        <span class="text5 cursorHover">#front-end delvop</span>
      </div>
      <div class="sec-profile" id="profile">
        <div class="title-wrap">
          <h2 class="title-type">ABOUT</h2>
        </div>
        <div class="profile-box">
          <div class="me"><img :src="require('../assets/images/sally.jpg')"></div>
          <div class="info">
            <div>
              <p class="title">Profile</p>
              <p>곽소형 / kwak so hyung</p>
              <p>1992. 06. 30</p>
              <p>ESFP</p>
              <p>kwak0630@gmail.com</p>
            </div>
            <div>
              <p class="title">History</p>
              <p>플그림 <span>2022.09 ~ 재직 중</span></p>
              <p>디지털다임 <span>2018.07 ~ 2022.09</span></p>
              <p>뉴턴그룹 <span>2017.02 ~ 2018.06</span></p>
              <p>아이커뮤니케이션즈 <span>2014.08 ~ 2016.11</span></p>
              <p>한양여자대학교 컴퓨터정보과 <span>2011.03 ~ 2014.02</span></p>
            </div>
            <div>
              <p class="title">License</p>
              <p>컴퓨터활용능력 3급</p>
              <p>정보기술자격 인증시험</p>
              <p>워드프로세서 1급</p>
            </div>
          </div>
        </div>
      </div>
      <div class="sec-skill" id="skill">
        <div class="title-wrap">
          <h2 class="title-type">SKILL</h2>
        </div>
        <SkillList :skills="skills" :skillLevels="skillLevels" />
      </div>
      <div class="sec-portfolio" id="portfolio">
        <div class="title-wrap">
          <h2 class="title-type">PORTFOLIO</h2>
        </div>
        <div class="portfolio-box">
          <div class="portfolio-item">
            <NuxtLink :to="{ path: '/portfolio/wcus', }">W Concept US</NuxtLink>
          </div>
        </div>
      </div>
      <div class="sec-contact" id="contact">
        <div class="title-wrap">
          <h2 class="title-type">CONTACT</h2>
        </div>
        <div class="contact-box">
          <i class="ico-letter"></i>
          <p class="email cursor-hover">kwak0630@gmail.com</p>
          <p>연락 주세요~!</p>
          <p class="v2">연락 주시면 이력서 및 경력기술서를 보내드립니다!</p>
        </div>
      </div>

      <ToastPopup ref="toastChrome" :timeout='15'>
        <template slot="content">
          <p><span>Chrome으로 보는 걸 권장합니다!</span></p>
        </template>
      </ToastPopup>
    </div>
  </div>
</template>

<script>
import CustomCursor from '@/components/Component/CustomCursor/CustomCursor.vue';
import SkillList from '@/components/Component/Skill/SkillList.vue';
import ToastPopup from '@/components/Popup/ToastPopup.vue';

export default {
  name: 'IndexPage',

  components: {
    CustomCursor,
    SkillList,
    ToastPopup
  },
  data() {
    return {
      skills: ['HTML', 'CSS, SCSS', 'Vue.js', 'JAVASCRIPT', 'jQuery', 'Photoshop', 'React.js'],
      skillLevels: [9, 9, 7, 7, 8, 4, 6],
    };
  },
  mounted() {
    // 컴포넌트가 마운트되면 ToastPopup을 열기
    this.$refs.toastChrome.open();
  }

}
</script>
