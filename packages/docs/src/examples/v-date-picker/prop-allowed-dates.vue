<template>
  <v-container>
    <v-row justify="space-around">
      <v-date-picker
        v-model="date"
        :allowed-dates="allowedDates"
        min="2016-06-15"
        max="2018-03-20"
      ></v-date-picker>
    </v-row>
  </v-container>
</template>

<script setup>
  import { useDate } from 'vuetify/labs/date'
  import { ref } from 'vue'

  const adapter = useDate()

  const date = ref('2018-03-02')

  function allowedDates (val) {
    return parseInt(adapter.toISO(val).split('-')[2], 10) % 2 === 0
  }
</script>

<script>
  import { useDate } from 'vuetify/labs/date'

  const adapter = useDate()

  export default {
    data: () => ({
      date: '2018-03-02',
    }),

    methods: {
      allowedDates: val => {
        return parseInt(adapter.toISO(val).split('-')[2], 10) % 2 === 0
      },
    },
  }
</script>
