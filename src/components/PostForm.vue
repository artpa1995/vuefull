<template>
  <form @submit.prevent>
    <h4>Post create</h4>
    <my-input
      v-focus
      v-model="post.title"
      type="text"
      placeholder="title"
    />
    <my-input
      v-model="post.body"
      type="text"
      placeholder="description"
    />
    <my-button
      style="align-self: flex-end; margin-top: 15px"
      @click="createPost"
    >
      Create
    </my-button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      post: {
        title: '',
        body: ''
      }
    }
  },
  methods: {
    createPost() {
      this.post.id = Date.now();
      this.$emit('create', this.post)
      this.post = {
        title: '',
        body: ''
      }
    }
  },
}
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}

</style>
