<template>
  <div>
    <slot v-bind="$data"></slot>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: "Scoped Slot",
      num: 1
    }
  },
  mounted() {
    setInterval(() => this.num++,1000);
  }
}
</script>

<style scoped>
div {
  font-size: 44px;
}
</style>
