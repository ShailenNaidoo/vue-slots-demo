<template>
  <div>
    <slot v-bind="slotProps"></slot>
  </div>
</template>

<script>
export default {
  props: ["url"],
  data() {
    return {
      meta: null,
      loading: false,
      loaded: false,
      loadingTime: null,
      imageLoaded: false
    }
  },
  computed: {
    slotProps() {
      return { 
        state: this.$data, 
        actions: {
          setImageLoaded: this.setImageLoaded
        }
      }
    }
  },
  methods: {
    async getURLData(url) {
      const res = await fetch(`https://us-central1-webdata-eeba3.cloudfunctions.net/api?url=${url}`);
      return res.json();
    },
    setImageLoaded() {
      this.imageLoaded = true;
    },
    setLoadingInfo() {
      this.loading = false;
      this.loaded = true;
    }
  },
  async mounted() {
    this.loading = true;
    this.meta = await this.getURLData(this.url);
    this.setLoadingInfo();
  },
  watch: {
    loading: {
      handler(n) {
        this.$emit("loading",n);
      }
    },
    loaded: {
      handler(n) {
        this.$emit("loaded",n);
      }
    },
    imageLoaded: {
      handler(n) {
        this.$emit("image-loaded",n);
      }
    }
  }
}
</script>
