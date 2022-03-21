<template>
	<div>
		<HeaderVeterinario/>
		<div class="container pt-5">
      <div class="mx-auto mt-5">
      	<h1 class="mt-5 mb-4 text-center"> Consultas rejeitadas</h1>
        <b-table striped hover :items="consultas" :fields="campos">
          <template #cell(Ações)="row">
            <b-button size="sm" @click="aceitarConsulta(row.item)" class="mr-2">
              Aceitar consulta
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
    this.consumirConsultasRejeitadasApi();
  },
  methods: {
    consumirConsultasRejeitadasApi(){
      this.$axios.get("consulta/buscar/")
      .then(res => {
        this.consultas = res.data
        this.consultas = this.consultas.filter(c => c.status == 2)
      })
      .catch(err =>  {
        console.log(err);
      })
    },
    aceitarConsulta(row){
      this.$axios.post("consulta/aprovar/"+row.idConsulta)
      .then(res => {
        this.consumirConsultasRejeitadasApi();
      })
      .catch(err =>  {
        console.log(err);
      })
    }
  }
}
</script>