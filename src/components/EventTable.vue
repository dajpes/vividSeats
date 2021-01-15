<template>
  <div>
    <table class="table events-table">
      <thead>
        <tr class="events-table-header">
          <th>Event Name</th>
          <th>Date</th>
          <th>Venue</th>
          <th>City</th>
          <th>State</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="{id,name,date,venue} in events" :key="id">
            <td>{{name}}</td>
            <td>{{date}}</td>
            <td>{{venue.name}}</td>
            <td>{{venue.city}}</td>
            <td>{{venue.state}}</td>
        </tr>
      </tbody>
    </table>
    <pre>
        {{events}}
    </pre>
    <!-- <table class="table events-table">
                    <thead>
                        <tr class="events-table-header">
                            <th>Event Name</th>
                            <th>Date</th>
                            <th>Venue</th>
                            <th>City</th>
                            <th>State</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>USC Trojans at Notre Dame Fighting Irish</td>
                            <td>Oct 17 7:30 PM</td>
                            <td>Notre Dame Stadium</td>
                            <td>Notre Dame</td>
                            <td>IN</td>
                        </tr>
                    </tbody>
                </table> -->
  </div>
</template>

<script setup>
import { defineProps } from "vue";

defineProps({
  events: {
    type: Array,
    default: () => {
      [];
    },
  },
});
</script>
