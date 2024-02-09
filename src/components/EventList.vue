<script>
import { store } from "../store.js" //state management
import register from "../debug" //per debuggare il componente da console

import EventCard from "./EventCard.vue"


export default {
    name: "EventList",
    components: {
        EventCard
    },
    data() {
        return {
            store
        }
    },
    methods: {
        doThings() {
            console.log("AppComponent does things");
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
        <EventCard v-for="evento in store.lista_eventi" :name="evento.name" :date="evento.date"
            :tickets="evento.available_tickets">
        </EventCard>
    </div>
</template>

<style scoped lang="scss">
// importo variabili
// @use './styles/partials/variables' as *;

// ...qui eventuale SCSS di AppComponent
</style>