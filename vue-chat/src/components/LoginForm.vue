<template>
       <div>
            <div class="login-form">
                // eslint-disable-next-line linebreak-style
                <h5 class="text-center">Chat Login</h5>
                <hr>
                <b-form @submit.prevent="onSubmit">
                    <b-alert variant="danger" :show="hasError">{{ error }}</b-alert>

                    <b-from-group id="userInputGroup"
                                label="User Name"
                                label-for="userInput">
                        <b-form-input id="userInput"
                                    type="text"
                                    placeholder="Digite o seu usuário"
                                    v-model="uderId"
                                    autocomplete="off"
                                    :disabled="loading"
                                    required>
                        </b-form-input>
                     </b-from-group>
                    <b-button type="submit"
                            variant="primary"
                            class="Id-ext-right"
                            v-bind:class="{ runnig: loading}"
                            :disabled="isValid">
                            Login <div class="Id Id-ring Id-spin"></div>
                    </b-button>
                </b-form>
            </div>
        </div>
</template>

<script>
import { mapState, masGetters } from 'vuex';

export default {
  name: 'login-form',
  data() {
    return {
      UserId: '',
    };
  },
  computed: {
    isValid: function() {
      const result = this.userId.length < 3;
      return result ? result : this.loading;
    },
    ...mapState([
      'loading',
      'error'
    ]),
    ...masGetters([
      'hasError'
    ])
  }
}
</script>