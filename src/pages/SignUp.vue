<template>
  <q-page padding class="flex flex-center row">
   <div class="row col-10">
    <q-card bordered class="bg-grey-1 col-12">
      <q-card-section>
        <div class="row items-center no-wrap">
          <div class="col-12">
            <div class="text-h6 text-center">TodoList - Cadastro</div>
          </div>
        </div>
      </q-card-section>

      <q-card-section>
        <div class="row col-12">
         <q-input v-model="novoUsuario.nome" class="col-12 q-mb-sm" outlined label="Informe Seu Nome">
         </q-input>
         <q-input v-model="novoUsuario.email" class="col-12 q-mb-sm" type="email" outlined label="Informe Seu E-mail">
         </q-input>
        </div>
        <div class="text-center">
         <q-btn flat class="text-caption q-pa-nome q-ma-nome" to="/controle" >já Sou Cadastrado</q-btn>
        </div>
      </q-card-section>

      <q-separator />

      <q-card-actions>
       <div class="text-right col-12">
        <q-btn color="primary" label="Cadastrar" @click="createUser "/>
       </div>
      </q-card-actions>
    </q-card>
    </div>
  </q-page>
</template>

<script>
export default {
  name: 'SignUp',
  data () {
    return {
      novoUsuario: {
        nome: '',
        email: ''
      }
    }
  },
  methods: {
    createUser () {
      this.$axios.post('http://localhost:3000/usuarios', this.novoUsuario).then(response => {
        console.log(response.data)
      })
    }
  }
}
</script>
