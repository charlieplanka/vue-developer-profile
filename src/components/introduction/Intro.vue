<template>
  <section class="intro-hero">
    <div class="container">
      <div class="row">
        <div class="col-sm-12 text-center">
        <!-- change to g-image -->
          <g-image class="intro-hero-img"
            src="../../assets/images/profile-me.jpg"
            alt=""
            quality="100"
            width="270"/>
            <h2 class="hero-title"><strong>{{ personal.full_name }}</strong></h2>
            <p class="hero-tagline">
              <ClientOnly>
                <vue-typer
                  class="typing-list"
                  :text='personal.roles'
                  :repeat='Infinity'
                  :shuffle='false'
                  initial-action='typing'
                  :pre-type-delay='70'
                  :type-delay='60'
                  :pre-erase-delay='2000'
                  :erase-delay='40'
                  erase-style='backspace'
                  :erase-on-complete='false'
                  caret-animation='blink'
                  />
              </ClientOnly>
            </p>
        </div>
        <div class="col-sm-12 mt-4">
          <intro-social :socials="socials" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import IntroSocial from './IntroSocial.vue'
export default {
  name: "",
  props: {
    'socials': {
      type: Array,
      required: false,
      default: function() {
        return []
      }
    },
    'personal': {
      type: Object,
      required: true,
      default: function() {
        return {}
      }
    }
  },
  components: {
    VueTyper: () => import('vue-typer').then(m => m.VueTyper),
    IntroSocial
  },
  data: () => ({

  })
}
</script>
<style lang="scss" scoped>
p {
  line-height: 30px;
  margin-bottom: 20px;
}
.intro-hero {
  background: url(../../assets/images/intro-back.jpg) no-repeat center center fixed; 
  background-size: cover;
  padding-top: 90px;
  padding-bottom: 50px;
  position: relative;
  z-index: 1;
}
.intro-hero-img {
  border-radius: 50%;
  margin-bottom: 13px;
}
.hero-title {
  font-size: 30px;
  font-weight: normal;
  margin-top: 30px;
  margin-bottom: 10px;
  color: #212529;
}
</style>
