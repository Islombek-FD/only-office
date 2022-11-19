<template>
   <div v-if="posts.length > 0">
      <h2>Pragraming languages list</h2>

      <post-item @remove="$emit('remove', post)" v-for="post in posts" :key="post.id" :post='post'/>
   </div>
   <div v-else style="padding: 20px; border: 2px solid red; margin-top: 20px; text-align: center">
      <h2 style="color: red">No programing languages list</h2>
   </div>
</template>

<script>
   import PostItem from '@/components/PostItem.vue';

   export default {
      components: {
         PostItem
      },
      props: {
         posts: {
            type: Array,
            required: true
         },
      },
   }
</script>

<style scoped>
   
</style>