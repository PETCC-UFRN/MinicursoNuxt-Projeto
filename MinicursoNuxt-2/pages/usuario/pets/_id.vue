<template>
	<div>
		<headerUsuario/>
    	<div class="container pt-5">
			<h1 class="mt-4 mb-2"><nuxt-link to="/usuario/pets/">
			Voltar aos pets</nuxt-link></h1>
			<hr>
			<div class="mt-3 mb-5 ml-2 mr-2">
				<b-row>
					<b-col sm="3">
						<b-avatar aligner="center" size="200px" src="/favicon.ico" ></b-avatar>
					</b-col>
					<b-col>
						<b-row class="mt-2">
							<b-col>
								<h3 class="pt-2">Mel</h3> 
							</b-col>
						</b-row>
						<b-row>
							<b-col class="mt-1 mb-1" cols="12">
								<span><strong>Aniversário:</strong>25/02</span>
							</b-col>
						</b-row>
						<b-row>
							<b-col class="mt-1 mb-1" cols="12">
								<b-button size="sm" @click="solicitarConsulta" class="mr-2">
					              Solicitar consulta
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
  methods: {
    solicitarConsulta(){
      console.log("Consulta solicitada");
    }
  }
}
</script>