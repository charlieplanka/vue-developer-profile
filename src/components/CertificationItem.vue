<template>
  <div class="wrapper mb-4">
    <div class="cert-badge mr-2">
      <a :href="certification.link" target="_blank">
        <g-image :src="certification.icon" alt="" />
      </a>
    </div>
    <div class="cert-content">
      <h4 class="mb-1 break"><a :href="certification.link" target="_blank">{{ certification.name }}</a></h4>
      <div>{{ certification.granted }} | {{ certification.date }}</div>
      <div class="mt-3">{{ certification.description }}</div>
    </div>
  </div>
</template>
<script>
export default {
  name: "WorkItem",
  props: {
    'certification': {
      type: Object,
      default: function() {
        return {}
      }
    }
  },
  data: () => ({

  })
}
</script>
<style lang="scss" scoped>
.wrapper {
  display: flex;
  line-height: 1.5;
}
.cert-badge {
  flex: 0 0 15%;
}

.cert-content {
  flex: 1;
  margin-left: 10px;
  h4 {
    font-weight: 600;
    @media (max-width: 600px) {
        font-size: 1rem;
  }
  }
  
  @media (max-width: 600px) {
    font-size: 0.8rem;
  }
}

.break {
    overflow-wrap: break-word;
}
</style>




  font-size: 25px;
  @media (min-width: 800px) {
    font-size: 30px;
  }
  @media (min-width: 1200px) {
    font-size: 40px;
  }
}