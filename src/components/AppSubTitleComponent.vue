<template>
  <h2 v-if="value">{{ value }}</h2>
</template>

<script>
export default {
  props: {
    value: { type: String, default: '', required: true },
  },
}
</script>

<style scoped>

</style>