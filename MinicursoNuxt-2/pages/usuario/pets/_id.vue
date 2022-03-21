<template>
	<div>
		<headerUsuario/>
    	<div class="container pt-5">
			<h3 class="mt-4 mb-2"><nuxt-link to="/usuario/pets/">
			Voltar aos pets</nuxt-link></h3>
			<hr>
			<div class="mt-3 mb-5 ml-2 mr-2">
				<b-row>
					<b-col>
						<b-row class="mt-2">
							<b-col>
								<h1 class="pt-2">{{pet.name}}</h1> 
							</b-col>
						</b-row>
						<b-row>
							<b-col class="mt-1 mb-1" cols="12">
								<span><strong>Aniversário: </strong>{{pet.d_niver}}</span>
							</b-col>
						</b-row>
						<b-row>
							<b-col class="mt-1 mb-1" cols="12">
								<span><strong>Dono: </strong>{{pet.dono.name}}</span>
							</b-col>
						</b-row>
						<b-row>
							<b-col class="mt-1 mb-1" cols="12">
								<b-button size="sm" class="mr-2":to="`/usuario/pets/consulta/${pet.idPet}`">
					              Solicitar consulta
					            </b-button>
					            <b-button size="sm" variant="warning" class="mr-2" :to="`/usuario/pets/edit/${pet.idPet}`">
					              Editar
					            </b-button>
					            <b-button size="sm" variant="danger" @click="excluir" class="mr-2">
					              Excluir
					            </b-button>
							</b-col>
						</b-row>
					</b-col>
				</b-row>
			</div>
		</div>
	</div>
</template>

<script>
export default {
  name: 'Pet',
  data(){
		return{
			pet: {
				idPet: 0,
				name: '',
				d_niver: '',
				dono: {
					name: ''
				}
			},
		};
	},
	mounted() {
		this.consumirPetApi();
	},
	methods: {
		consumirPetApi(){
			this.$axios.get(`pet/buscar/${this.$route.params.id}`)
			.then(res => {
				this.pet = res.data
			})
			.catch(err =>  {
				console.log(err);
			})
		},
	    excluir(){
	    	this.$axios.delete(`pet/remover/${this.$route.params.id}`)
			.then(res => {
				this.$router.push('/usuario/pets');
			})
			.catch(err =>  {
				console.log(err);
			})
	    }
	}
}
</script>