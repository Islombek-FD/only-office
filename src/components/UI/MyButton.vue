<template>
   <button>
      <slot></slot>
   </button>
</template>

<script>
   export default {
      name: 'my-button',
   }
</script>


<style scoped>
   .btn {
      padding: 10px;
      border: none;
      cursor: pointer;
      border-radius: 4px;
      transition: all 0.3s ease;
   }

   .btn:hover {
      opacity: 0.75;
   }

   .btn.block {
      width: 100%;
   }

   .btn-primary {
      background-color: rgb(71, 71, 240);
      color: white;
   }

   .btn-danger {
      background-color: rgb(240, 55, 55);
      color: white;
   }
</style>
