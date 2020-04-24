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
      <h1>Bienvenido a la Trivia</h1>
      <h2>{{ addname() }}</h2>
      <label for="input-name">Tu nombre:</label>
      <!--<input type="text" @input="addname" placeholder="tu nombre"/>-->
      <b-form-input
      id="input-live"
      v-model="name"
      :state="nameState"
      aria-describedby="input-live-help input-live-feedback"
      placeholder="Enter your name"
      trim
    ></b-form-input>

      <router-link to="/trivia">
        <b-button :disabled="!nameState" pill variant="danger" >Empezar a jugar hoy</b-button>
      </router-link>
    </div>
  </div>
</template>


<script>
export default {
  name: "Home",
  data() {
    return {
      message: 'Hola mundo',
      arraylist: ["salir", "pasear", "estudiar"],
      newmessage: "",
      saludo: "",
      estate: true,
      name:'',
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
    addname() {
      if (this.name) {
        return this.saludo = "Hola " + this.name;
        
      }
    }
  },
  computed: {
    nameState() {
        return this.name.length > 2 ? true : false
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
  margin: auto;
  width:25%;
}
.main-trivia button {
  margin-top: 6px;
}
</style>