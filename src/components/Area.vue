<template>
    <div class="area-con">
        <router-view></router-view>
    </div>
</template>

<script setup lang="ts">
import { defineComponent } from 'vue'
</script>

<style scoped>
.area-con {
    margin: 10px 10px 10px 0;
    position: fixed;
    left: 240px;
    top: 0;
    width: 80%;
    height: calc(100% - 20px);
    display: inline-block;
    background-color: rgb(78, 177, 190);
    border-radius: 8px;
    overflow: hidden;
    transition: width 0.1s ease-in-out;
    /* cursor: pointer; */
    /* user-select: none; */
}
</style>