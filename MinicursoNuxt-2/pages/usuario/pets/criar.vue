<template>
  <div>
    <headerUsuario/>
    <div class="container pt-5">
      <h1 class="mt-5 mb-4 text-center">Insira os dados do seu pet</h1> 
      <b-form @submit.prevent="onSubmit">

        <b-form-group id="input-group-1" label="Nome:" label-for="input-1">
          <b-form-input
            id="input-1"
            v-model="form.name"
            placeholder="Insira o nome do pet"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-2" label="Aniversário:" label-for="input-2">
          <b-form-input
            id="input-2"
            v-model="form.d_niver"
            placeholder="Insira a data de aniversário do pet"
            type="date"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group id="input-group-1" label="Dono:" label-for="input-1">
            <b-form-select 
              id="input-2"
              v-model="selected" 
              :options="options"
              required
            ></b-form-select>
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
      selected: null,
      donos: [],
      form: {
        name: '',
        d_niver: ''
      },
      options: [
        {value: null, text: "Escolha o dono do pet"}
      ]
    }
  },
  mounted() {
    this.consumirDonosApi();
  },
  methods: {
    consumirDonosApi(){
      this.$axios.get("dono/buscar/")
      .then(res => {
        this.donos = res.data
        this.donos.forEach((value, index) => {
            this.options.push({
            value: value.idPessoa,
            text: value.name
          })
        });
      })
      .catch(err =>  {
        console.log(err);
      })
    },
    onSubmit(){
      console.log(this.form);
      this.$axios.post("pet/cadastrar/"+this.selected, this.form)
      .then(res => {
        this.$router.push('/usuario/pets');
      })
      .catch(err => {
        console.log(err)
      });
    }
  }
}
</script>