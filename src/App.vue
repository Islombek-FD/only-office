// v-bind:posts = :post;
// v-on:click = @click;

<template>
   <div class="container">
      <h1>Create post</h1>

      <div style="display: flex; justify-content: space-between; align-items: center">
         <my-button @click="createPostModal" class="btn btn-primary">Add post</my-button>

         <my-select v-model="selectedSort"> 
            
         </my-select>
      </div>

      <my-modal v-model:show="showModal">
         <post-from @create="createPost" />
      </my-modal>

      <post-list v-if="!isPostsLoading" @remove="removePost" :posts="posts" />

      <div v-else>
         <h3>Loading....</h3>
      </div>
   </div>
</template>

<script>
   import axios from 'axios';
   import PostFrom from './components/PostForm.vue';
   import PostList from '@/components/PostList.vue';

   export default {
      components: {
         PostFrom,
         PostList
      },
      data() {
         return {
            posts: [],
            showModal: false,
            isPostsLoading: true, 
            selectedSort: ''
         }
      },
      methods: {
         async fetchPosts() {
            try {
               this.isPostsLoading = true;
               const response = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10');
               
               this.posts = response.data;
            } catch (e) {
               console.log(e.messagw);
            } finally {
               this.isPostsLoading = false;
            }
         },
         createPostModal() {
            this.showModal = true;
         },
         createPost(post) {
            this.posts.push(post);
            this.showModal = false;
         },
         removePost(post) {
            this.posts = this.posts.filter(p => p.id !== post.id);
         }
      },
      mounted() {
         this.fetchPosts();
      }
   }
</script>


<style>
   * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
   }

   .container {
      max-width: 500px;
      margin: 0 auto;
   }
</style>