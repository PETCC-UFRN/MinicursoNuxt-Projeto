<template>
	<div>
		<HeaderVeterinario/>
		<div class="container pt-5">
      <div class="mx-auto mt-5">
      	<h1 class="mt-5 mb-4 text-center"> Consultas abertas</h1>
        <b-table striped hover :items="consultas" :fields="campos">
          <template #cell(Ações)="row">
            <b-button size="sm" @click="aceitarConsulta(row.item)" class="mr-2">
              Aceitar consulta
            </b-button>
            <b-button size="sm" @click="recusarConsulta(row.item)" class="mr-2">
              Rejeitar consulta
            </b-button>
          </template> 
        </b-table>
      </div>
    </div>
	</div>
</template>

<script>
export default {
  name: 'Consultas_Abertas',
  data() {
    return {
      consultas: [],
      campos: [
        { key: "pet.name", sortable: true, label: "Pet"  },
        { key: "d_consulta", sortable: true, label: "Data"  },
        { key: "veterinario.name", sortable: true, label: "Veterinario"  },
        { key: "Ações", sortable: false, label: "Ações"  },
      ]
    }
  },
  mounted() {
    this.consumirConsultasAbertasApi();
  },
  methods: {
    consumirConsultasAbertasApi(){
      this.$axios.get("consulta/buscar/")
      .then(res => {
        this.consultas = res.data
        this.consultas = this.consultas.filter(c => c.status == 0)
      })
      .catch(err =>  {
        console.log(err);
      })
    },
    aceitarConsulta(row){
      this.$axios.post("consulta/aprovar/"+row.idConsulta)
      .then(res => {
        this.consumirConsultasAbertasApi();
      })
      .catch(err =>  {
        console.log(err);
      })
    },
    recusarConsulta(row){
      this.$axios.post("consulta/rejeitar/"+row.idConsulta)
      .then(res => {
        this.consumirConsultasAbertasApi();
      })
      .catch(err =>  {
        console.log(err);
      })
    }
  }
}
</script>