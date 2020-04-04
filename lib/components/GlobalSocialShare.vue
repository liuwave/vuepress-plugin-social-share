<template>
  <div
    v-if="visible"
    class="social-share-global"
  >
    <social-share
      v-show="isActive"
      v-bind="$attrs"
    />
    <button
      @click="isActive = !isActive"
      class="social-share-trigger social-share-btn"
      type="button"
      role="button"
    >
      <span class="social-share-icon-svg">
        <svg
          v-if="isActive"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path d="M19,6.41L17.59,5L12,10.59L6.41,5L5,6.41L10.59,12L5,17.59L6.41,19L12,13.41L17.59,19L19,17.59L13.41,12L19,6.41Z" />
        </svg>
        <svg
          v-else
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path d="M18,16.08C17.24,16.08 16.56,16.38 16.04,16.85L8.91,12.7C8.96,12.47 9,12.24 9,12C9,11.76 8.96,11.53 8.91,11.3L15.96,7.19C16.5,7.69 17.21,8 18,8A3,3 0 0,0 21,5A3,3 0 0,0 18,2A3,3 0 0,0 15,5C15,5.24 15.04,5.47 15.09,5.7L8.04,9.81C7.5,9.31 6.79,9 6,9A3,3 0 0,0 3,12A3,3 0 0,0 6,15C6.79,15 7.5,14.69 8.04,14.19L15.16,18.34C15.11,18.55 15.08,18.77 15.08,19C15.08,20.61 16.39,21.91 18,21.91C19.61,21.91 20.92,20.61 20.92,19A2.92,2.92 0 0,0 18,16.08Z" />
        </svg>
      </span>
    </button>
  </div>
</template>

<script>
import SocialShare from './SocialShare'

export default {
  components: {
    SocialShare,
  },

  inheritAttrs: false,

  computed: {
    visible () {
      return !(this.$frontmatter.noGlobalSocialShare || this.$frontmatter.noSocialShare)
    },
  },

  data () {
    return {
      isActive: false,
    }
  },
}
</script>
