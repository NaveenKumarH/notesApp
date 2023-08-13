<script setup>

import { ref } from 'vue';
const data = ref([])
const noteAdd = ref('');

</script>

<template>
  <main>

    <div class="maindiv">
      <input type="text" v-model="noteAdd" placeholder="Add notes from here!" />
      <button style="background-color: white; color: black;"
        @click="() => { if (noteAdd != '') { data.push(noteAdd); noteAdd = ''; } }">+</button>
    </div>

    <div v-for="(item, index) in data" :key="index">
      <div class="notesdiv">
        <p>{{ item }}</p>
        <button @click="() => { data.splice(index, 1); }">-</button>
      </div>
    </div>

  </main>
</template>

<style>
* {
  background-color: black;
}

main {
  justify-content: center;
}

p {
  background-color: aliceblue;
  margin: 10px;
}

input {
  border-color: rgb(0, 0, 0);
  border-style: solid;
  border-radius: 3px;
  font-size: 10px;
  font-weight: bold;
  color: white;

}

.maindiv {
  display: flex;
  justify-content: space-evenly;
  padding: 20px;
  align-items: center;

}

.notesdiv {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: aliceblue;
  margin: 10px;
  border-radius: 3px;
}

button {
  border-radius: 3px;
  border-color: rgba(0, 0, 0, 0);
  color: white;
  background-color: black;
  margin: 15px;
}

::placeholder {
  color: white;
  opacity: 50%;
}
</style>
