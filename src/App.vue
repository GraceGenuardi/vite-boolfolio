<script>
import Posts from './components/Posts.vue'
import axios from 'axios'

export default {
  components: {
    Posts
  },
  data() {
    return {
      projects: []
    }
  },
  created() {
    axios.get('http://localhost:8000/api/projects')
      .then(response => {
        this.projects = response.data
      })
      .catch(error => {
        console.log(error)
      })
  }
}
</script>

<template>
  <div class="container">
    <h1 class="title">
      Posts
    </h1>
    <Posts />
  </div>
</template>

<style >
.title {
  padding: 2rem 0;
}
</style>
