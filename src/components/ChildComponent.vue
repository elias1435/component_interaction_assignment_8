<script setup>
   const props  = defineProps(['message']);
   const emit   = defineEmits(['update:modelValue']);

   function messageEmitted (){
     props.name = emit('update:message','Hi I am a Vue Learner!')
   }

</script>

<template>
    <div class="mt-10 h-96 bg-gradient-to-r from-blue-100 to-teal-100 flex items-center justify-center flex-col">
        <h1 class="text-black-900 text-xl my-5">Chiled Component:</h1>
        <h2 class="text-black text-xl my-5">Message : <span class="text-red-600 hover:text-blue-900">{{ message }}</span></h2>
    </div>

    <div class="flex items-center justify-center">
        <button @click="messageEmitted ()" class="bg-blue-500 hover:bg-blue-700 text-white font-bold my-8 py-2 px-4 rounded"><em>Button</em></button>
    </div>

</template>

<style scoped>

</style>