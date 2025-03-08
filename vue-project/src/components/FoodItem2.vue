<template>
    <div class="mangoes">
      <h2>{{ name }}</h2>  
      <p>{{ message }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: 'Mangoes',
        message: 'I like Mangoes',
        clicks: 0
      }
    }
  }
  </script>
  
  <style>
  .mangoes {
    border: dashed black 1px;
    display: inline-block;
    margin: 10px;
    padding: 10px;
    background-color: yellow;
  }

  </style>