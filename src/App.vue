<template>
  <div id="app">
    <h1>Cadastro</h1>
    <div>
      <form action="">
        <label for="">Nome </label>
        <input type="text" v-model="user.nome" /><br /><br />

        <label for="">E-mail </label>
        <input type="email" v-model="user.email" /><br /><br />

        <label for="">Qtde funcionários </label>
        <input type="number" v-model="user.qtdeFunc" /><br /><br />

        <label for="">Opinião </label>
        <textarea v-model="opiniao"></textarea><br /><br />

        <label for="">Tecnologias</label>
        <span>
          <input type="checkbox" value="html" v-model="tecnologias" />HTML
        </span>
        <span>
          <input type="checkbox" value="css" v-model="tecnologias" />CSS
        </span>
        <span>
          <input
            type="checkbox"
            value="javascript"
            v-model="tecnologias"
          />Javascript
        </span>
        <span>
          <input type="checkbox" value="vuejs" v-model="tecnologias" />VueJS
        </span>
      </form>
    </div>
    <hr />
    <div class="item">
      <label for="">Nome: {{ user.nome }}</label> <br /><br />
      <label for="">E-mail: {{ user.email }}</label> <br /><br />
      <label for="">Qtde funcionários: {{ user.qtdeFunc }}</label> <br /><br />
      <label for="">Sua opinião: {{ opiniao }}</label> <br /><br />
      <label for="">Tecnologias:</label>
      <ul>
        <li v-for="tech in tecnologias" :key="tech">{{ tech }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      user: {
        nome: "",
        email: "",
        qtdeFunc: 0,
      },
      opiniao: "",
      tecnologias: [],
    };
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
</style>
