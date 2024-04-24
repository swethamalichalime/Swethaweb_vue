<template>
     <div class="events-container">
        <div v-for="event of eventsList" :key="event?.event_id">
            <SingleEvent :event=event />
        </div>
    </div>
</template>

<script>
import SingleEvent from "./SingleEvent.vue";

    export default{
        name: "EventsDirectory",
        components:{
            SingleEvent
        },
        props:{
            eventsList: Array
        }
    }
</script>

<style scoped>
    .events-container{
        display: grid;
        grid-template-columns: auto auto auto;
        gap:10px;
    }
</style>