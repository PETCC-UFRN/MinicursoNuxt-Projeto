<template>
  <div>
    <div class="container pt-5">
      <b-form @submit.prevent="onSubmit">

        <b-form-group id="input-group-1" label="Nome:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.name"
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

        <b-form-group id="input-group-3" label="Registro:" label-for="input-3">
          <b-form-input
            id="input-3"
            v-model="form.registro"
            placeholder="Insira seu registro"
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
        name: '',
        email: '',
        registro: ''
      }
    }
  },
  methods:{
    onSubmit(){
      console.log(this.form);
      this.$axios.post("veterinario/cadastrar/", this.form)
      .then(res => {
        this.$router.push('/veterinario/abertas');
      })
      .catch(err => {
        console.log(err)
      });
    }
  }
}
</script>