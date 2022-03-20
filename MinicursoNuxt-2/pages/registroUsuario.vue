<template>
  <div>
    <div class="container pt-5">
      <b-form @submit.prevent="onSubmit">

        <b-form-group id="input-group-1" label="Nome:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.nome"
            placeholder="Insira seu nome"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Email:" label-for="input-2">
          <b-form-input
            id="input-2"
            v-model="form.email"
            placeholder="Insira seu email"
            type="email"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-3" label="Telefone:" label-for="input-3">
          <b-form-input
            id="input-3"
            v-model="form.telefone"
            placeholder="Insira seu telefone"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-4" label="Endereço:" label-for="input-4">
          <b-form-input
            id="input-4"
            v-model="form.endereco"
            placeholder="Insira seu endereço"
            required
          ></b-form-input>
        </b-form-group>

        <b-button type="submit" variant="primary">Submit</b-button>
      </b-form>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Registro',
  data() {
    return {
      form: {
        nome: '',
        email: '',
        telefone: '',
        endereço: ''
      }
    }
  },
  methods:{
    onSubmit(){
      console.log(this.form);
      this.$router.push('/usuario/pets');
    }
  }
}
</script>