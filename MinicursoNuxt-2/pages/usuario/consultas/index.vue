<template>
	<div>
		<HeaderUsuario/>
		<div class="container pt-5">
	      <div class="mx-auto mt-5">
	      	<h1 class="mt-5 mb-4 text-center"> Consultas solicitadas</h1>
	        <b-table striped hover :items="consultas" :fields="campos">
              <template #cell(status)="row">
                  {{traduzirStatus(row.item.status)}}
              </template> 
          </b-table>
	      </div>
	    </div>
	</div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      consultas: [],
      campos: [
        { key: "pet.name", sortable: true, label: "Pet"  },
        { key: "d_consulta", sortable: true, label: "Data"  },
        { key: "status", sortable: true, label: "Estado"  },
        { key: "veterinario.name", sortable: true, label: "Veterinario"  },
      ]
    }
  },
  mounted() {
    this.consumirConsultasApi();
  },
  methods: {
    consumirConsultasApi(){
      this.$axios.get("consulta/buscar/")
      .then(res => {
        this.consultas = res.data
      })
      .catch(err =>  {
        console.log(err);
      })
    },
    traduzirStatus(item){
      if(item == 0){
        return "Em aberto"
      }
      else if (item == 1){
        return "Aceita"
      }
      else{
        return "Rejeitada"
      }
    }
  }
}
</script>