<template>
	<div class="flip-card">
		<input class="checkbox" type="checkbox">
		<div class="wrap">
			<div class="front">
				<div class="form paralax">
					<h2>Login</h2>
					<div class="form-block">
						<span class="material-icons">fingerprint</span>
						<input type="text" name="user" placeholder="Username">
					</div>
					<div class="form-block">
						<span class="material-icons">password</span>
						<input type="password" name="pass" placeholder="Password">
					</div>
					<button>Submit</button>
				</div>
			</div>

			<div class="back">
				<div class="form paralax">
					<h2>Register</h2>
					<div class="form-block">
						<h3 style="text-align: center;">Microsoft</h3>
					</div>
					<div class="form-block">
						<h3 style="text-align: center;">Google</h3>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script lang="ts">
	export default{
		name: 'LeanFlippyLogin'
	}
</script>

<style scoped>
	.flip-card{
		width: 20vw;
		height: 20vw;
		-webkit-transform-style: preserve-3d;
		transform-style: preserve-3d;
		perspective: 1000px;
	}

	.wrap{
		position: relative;
		width: 100%;
		height: 100%;
		transition: all 600ms ease-out;
		-webkit-transform-style: preserve-3d;
		transform-style: preserve-3d;
	}

	.checkbox{
		margin: 1vh 0;
	}
	.checkbox:checked ~ .wrap{
		transform: rotateY(180deg);
	}

	.front, .back {
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0;
		top: 0;
		display: flex;
		justify-content: left;
		align-items: center;
		-webkit-transform-style: preserve-3d;
		transform-style: preserve-3d;
		border-radius: 12px;
	}

	.front {
		background-color: #00B6D8;
		color: white;
	}

	.back {
		background-color: #00B6D8;
		color: white;
		transform: rotateY(180deg);
	}

	.paralax{
		padding: 0 2vw;
		transform: translate3d(0, 0, 50px) perspective(100px);
	}

	.form{
		width: 100%;
		display: grid;
		grid-gap: 1vh;
		grid-template-rows: 2fr 1fr 1fr 2fr;
		align-items: center;
		-webkit-font-smoothing: antialiased;
	}

	.form h2{
		text-align: center;
	}

	.form .form-block{
		display: flex;
		align-items: center;
		background: white;
		color: black;
		padding: 0.5vw;
		border-radius: 12px;
	}
	.form .form-block h3{
		width: 100%;
		text-align: center;
		padding: 0;
	}

	.form .form-block *:first-child{
		padding: 0 1vw 0 0;
	}
	.form .form-block input{
		width: 100%;
		border: none;
		background: none;
		outline: none;
	}

	.form button{
		width: 50%;
		height: 5vh;
		margin: auto;
	}
</style>