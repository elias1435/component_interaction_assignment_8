<script setup>
    import { reactive,ref } from 'vue'
    import ChildComponent from './ChildComponent.vue';

    const persons = reactive({
            'name'  : 'Md. Eliass Hossain',
            'profession' : 'Web Developer @upwork.com',
            'projects' : [
                {'name' : 'Blog', 'link' : 'www.howtoonlinetips.com'},
                {'name' : 'Web Project', 'link' : 'www.ppa.co.uk'}
            ],
            'message'   : 'Working as a web developer with 10 years of experience'
        });
</script>

<template>
    <div class="h-96 bg-gradient-to-r from-blue-100 to-pink-100 flex items-center justify-center flex-col">
        <h1 class="text-black-900 text-xl my-5">Parent Component:</h1>
        <h2 class="text-black text-l ">Name : {{ persons.name }}</h2>
        <h2 class="text-black text-l ">Profession : {{ persons.profession }}</h2>
        <h2 class="text-black text-l ">Message : {{ persons.message }}</h2>
        <h2 class="text-black text-l mt-5 mb-3">Projects:</h2>
        <ul class="list-disc">
            <li class="ml-5" v-for="(project, index) in persons.projects" :key="index">{{ project.name }}</li>
        </ul>
    </div>

    <ChildComponent v-model:message="persons.message" ></ChildComponent>
</template>

<style scoped>

</style>