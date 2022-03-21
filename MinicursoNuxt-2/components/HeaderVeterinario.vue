<template>
	<div>
	  <b-navbar toggleable="lg" type="light" variant="success">
	    <b-collapse id="nav-collapse" is-nav>
	      <b-navbar-nav>
	      	<b-nav-item to="/veterinario/abertas/">Consultas abertas</b-nav-item>
	        <b-nav-item to="/veterinario/aceitas/">Consultas aceitas</b-nav-item>
	        <b-nav-item to="/veterinario/rejeitadas/">Consultas rejeitadas</b-nav-item>    
	      </b-navbar-nav>
	      <b-navbar-nav class="ml-auto">
	        <b-nav-item to="/">Sair</b-nav-item>
	      </b-navbar-nav>
	    </b-collapse>
	  </b-navbar>
	</div>
</template>

<style>

</style>