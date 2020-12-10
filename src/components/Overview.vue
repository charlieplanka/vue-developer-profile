<template>
  <div>
    <Card title="Обо мне">
      <p class="lead">
        Привет! Меня зовут <strong>{{ personal.name }}</strong>, я веб-программистка.
      </p>
      <p>
         Пишу на Python и Javascript, знаю основы вёрстки, знакома с Django и Vue. Открыта к интересным проектам и сотрудничеству.
      </p>
      <div class="mt-4">
        <button class="btn btn-primary mr-3" @click="downloadResume">Посмотреть резюме</button>
        <!-- <buy-me-a-coffee v-if="coffeeDonateUrl" :coffeeDonateUrl="coffeeDonateUrl"/> -->
      </div>
    </Card>
  </div>
</template>
<script>
import Card from './Card.vue'
// import BuyMeACoffee from './common/BuyMeACoffee.vue'

export default {
  name: "Overview",
  props: {
    // 'socials': {
    //   type: Array,
    //   required: true,
    //   default: function() {
    //     return []
    //   }
    // },
    'personal': {
      type: Object,
      required: true,
      default: function() {
        return {}
      }
    },
    // "coffeeDonateUrl": {
    //   type: String,
    //   required: false,
    //   default: function() {
    //     return "https://www.buymeacoffee.com/8buMYCOog"
    //   }
    // }
  },
  components: {
    Card,
    // BuyMeACoffee
  },
  data: () => ({

  }),
  methods: {
    downloadResume() {
      window.open("https://drive.google.com/file/d/1oZ0lcjsO5GIHjkhcUjtaDVY6IsUw9v1Z/", "_blank")
    }
  }
}
</script>
<style lang="scss" scoped>
.lead {
  color: #000;
}
</style>
