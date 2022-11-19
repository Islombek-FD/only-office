<template>
   <input @input="updateInput" :value="modelValue" class="input" type="text" />
</template>

<script>
   export default {
      name: 'my-input',
      props: {
         modelValue: [String, Number]
      },
      methods: {
         updateInput(e) {
            this.$emit('update:modelValue', e.target.value)
         }
      }
   }
</script>


<style scoped>
   .input {
      display: block;
      width: 100%;
      margin-bottom: 10px;
      padding: 10px;
      border: 2px solid gray;
   }

   .input:focus {
      outline: none;
   }
</style>