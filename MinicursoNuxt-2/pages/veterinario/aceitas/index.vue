<template>
	<div>
		<HeaderVeterinario/>
		<div class="container pt-5">
	      <div class="mx-auto mt-5">
	      	<h1 class="mt-5 mb-4 text-center"> Consultas aceitas</h1>
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
          { pet: 'Pandora', responsável: 'Danilo' },
          { pet: 'Scooby', responsável: 'Danilo' },
          { pet: 'Bobby', responsável: 'Leandro' },
        ]
      }
    }
}
</script>