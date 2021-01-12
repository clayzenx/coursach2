<template>
  <p v-if="value">{{ value }}</p>
</template>

<script>
export default {
  props: {
    value: { type: String, required: true },
  },
}
</script>
