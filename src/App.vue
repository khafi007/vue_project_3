<template>
  <div id="app">
    <MarkdownEditor />
  </div>
</template>

<script>
import MarkdownEditor from './components/Markdown.vue';

export default {
  name: 'App',
  components: {
    MarkdownEditor,
  },
};
</script>

<style>
body {
  font-family: Arial, sans-serif;
  
}
#app{
display: inline;
width:1500px;
}
.markdown-preview{
  overflow-wrap:anywhere;
}
</style>
