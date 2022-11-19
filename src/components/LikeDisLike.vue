<template>
   <dir>
      <dir>
         <h3>Like: {{ likes }}</h3>
         <h3>Dislikes: {{ dislikes }}</h3>
      </dir>

      <div>
         <button @click="addLike">Add like</button>
         <button @click="addDislikes">Add dislikes</button>
      </div>
   </dir>
</template>

<script>
   export default {
      data() {
         return {
            likes: 0,
            dislikes: 0
         }
      },
      methods: {
         addLike() {
            this.likes +=1
         },
         addDislikes() {
            this.dislikes +=1
         }
      }
   }
</script>