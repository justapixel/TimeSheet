<template>
  <v-container class="grey darken-4">
    <h1>TimeSheet</h1>
    <v-simple-table fixed-header height="400">
      <template v-slot:default>
        <thead>
          <tr>
            <th class="text-left">Date</th>
            <th class="text-left">In</th>
            <th class="text-left">Out</th>
            <th class="text-left">Total</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in desserts" :key="item.name">
            <td>{{ item.date }}</td>
            <td><TimePickDialog :timerc=item.time_in @updateTime="item.time_in = $event"/></td>
            <td><TimePickDialog :timerc=item.time_out @updateTime="item.time_out = $event"/></td>
            <td>{{totalday(item)}}</td>
          </tr>
        </tbody>
      </template>
    </v-simple-table>
  </v-container>
</template>

<script>
import TimePickDialog from './TimePickDialog';
import moment from 'moment';

export default {
  name: "TimeSheet",
  components: {
    TimePickDialog
  },
  props: {},
  data() {
    return {
      desserts: [
        {
          date: "01/03",
          name: "Frozen Yogurt",
          calories: 159,
          time_in: "0:00",
          time_out: "0:00"
        },
        {
          date: "02/03",
          name: "Ice cream sandwich",
          calories: 237,
          time_in: null,
          time_out: null
        },
        {
          date: "03/03",
          name: "Eclair",
          calories: 262,
          time_in: null,
          time_out: null
        },
        {
          date: "04/03",
          name: "Cupcake",
          calories: 305,
          time_in: null,
          time_out: null
        },
        {
          date: "05/03",
          name: "Gingerbread",
          calories: 356,
          time_in: null,
          time_out: null
        },
        {
          date: "06/03",
          name: "Jelly bean",
          calories: 375,
          time_in: null,
          time_out: null
        },
        {
          date: "07/03",
          name: "Lollipop",
          calories: 392,
          time_in: null,
          time_out: null
        }
      ]
    };
  },

  methods: {
    totalday: function(date) {
      var start = moment(date.date + " " + date.time_in, 'DD/MM HH-mm');
      var end = moment(date.date + " " + date.time_out, 'DD/MM HH-mm')
      var duration = moment.duration(end.diff(start));
      var hours = duration.asHours();
      return hours.toFixed(2);
    },
  }
};
</script>

<style></style>
