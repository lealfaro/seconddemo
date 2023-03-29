<template>
    <div class="about">
      <h1>Gracias por contactarnos</h1>
      {{message}}
      <button id="list" onclick="list()">List</button>
    </div>
  </template>

  <script>
  export default {
    name: "App",
    data() {
      return {
        message: ""
      };
    },
    async mounted() {
      const { text } = await (await fetch("/api/mtc")).json();
      this.message = text;
    }
  };
  </script>
  