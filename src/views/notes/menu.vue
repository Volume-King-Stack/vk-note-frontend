<template>
    <div class="menu-con">
        <div class="box" v-for="item, index in notes" :key="index">{{item.title}}</div>
    </div>
</template>

<script setup lang="ts">
import { ref } from "@vue/reactivity";

const notes = ref([
    {title: 'note1', content: 'content1'},
    {title: 'note2', content: 'content2'},
    {title: 'note3', content: 'content3'},
]);
</script>

<style scoped>
.menu-con {
    width: 220px;
    display: inline-block;
}
.box {
    width: 100%;
    height: 100px;
    background-color: rgb(225, 121, 121);
    margin: 10px;
    display: inline-block;
    cursor: pointer;
}
</style>