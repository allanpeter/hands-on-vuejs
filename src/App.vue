

<template>
  <div class="container" style="margin-top: 50px;">
    <div class="mb-3">
      <label for="inputNome" class="form-label">Nome</label>
      <input type="email" class="form-control" id="inputNome" aria-describedby="emailHelp" v-model="form.name"
        placeholder="Digite o Nome">
    </div>
    <div class="mb-3">
      <label for="inputNome" class="form-label">Time</label>
      <input type="email" class="form-control" id="inputNome" aria-describedby="emailHelp" v-model="form.team"
        placeholder="Digite o Time">
    </div>

    <div class="mb-3">
      <label for="inputNome" class="form-label">Idade</label>
      <input type="email" class="form-control" id="inputNome" aria-describedby="emailHelp" v-model="form.age"
        placeholder="Digite o Idade">
    </div>
  

    <button @click="addUser()" class="btn btn-primary">Salvar</button>
  </div>

  <div class="container" style="margin-top: 50px;">
    <div class="row">
    <div class="col">
      <div v-for="(user, index) in users" :key="index">
      <p>Nome: {{ user.name }}</p>
      <p>Time: {{ user.team }}</p>
      <p>Idade: {{ user.age }}</p>
      <hr />
    </div>
    </div>
  </div>
  
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";

interface User {
  name: string;
  team: string;
  age: string;
}

const form = ref<User>({
  name: "",
  team: "",
  age: "",
});

const users = ref<User[]>([]);

function addUser() {
  users.value.push(form.value);
}
</script>
