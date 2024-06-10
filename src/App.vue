<template>
  <div id="app" class="container mx-auto p-4">
    <h1 class="text-3xl font-bold mb-6 text-center">Editor de Código HTML com TailwindCSS</h1>
    <div class="flex flex-col lg:flex-row gap-4">
      <div class="lg:w-1/2">
        <CodeEditor v-model="code" />
      </div>
      <div class="lg:w-1/2 p-4 bg-gray-100 rounded shadow-lg">
        <Preview :content="previewCode" />
      </div>
    </div>
  </div>
</template>

<script>
import { ref, watch } from 'vue';
import CodeEditor from './components/CodeEditor.vue';
import Preview from './components/Preview.vue';

export default {
  components: {
    CodeEditor,
    Preview
  },
  setup() {
    const code = ref('<div class="text-center text-blue-500">Hello, TailwindCSS!</div>');
    const previewCode = ref(code.value);

    watch(code, (newCode) => {
      previewCode.value = newCode;
    });

    return { code, previewCode };
  }
}
</script>

<style>
body {
  font-family: 'Nunito', sans-serif;
}
</style>
