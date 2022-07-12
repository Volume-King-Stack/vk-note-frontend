<template>
  <div class="con">
    <Menus />
    <div class="right">
  <Editor class="editor" :init="{
        plugins: 'lists link image table code help wordcount'
      }" />
    </div>
  
  </div>
</template>

<script setup lang="ts">
import { defineComponent } from 'vue'
import Menus from './notes/menu.vue'
import Editor from '@tinymce/tinymce-vue'
</script>

<style scoped>
.con {
    display: flex;
    justify-content: space-between;
}
.right {
    width: calc(100% - 220px);
}
.editor {
    position: absolute;
    height: 100%;
}
</style>