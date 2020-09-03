<template>
  <q-page padding class="flex flex-center">
    <div class="row col-12">
      <q-card class="col-12">
        <q-section-card>
          <div class="text-h6"> TodoList - Login</div>
        </q-section-card>
        <q-card-section class="row q-col-gutter-md q-pr-none">
          <div class="q-col-gutter-sm q-pr-none col-12 row">
            <q-input class="col-12" filled v-model="user.login" label="Login"></q-input>
            <q-input class="col-12" filled type="password" v-model="user.senha" label="Senha"></q-input>
          </div>
        </q-card-section>
        <q-card-section class="col-12 text-right">
          <q-btn label="Cadastrar" class="q-mr-sm" to="/controle/sign-up" color="secondary"/>
          <q-btn label="Login" @click="logar" color="primary"/>
        </q-card-section>
      </q-card>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'Login',
  data () {
    return {
      user: {
        login: '',
        senha: ''
      }
    }
  },
  methods: {
    logar () {
      this.$q.notify({
        message: 'Usuario Logado com Sucesso',
        color: 'positive'
      })
      this.$router.push('/')
    }
  }
}
</script>
