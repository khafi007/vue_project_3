<template>
  <div class="markdown-editor">
    <textarea v-model="input" placeholder="Enter markdown text"></textarea>
    <div v-html="compiledMarkdown" class="markdown-preview"></div>
  </div>
</template>

<script>
import { marked } from 'marked';
import hljs from 'highlight.js';
import 'highlight.js/styles/github.css';

export default {
  data() {
    return {
      input: '',
    };
  },
  computed: {
    compiledMarkdown() {
      return marked(this.input, {
        highlight: function (code) {
          return hljs.highlightAuto(code).value;
        },
      });
    },
  },
};
</script>

<style scoped>
.markdown-editor {
  display: flex;
  flex-direction: row;
}

textarea {
  width: 50%;
  height: 100vh;
  padding: 10px;
  font-size: 16px;
}

.markdown-preview {
  width: 50%;
  height: 100vh;
  padding: 10px;
  border-left: 1px solid #ddd;
  overflow: auto;
}
</style>
