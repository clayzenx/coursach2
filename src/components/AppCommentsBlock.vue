<template>
  <p>
    <button class="btn primary" @click="fetchComments">Загрузить комментарии</button>
  </p>
  <div class="card" v-if="comments.length > 0">
    <h2>Комментарии</h2>
    <ul class="list">
      <li class="list-item" v-for="comment in comments" :key="comment.id">
        <div>
          <p><strong>{{ comment.email.split('@')[0] }}</strong></p>
          <small>{{ comment.name }}</small>
        </div>
      </li>
    </ul>
  </div>
  <div class="loader" v-if="loading"></div>
</template>

<script>
export default {
  data() {
    return {
      comments: [],
      loading: false
    }
  },
  methods: {
    fetchComments() {
      this.loading = true
      fetch('https://jsonplaceholder.typicode.com/comments?_limit=42')
        .then(response => response.ok? response.json(): Promise.reject('Не удалось получить данные'))
        .then(data => this.comments = data)
        .then(() => this.loading = false)
          .catch(err => alert(err))

    }
  },
}
</script>

