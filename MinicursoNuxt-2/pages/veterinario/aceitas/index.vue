<template>
	<div>
		<HeaderVeterinario/>
		<div class="container pt-5">
      <div class="mx-auto mt-5">
      	<h1 class="mt-5 mb-4 text-center"> Consultas aceitas</h1>
        <b-table striped hover :items="consultas" :fields="campos">
          <template #cell(Ações)="row">
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
  name: 'IndexPage',
  data() {
    return {
      consultas: [],
      campos: [
        { key: "pet.name", sortable: true, label: "Pet"  },
        { key: "d_consulta", sortable: true, label: "Data"  },
        { key: "pet.dono.name", sortable: true, label: "Dono"  },
        { key: "veterinario.name", sortable: true, label: "Veterinario"  },
        { key: "Ações", sortable: false, label: "Ações"  },
      ]
    }
  },
  mounted() {
    this.consumirConsultasAceitasApi();
  },
  methods: {
    consumirConsultasAceitasApi(){
      this.$axios.get("consulta/buscar/")
      .then(res => {
        this.consultas = res.data
        this.consultas = this.consultas.filter(c => c.status == 1)
      })
      .catch(err =>  {
        console.log(err);
      })
    },
    recusarConsulta(row){
      this.$axios.post("consulta/rejeitar/"+row.idConsulta)
      .then(res => {
        this.consumirConsultasAceitasApi();
      })
      .catch(err =>  {
        console.log(err);
      })
    }
  }
}
</script>