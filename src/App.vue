<template>
  <div id="app">
    <h1>Cadastro</h1>
    <div>
      <form v-on:submit.prevent="enviar">
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
        <br /><br />

        <label for="">Tipo de contrato</label>
        <select v-model="tipoSelecionado">
          <option
            v-for="tipo in tipos"
            v-bind:key="tipo.id"
            v-bind:value="tipo.nome"
          >
            {{ tipo.nome }}
          </option>
        </select>
        <br /><br />
        <label for="">Qual o seu nível?</label>
        <span>
          <input type="radio" value="basico" v-model="nivel" />Básico
        </span>
        <span>
          <input
            type="radio"
            value="intermediario"
            v-model="nivel"
          />Intermédiário
        </span>
        <span>
          <input type="radio" value="avancado" v-model="nivel" />Avançado
        </span>
        <br /><br />
        <button type="submit">Enviar</button>
      </form>
    </div>
    <hr />
    <div class="item" v-show="resultado">
      <label for="">Nome: {{ user.nome }}</label> <br /><br />
      <label for="">E-mail: {{ user.email }}</label> <br /><br />
      <label for="">Qtde funcionários: {{ user.qtdeFunc }}</label> <br /><br />
      <label for="">Sua opinião: {{ opiniao }}</label> <br /><br />
      <label for="">Tecnologias:</label>
      <ul>
        <li v-for="tech in tecnologias" v-bind:key="tech">{{ tech }}</li>
      </ul>
      <br /><br />
      <label for="">Tipo de contrato: {{ tipoSelecionado }}</label> <br /><br />
      <label for="">Nível selecionado: {{ nivel }}</label>
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
      tipos: [
        { id: 1, nome: "CLT" },
        { id: 2, nome: "Freelancer" },
        { id: 3, nome: "PJ" },
        { id: 4, nome: "Remoto" },
      ],
      tipoSelecionado: 1,
      nivel: "basico",
      resultado: false,
    };
  },
  methods: {
    enviar() {
      this.resultado = true;
    },
  },
};
</script>

<style scoped>
form {
  display: flex;
  flex-direction: column;
}
</style>
