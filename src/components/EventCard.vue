<script>
import { store } from "../store.js" //state management
import register from "../debug" //per debuggare il componente da console

export default {
    name: "EventCard",
    props: {
        name: String,
        date: String,
        tickets: Number
    },
    data() {
        return {
            store
        }
    },
    methods: {
        doThings() {
            console.log("E does things");
        }
    },
    mounted() {
        register(this); //per debuggare il componente da console
        this.doThings();
    }
}
</script>

<template>
    <div class="card" style="width: 18rem;">
        <div class="card-body">
            <h5 class="card-title">{{ name }}</h5>
            <p class="card-text">Data dell'evento: {{ date }}</p>
            <p class="card-text">Numero di posti disponibili: {{ tickets }}</p>
            <a href="#" class="btn btn-primary">Dettagli evento</a>
        </div>
    </div>
</template>

<style scoped lang="scss">
// importo variabili
// @use './styles/partials/variables' as *;

// ...qui eventuale SCSS di AppComponent
div {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    margin: 1rem;
}
</style>