<template>
  <h1 v-if="value">{{ value }}</h1>
</template>

<script>
export default {
  props: {
    value: { type: String, default: '', required: true },
  },
}
</script>

