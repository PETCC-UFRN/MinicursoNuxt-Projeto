<template>
  <div>
  	<div class="container pt-5">
      <b-form @submit.prevent="onSubmit">

        <b-form-group id="input-group-1" label="Usuário:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.usuario"
            placeholder="Insira seu usuário"
            required
          ></b-form-input>
        </b-form-group>

        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
      <h4 class="mt-4 mb-2"><nuxt-link to="/registroVeterinario">Cadastrar-se</nuxt-link></h4>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      form: {
        usuario: ''
      }
    }
  },
  methods:{
    onSubmit(){
      console.log(this.form);
      this.$router.push('/veterinario/abertas/');
    }
  }
}
</script>