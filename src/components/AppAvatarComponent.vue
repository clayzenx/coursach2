<template>
  <div class="avatar" v-if="value">
    <img alt="avatar" :src="value">
  </div>
</template>

<script>
export default {
  props: {
    value: { type: String, default: 'https://via.placeholder.com/150' }
  },
}
</script>

<style scoped>
.avatar { display: flex; justify-content: center; }
.avatar img { width: 150px; height: auto; border-radius: 50%;}
</style>