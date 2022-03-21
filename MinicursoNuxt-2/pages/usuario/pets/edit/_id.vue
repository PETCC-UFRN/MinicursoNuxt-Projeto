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

	        <b-button type="submit" variant="primary">Submit</b-button>
	      </b-form>
	    </div>
	</div>
</template>

<script>
export default {
  name: 'Pet',
  data(){
		return{
			form: {
		        name: '',
		        d_niver: ''
		      }
		};
	},
	mounted() {
		this.consumirPetApi();
	},
	methods: {
		consumirPetApi(){
			this.$axios.get(`pet/buscar/${this.$route.params.id}`)
			.then(res => {
				this.form = res.data
			})
			.catch(err =>  {
				console.log(err);
			})
		},
		onSubmit(){
	      this.$axios.post("pet/cadastrar/"+this.form.dono.idPessoa, {
	      	idPet: this.$route.params.id,
	        name: this.form.name,
	        d_niver: this.form.d_niver
	      })
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