<template>
	<nav class="navbar navbar-expand-md navbar-light bg-white shadow-sm mb-3">
		<a
			class="navbar-brand"
			href="/"
		>
			Single Page Application
		</a>
		<button
			class="navbar-toggler"
			type="button"
			data-toggle="collapse"
			data-target="#navbarCollapse"
			aria-controls="navbarCollapse"
			aria-expanded="false"
		>
			<span class="navbar-toggler-icon"></span>
		</button>
		<div
			class="collapse navbar-collapse"
			id="navbarCollapse"
		>
			<div
				v-if="isLogged"
				class="ml-auto navbar-nav"
			>
				<li class="nav-item">
					<router-link
						:to="{name: 'Home'}"
						tag="a"
						:class="['nav-link']"
					>Home</router-link>
				</li>
				<li class="nav-item">
					<router-link
						:to="{name: 'About'}"
						tag="a"
						:class="['nav-link']"
					>About</router-link>
				</li>
				<li class="nav-item">
					<a
						href="#"
						@click="logout()"
						:class="['nav-link']"
					>Logout</a>
				</li>
			</div>
			<div
				v-if="!isLogged"
				class="ml-auto navbar-nav"
			>
				<li class="nav-item">
					<router-link
						:to="{name: 'Login'}"
						tag="a"
						:class="['nav-link', '']"
					>Login</router-link>
				</li>
				<li class="nav-item">
					<router-link
						:to="{name: 'Register'}"
						tag="a"
						:class="['nav-link']"
					>Register</router-link>
				</li>
			</div>
		</div>
	</nav>
</template>
<script>
import { mapGetters } from "vuex";

export default {
	computed: {
		...mapGetters(["isLogged"]),
	},
	methods: {
		logout() {
			this.$store.dispatch("logout");
		},
	},
};
</script>

<style>
</style>