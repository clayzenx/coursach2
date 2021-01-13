<template>
  <form class="card">
    <div class="form-control">
      <label for="type">Тип блока</label>
      <select v-model="type" id="type">
        <option value="title">Заголовок</option>
        <option value="sub-title">Подзаголовок</option>
        <option value="avatar">Аватар</option>
        <option value="text">Текст</option>
      </select>
    </div>

    <div class="form-control">
      <label for="value">Значение</label>
      <textarea v-model="value" id="value" rows="3"></textarea>
    </div>

    <button
        :disabled="!isValid()"
        class="btn primary"
        @click.prevent="add">
      Добавить
    </button>
  </form>
</template>

<script>
export default {
  emits: ['addComponent'],
  data() {
    return {
      type: 'title',
      value: '',
      id: 0,
    }
  },
  methods: {
    add() {
      if ( this.isValid() )
        this.$emit('addComponent', { id: this.id + 1, type: this.type, value: this.value })
        this.value = ''; this.type = 'title'
    },
    isValid(){ return this.value !== '' }
  },
}
</script>
