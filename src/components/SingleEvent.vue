<template>
    <div class="event-card">
        <div class="event-photo">
            <img :src=event.event_image alt="Event Photo"/>
        </div>
        <div class="event-details">
            <h3 class="event-name">{{event.event_name}}</h3>
            <h3 class="grid-item">${{event.event_price}}</h3>
            <p class="row2">{{event.event_description}}</p>
            <p><img src="https://img.icons8.com/?size=24&id=85102&format=png" alt="Calendar Icon"/>{{event.event_date}}</p>
            <p><img src="https://img.icons8.com/?size=24&id=QECUQIt2LlW8&format=png" alt="Time Icon"/>{{event.event_time}}</p>
            <p class="row2"><img src="https://img.icons8.com/?size=24&id=85149&format=png" alt="Location Icon"/>{{event.event_location}}</p>
        </div>
    </div>
</template>

<script>
    export default{
        name: "SingleEvent",
        props:{
            event:Object
        }
    }
</script>

<style scoped>
    @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap');

    .event-card{
        display: flex;
        flex-direction:column;
        align-items:center;
        border:transparent;
        border-radius: 4px;
        padding: 10px;
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
    }
    .event-details{
        display:grid;
        grid-template-columns: auto auto;
        gap: 10px;
        justify-content: space-between;
    }
    .event-details .row2{
        grid-column: 1 / -1;
    }
    .event-details img{
        vertical-align: middle; 
    }
    .grid-item{
        text-align: right;
    }
    .event-photo{
        width:100%;
    }
    .event-photo img{
        width:100%;
        height:300px;
        object-fit: cover;
    }
    .event-name{
        font-family: "Playfair Display", serif;
    }
</style>