<script>
import AppComponent from "./components/AppComponent.vue"
import EventList from "./components/EventList.vue"

import axios from 'axios'; //importo Axios
import { store } from "./store.js" //state management

export default {
	components: {
		AppComponent,
		EventList
	},
	data() {
		return {
			store
		}
	},
	mounted() {
		this.doThings();

		axios.get("http://localhost:8000/api/events").then(risultato => {
			console.log(risultato.data.results);
			store.lista_eventi = risultato.data.results
		}).catch(errore => {
			console.error(errore);
		});
	},
	methods: {
		doThings() {
			console.log("App.vue does things");
		}
	}
}
</script>

<template>
	<main>
		<EventList></EventList>
	</main>
</template>

<style lang="scss">
// importo il foglio di stile generale dell'applicazione, non-scoped
@use './styles/general.scss';
</style>

<style scoped lang="scss">
// importo variabili
// @use './styles/partials/variables' as *;

// ...qui eventuale SCSS di App.vue
main {
	padding: 1rem;
}
</style>