<template>
	<div>
		<HeaderVeterinario/>
		<div class="container pt-5">
      <div class="mx-auto mt-5">
      	<h1 class="mt-5 mb-4 text-center"> Consultas abertas</h1>
        <b-table striped hover :items="items" :fields="fields">
          <template #cell(Ações)="row">
            <b-button size="sm" @click="aceitarConsulta(row.item)" class="mr-2">
              Aceitar consulta
            </b-button>
            <b-button size="sm" @click="recusarConsulta(row.item)" class="mr-2">
              Recusar consulta
            </b-button>
          </template> 
        </b-table>
      </div>
    </div>
	</div>
</template>

<script>
export default {
  name: 'Consultas Abertas',
  data() {
    return {
      fields: ['pet', 'responsável', 'Ações'],
      items: [
        { pet: 'Belinha', responsável: 'Danilo' },
        { pet: 'Bethoven', responsável: 'Júlia' },
        { pet: 'Scott', responsável: 'Jefferson' },
      ]
    }
  },
  methods: {
    aceitarConsulta(row){
      console.log("Consulta de "+row.pet+" aceita");
      const index= this.items.indexOf(row);
      this.items.splice(index, 1);
    },
    recusarConsulta(row){
      console.log("Consulta de "+row.pet+" recusada");
      const index= this.items.indexOf(row);
      this.items.splice(index, 1);
    }
  }
}
</script>