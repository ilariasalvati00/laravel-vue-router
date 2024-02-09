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
    <div>
        <h1>{{ name }}</h1>
        <p>Data dell'evento: {{ date }}</p>
        <p>Numero di posti disponibili: {{ tickets }}</p>
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
    border: 1px solid black;
}
</style>