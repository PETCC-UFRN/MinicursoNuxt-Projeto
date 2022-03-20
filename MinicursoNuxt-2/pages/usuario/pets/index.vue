<template>
	<div>
		<HeaderUsuario/>
	    <div class="container pt-5">
	      <div class="mx-auto mt-5">
	        <h1 class="mt-5 mb-4 text-center"> Seus pets</h1>
	        <b-row class="mx-auto">
	        	<b-button size="sm" to="criar" class="mr-2">
	              Adicionar novo pet
	            </b-button>
	        </b-row>  
	        <div class="pt-5 mb-4">
	            <b-row class="mx-auto" align-h="center">
		            <div>
		                <b-col class="mt-2 mb-2 ml-2 mr-2">
		                <nuxt-link to="/usuario/pets/1">
		                    <b-avatar size="190px" src="/favicon.ico">
		                    </b-avatar>
		                <b-row class="mt-2" align-h="center">
		                    <p class="nome pt-2 pb-2 pr-2 pl-2" style="text-align: justify">Mel</p>
		                    </b-row>
		                </nuxt-link>
		                </b-col>
		            </div>
		            <div>
		                <b-col class="mt-2 mb-2 ml-2 mr-2">
		                <nuxt-link to="#">
		                    <b-avatar size="190px" src="/favicon.ico">
		                    </b-avatar>
		                <b-row class="mt-2" align-h="center">
		                    <p class="nome pt-2 pb-2 pr-2 pl-2" style="text-align: justify">Belinha</p>
		                    </b-row>
		                </nuxt-link>
		                </b-col>
		            </div>
		            <div>
		                <b-col class="mt-2 mb-2 ml-2 mr-2">
		                <nuxt-link to="#">
		                    <b-avatar size="190px" src="/favicon.ico">
		                    </b-avatar>
		                <b-row class="mt-2" align-h="center">
		                    <p class="nome pt-2 pb-2 pr-2 pl-2" style="text-align: justify">Scooby</p>
		                    </b-row>
		                </nuxt-link>
		                </b-col>
		            </div>
		            <div>
		                <b-col class="mt-2 mb-2 ml-2 mr-2">
		                <nuxt-link to="#">
		                    <b-avatar size="190px" src="/favicon.ico">
		                    </b-avatar>
		                <b-row class="mt-2" align-h="center">
		                    <p class="nome pt-2 pb-2 pr-2 pl-2" style="text-align: justify">Pingo</p>
		                    </b-row>
		                </nuxt-link>
		                </b-col>
		            </div>
		            <div>
		                <b-col class="mt-2 mb-2 ml-2 mr-2">
		                <nuxt-link to="#">
		                    <b-avatar size="190px" src="/favicon.ico">
		                    </b-avatar>
		                <b-row class="mt-2" align-h="center">
		                    <p class="nome pt-2 pb-2 pr-2 pl-2" style="text-align: justify">Pandora</p>
		                    </b-row>
		                </nuxt-link>
		                </b-col>
		            </div>
		            <div>
		                <b-col class="mt-2 mb-2 ml-2 mr-2">
		                <nuxt-link to="#">
		                    <b-avatar size="190px" src="/favicon.ico">
		                    </b-avatar>
		                <b-row class="mt-2" align-h="center">
		                    <p class="nome pt-2 pb-2 pr-2 pl-2" style="text-align: justify">Billy</p>
		                    </b-row>
		                </nuxt-link>
		                </b-col>
		            </div>
	            </b-row>
	        </div>
	      </div>
	    </div>
	  </div>
</template>

<script>
export default {
  name: 'Pets'
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