<template>
    <div class="nav-con" :class="isFold ? 'narrow' : 'wide'">
        <ul>
            <li @click="handleNavClick(item)" v-for="item in navs" :key="item.text">{{item.text}}</li>
        </ul>
        <div class="fold" @click="fold">折叠/展开</div>
    </div>
</template>

<script setup lang="ts">
import {defineProps, ref} from 'vue'
import {useRouter} from 'vue-router'

const props = defineProps(['a'])
console.log(props);

const navs = ref([
    {text: '所有功能', path: '/function'},
    {text: '随笔', path: '/informal'},
    {text: '笔记', path: '/notes'},
    {text: '协同合作', path: '/cooperation'},
    {text: '标签', path: '/tags'},
])
const isFold = ref<Boolean>(false)

const fold = () => {
    isFold.value = !isFold.value
}

const router = useRouter()
const handleNavClick = (item) => {
    router.push(item.path)
}
</script>

<style scoped>
.nav-con {
    margin: 10px;
    position: absolute;
    left: 0;
    top: 0;
    height: calc(100% - 20px);
    display: inline-block;
    background-color: rgb(67, 96, 152);
    border-radius: 8px;
    overflow: hidden;
    transition: width 0.1s ease-in-out;
}

li {
    margin: 20px;
    cursor: pointer;
    user-select: none;
}

.fold {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 30px;
    background-color: aqua;
    cursor: pointer;
    user-select: none;
}
.wide {
    width: 220px;
}
.narrow {
    width: 100px;
}
</style>
