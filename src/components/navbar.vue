<template>
	<nav>
		<v-toolbar  text color="blue-grey lighten-5">
			<v-app-bar-nav-icon class="gray--text" @click="changeValue"></v-app-bar-nav-icon>
			<v-toolbar-title class="text-uppercase cyan--text text--lighten-1">
				<span class="font-weight-light">Todo</span>
				<span>Vuetify</span>
			</v-toolbar-title>
			<v-spacer></v-spacer>
			<v-btn color="cyan lighten-4">
				<span>Sign out</span>
				<v-icon>exit_to_app</v-icon>
			</v-btn>
		</v-toolbar>
	</nav>
</template>

<script>
import { bus } from "@/main";

export default {
    name: 'navbar',
    
	props: {
		drawer: {
			type: Boolean
		}
	},
	data() {
		return {
			openDrawer: this.drawer
		};
	},
	methods: {
		changeValue () {
			this.openDrawer = !this.openDrawer;
			bus.$emit('action', this.openDrawer);
		}
	}
};
</script>
