<template>
	<div>
		<HeaderUsuario/>
	    <div class="container pt-5">
	      <div class="mx-auto mt-5">
	        <h1 class="mt-5 mb-4 text-center">Pets</h1>
	        <b-row class="mx-auto">
	        	<b-button size="sm" to="criar" class="mr-2">
	              Adicionar novo pet
	            </b-button>
	        </b-row>
	        <b-table striped hover :items="pets" :fields="campos">
	        	<template #cell(Ações)="row">
		            <b-button size="sm"class="mr-2" :to="`/usuario/pets/${row.item.idPet}`">
		              Ver detalhes
		            </b-button>
		        </template>
	        </b-table>
	      </div>
	    </div>
	  </div>
</template>

<script>
export default {
	name: 'Pets',
	data(){
		return{
			pets: [],
			campos: [
				{ key: "name", sortable: true, label: "Nome"  },
				{ key: "dono.name", sortable: true, label: "Dono"  },
				{ key: "Ações", sortable: false, label: "Ações"  }
			]
		};
	},
	mounted() {
		this.consumirPetsApi();
	},
	methods: {
		consumirPetsApi(){
			this.$axios.get("pet/buscar/")
			.then(res => {
				this.pets = res.data
			})
			.catch(err =>  {
				console.log(err);
			})
		}
	}
}
</script>

<style scoped>
.nome {
  font-size: 17px;
  font-weight: 300;
  background: white;
  border-radius: 5px;
  margin-right: 10px;
}
</style>