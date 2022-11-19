// @input="post.title = $event.target.value" v-bind:value="post.title" = v-model='post.title'
// @input="post.body = $event.target.value" v-bind:value="post.body" = v-model='post.body'

<template>
   <form @submit.prevent>
      <h2 style="margin-bottom: 20px;">Create post</h2>
      
      <my-input 
         v-model="post.title"
         class="input" 
         type="text" 
         placeholder="Write title"
      />
         
      <my-input
         v-model="post.body"
         class="input" 
         type="text" 
         placeholder="Write body"
      />

      <div style="display: flex; justify-content: flex-end; gap: 20px">
         <my-button class="btn btn-danger">Cancel</my-button>
         <my-button @click="createPost" class="btn btn-primary">Add Post</my-button>
      </div>
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
            this.$emit('create', this.post);
            this.post = {
               title: '',
               body: ''
            }
         }
      }
   }
</script>

<style scoped>
   
</style>