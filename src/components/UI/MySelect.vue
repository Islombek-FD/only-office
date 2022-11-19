<template>
   <select @change="changeOption" v-model="modelValue" class='select'>
      <option disabled value="">All</option>

      <option v-for="option in options" :key="option.value" :value="option.value">{{option.name}}</option>
   </select>
</template>

<script>
   export default {
      name: "my-select",
      mthods: {
         changeOption(option) {
            this.$emit('update:modelValue', option);
         }
      }
   }
</script>

<style scoped>
   .select {
      padding: 10px;
      border: 2px solid gray;
   }
</style>