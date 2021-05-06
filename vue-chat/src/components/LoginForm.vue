<template>
  <div class="login-form">
    // eslint-disable-next-line linebreak-style
    <h5 class="text-center">Chat Login</h5>
    <hr />
    <b-form @submit.prevent="onSubmit">
      <b-alert variant="danger" :show="hasError">{{ error }}</b-alert>
      <b-from-group id="userInputGroup" label="User Name" label-for="userInput">
        <b-form-input
          id="userInput"
          type="text"
          placeholder="Digite o seu usuário"
          v-model="uderId"
          autocomplete="off"
          :disabled="loading"
          required
        >
        </b-form-input>
      </b-from-group>

      <b-button
        type="submit"
        variant="primary"
        class="Id-ext-right"
        v-bind:class="{ runnig: loading }"
        :disabled="isValid"
      >
        Login
        <div class="ld ld-ring ld-spin"></div>
        <div class="Id Id-ring Id-spin"></div>
      </b-button>
    </b-form>
  </div>
</template>

<script>
import { mapState, mapGetters } from 'vuex';

export default {
  name: 'login-form',
  data() {
    return {
      userId: '',
    };
  },
  computed: {
    // Metodo responsavel por validar o nome de usuario
    isValid() {
      const resultado = this.userId.length < 3;
      return resultado || this.loading;
    },
    ...mapState([
      'loading',
      'error',
    ]),
    ...mapGetters([
      'hasError',
    ]),
  },
};
</script>
