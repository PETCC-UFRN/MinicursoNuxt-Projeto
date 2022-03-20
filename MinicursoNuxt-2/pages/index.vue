<template>
  <div>
  	<div class="container pt-5">
      <div class="mx-auto mt-5">
      	<h1 class="mt-5 mb-4 text-center"> Bem-vindo! Faça login para continuar</h1>
      	<b-row class="mx-auto" align-h="center">
      		<b-button size="sm" class="mr-2" to="/loginUsuario" variant="info">
				Área do usuário
			</b-button>
			<b-button size="sm" class="mr-2" to="/loginVeterinario" variant="success">
				Área do veterinário
			</b-button>
      	</b-row>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Index'
}
</script>
