<template>
  <div class="home">
    <!--<h1>{{ message }}</h1>
    <input type="text" v-model="message" />
    <ul>
      <li v-for="(list,index) in arraylist" :key="index">
        {{ index }} {{ list }}
        <button @click="deletemessage(index)">eliminar</button>
      </li>
    </ul>
    <label for="input-text">coloca tu item aqui</label>
    <input type="text" id="input-text" v-model="newmessage" />
    <button v-on:click="addmessage">Agregar mensaje</button>-->

    <div class="main-trivia">
      <h1>Bienvenido a la Trivi   a</h1>
      <h2>{{ saludo }}</h2>
      <label for="input-name">Tu nombre:</label>
      <input type="text" @input="addname" />
      <router-link to="/trivia">
        <button :disabled="isDisabled">Empezar a jugar hoy</button>
      </router-link>
    </div>
  </div>
</template>


<script>
export default {
  name: "Home",
  data() {
    return {
      message: "Hola mundo",
      arraylist: ["salir", "pasear", "estudiar"],
      newmessage: "",
      saludo: "",
      estate: true
    };
  },
  methods: {
    addmessage() {
      this.arraylist.push(this.newmessage);
      this.newmessage = "";
    },
    deletemessage(index) {
      this.arraylist.splice(index, 1);
    },
    addname(e) {
      if (e.target.value) {
        this.saludo = "Hola " + e.target.value;
        this.estate = false;
      } else {
        this.saludo = "";
        this.estate= true;
      }
    }
  },
  computed: {
    isDisabled() {
      return this.estate;
    }
  }
};
</script>

<style>
.main-trivia {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
}
.main-trivia button {
  margin-top: 6px;
}
</style>