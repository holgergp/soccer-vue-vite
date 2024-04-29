<script setup>

import LeagueTable from "./components/LeagueTable.vue";
</script>

<template>
  <div className="index">
    <LeagueTable />
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  color: #fff;
  background: #222;
}

#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 2rem;
}

.index img {
  margin: 40px auto;
  border-radius: 4px;
  background: #fff;
  display: block;
}

.App {
  text-align: center;
}
.index .notice {
  margin: 20px auto;
  padding: 15px 0;
  text-align: center;
  border: 1px solid #000;
  border-width: 1px 0;
  background: #666;
}

.textPointer {
  cursor: text;
}
</style>
