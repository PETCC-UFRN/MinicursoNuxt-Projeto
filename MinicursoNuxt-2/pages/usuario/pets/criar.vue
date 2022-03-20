<template>
  <div>
    <headerUsuario/>
    <div class="container pt-5">
      <h1 class="mt-5 mb-4 text-center">Insira os dados do seu pet</h1> 
      <b-form @submit.prevent="onSubmit">

        <b-form-group id="input-group-1" label="Nome:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.nome"
            placeholder="Insira o nome do pet"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Aniversário:" label-for="input-2">
          <b-form-input
            id="input-2"
            v-model="form.aniversario"
            placeholder="Insira a data de aniversário do pet"
            type="date"
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
        usuario: '',
        aniversario: ''
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