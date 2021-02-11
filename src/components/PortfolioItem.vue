<template>
  <div class="mb-4" @click="showDetail">
    <div>
      <div class="image-container">
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/organisation_thumb.png" fit="cover" v-if="project.code === 'organisation-figma'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/trello_thumb.png" fit="cover" v-else-if="project.code === 'trello-api'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/snake_thumb.png" fit="cover" v-else-if="project.code === 'snake-game'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/albums_thumb.png" fit="cover" v-else-if="project.code === 'music-albums'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/django_library_thumb.png" fit="cover" v-else-if="project.code === 'django-library'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/django_shelter_thumb.png" fit="cover" v-else-if="project.code === 'django-shelter'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/goose_gallery_thumb.png" fit="cover" v-else-if="project.code === 'goose-gallery'" height="240"/>
        <g-image
          class="thumbnail"
          src="~/assets/images/projects/websocket_chat_thumb.png" fit="cover" v-else-if="project.code === 'websocket-chat'" height="240"/>
        <div class="thumbnail-controls"
          @mouseover="showControl = true"
          @mouseleave="showControl = false"
          >
          <div class="controls" v-if="showControl">
            <div class="icon-wrapper">
              <font-awesome-icon icon="sign-in-alt" size="lg"/>
            </div>
          </div>
        </div>

      </div>


      <div class="mt-1"><strong>{{ project.name }} </strong></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "PortfolioItem",
  data: () => ({
    showControl: false
  }),
  props: {
    'project': {
      type: Object,
      default: function() {
        return {
        }
      }
    }
  },
  computed: {
  },
  methods: {
    showDetail() {
      this.$emit('showDetail')
    }
  }
}
</script>
<style lang="scss" scoped>

.image-container {
  position: relative;
}

.thumbnail {
    border-radius: 3%;
    border: 1px solid #ededed;
}

.thumbnail-controls:hover {
  box-shadow: 0 1px 6px rgba(57,73,76,0.35);
  border-color: transparent;
  background-color: rgba(0, 0, 0, 0.7);
  opacity: 0.3;
  cursor: pointer;
}

.controls {
  position: absolute;
  top: 50%;
  left: 50%;
  color: #3eaf7c;
  transform: translate(-50%, -50%);
  .icon-wrapper {
    background-color: #fff;
    border-radius: 50%;
    padding: 10px;
  }
  z-index: 101;
}

.thumbnail-controls {
  position: absolute;
  width: 100%;
  height: 100%;
  text-align: center;
  z-index: 100;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
}

.portfolio-wrapper {
  padding: 10px;
}

</style>
