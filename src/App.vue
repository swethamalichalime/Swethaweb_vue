<template>
  <EventHeader/>
  <EventsDirectory :eventsList=eventsList />
</template>

<script>
  import EventHeader from "./components/EventHeader.vue";
  import EventsDirectory from "./components/EventsDirectory.vue";

  export default{
    name: "App",
    components:{
      EventHeader,
      EventsDirectory
    },
    data(){
      return{
        eventsList:[]
      }
    },
    methods:{
      async getEventsList(){
        const res = await fetch("https://swethaweb-node.onrender.com/api");
        const eventsData = await res.json();
        console.log("eventsData" , eventsData[0].events);
        return eventsData[0].events;
      }
    },
    async created(){
        this.eventsList = await this.getEventsList();
    }
  }
</script>

<style scoped>
</style>