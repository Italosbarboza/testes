<template>
    <div class="w-full h-full flex flex-col rounded shadow-lg overflow-hidden">
      <div class="flex items-center justify-between p-2 bg-gray-800 text-white rounded-t">
        <h2 class="text-lg font-bold">Editor de Código</h2>
      </div>
      <textarea
        v-model="code"
        class="flex-grow p-4"
        style="background-color: #1a202c; color: #ffffff; border: none; outline: none; resize: none; font-family: 'Fira Code', monospace; font-size: 14px; line-height: 1.5; height: 90vh;"
        placeholder="Digite seu código HTML aqui..."
      ></textarea>
    </div>
  </template>
  
  <script>
  import { defineComponent } from 'vue';
  
  export default defineComponent({
    props: {
      modelValue: {
        type: String,
        default: ''
      }
    },
    data() {
      return {
        code: this.modelValue
      }
    },
    watch: {
      code(newVal) {
        this.$emit('update:modelValue', newVal)
      }
    },
    methods: {
      formatCode() {
        // Implementar um formatador de HTML simples
        this.code = this.code.trim();
      }
    }
  });
  </script>