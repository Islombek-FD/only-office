<template>
   <div class="post">
      <strong class="post-id">{{post.id}}</strong>
      
      <div>
         <h3>Title: {{post.title}}</h3>
         <p>Body: {{post.body}}</p>
      </div>

      <my-button @click="$emit('remove', post)" class="btn btn-danger">Delete</my-button>
   </div>
</template>

<script>
   export default {
      props: {
         post: {
            type: Object,
            required: true
         }
      }
   }
</script>

<style scoped>
   .post {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-top: 20px;
      padding: 20px;
      border: 2px solid red;
   }

   .post-id {
      margin-right: 10px;
      font-size: 20px;
   }
</style>