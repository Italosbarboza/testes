<template>
    <div class="preview p-4 border rounded" v-html="content"></div>
  </template>
  
  <script>

  export default {
    props: {
      content: {
        type: String,
        default: ''
      }
    }
  }
  </script>
  