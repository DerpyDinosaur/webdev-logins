<template>
	<nav>
		<h3 @click="demo=0">Flippy</h3>
		<h3 @click="demo=1">Minimal</h3>
		<h3 @click="demo=2"></h3>
	</nav>
	<FlippyLogin v-if="demo===0"/>
	<Minimal v-if="demo===1"/>
</template>

<script lang="ts">
	import "@fontsource/material-icons";
	import "@fontsource/lato";
	//||
	import FlippyLogin from './components/FlippyLogin.vue'
	import Minimal from './components/Minimal.vue'

	export default{
		name:'app',
		components:{
			FlippyLogin,
			Minimal
		},
		data(){
			return{
				demo: 1
			}
		}
	}
</script>

<style>
	*{
		font-family: "Lato";
		padding: 0;
		margin: 0;
	}

	html{
		background: #272833;
		color: white;
	}

	#app {
		display: flex;
		justify-content: center;
		align-items: center;
		min-height: 100vh;
	}

	nav{
		position: absolute;
		top: 0;
		left: 0;
		margin: 5vh 5vw;
		display: flex;
		justify-content: space-around;
		align-items: center;
	}

	nav h3{
		margin: 0 1vw;
		cursor: pointer;
		font-weight: bold;
	}

	nav h3:hover{
		color: green;
	}
</style>
