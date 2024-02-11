<script>
import EventList from "../components/EventList.vue"
export default {
    name: "AppHome",
    components: {
        EventList
    },
}
</script>

<template>
    <section>
        <h1 class="mt-5 mb-3">Home</h1>
    </section>
    <main>
        <EventList></EventList>
    </main>
</template>

<style scoped></style>