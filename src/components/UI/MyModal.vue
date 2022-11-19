<template>
   <div @click.stop="toggleModal" class="modal" v-if="show">
      <div @click.stop class="modal__inner">
         <slot></slot>
      </div>
   </div>
</template>


<script>
   export default {
      name: "my-modal",
      props: {
         show: {
            type: Boolean,
            default: false
         }
      },
      methods: {
         toggleModal() {
            this.$emit('update:show', false);
         }
      }
   }
</script>

<style scoped>
   .modal {
      position: fixed;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
      z-index: 10000;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: rgba(0, 0, 0, 0.5);
   }

   .modal__inner {
      width: 400px;
      padding: 20px;
      background-color: white;
      border-radius: 20px;
   }
</style>