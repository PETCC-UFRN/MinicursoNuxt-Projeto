<template>
	<div>
		<HeaderUsuario/>
		<div class="container pt-5">
	      <div class="mx-auto mt-5">
	      	<h1 class="mt-5 mb-4 text-center"> Consultas solicitadas</h1>
	        <b-table striped hover :items="items"></b-table>
	      </div>
	    </div>
	</div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
      return {
        items: [
          { pet: 'Belinha', estado: 'Em aberto', veterinario_responsável: '' },
          { pet: 'Pandora', estado: 'Aceita', veterinario_responsável: 'Heitor' },
          { pet: 'Scooby', estado: 'Aceita', veterinario_responsável: 'Heitor' },
          { pet: 'Billy', estado: 'Recusada', veterinario_responsável: 'Marcos' }
        ]
      }
    }
}
</script>