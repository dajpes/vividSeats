<template>
  <div v-if="state.Events.length">
    THERE ARE EVENTS
    <div>
      <InputValue @filterEvent="processFilter"/>
    </div>
    <EventTable :events="state.Events" />
  </div>
  <div v-else>NO EVENTS</div>
</template>

<script setup>
import axios from "axios";
import EventTable from "./EventTable.vue";
import InputValue from "./InputValue.vue";
import { reactive } from "vue";
const state = reactive({
  Events: [],
});

const processFilter = (data) =>{
    console.log('Data from input: ',data);
}

const getEvents = () => {
  axios
    .get("http://localhost:8080/events")
    .then((e) => {
      state.Events = e.data;
    })
    .catch((e) => console.log("Error feteching events:", e));
};

getEvents();
</script>
