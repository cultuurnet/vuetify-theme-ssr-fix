<template>
  <v-container
    id="input-usage"
    fluid
  >
    <v-row>
      <v-col cols="12">
        <v-input
          :messages="['Messages']"
          append-icon="mdi-close"
          prepend-icon="mdi-phone"
          @click:append="appendIconCallback"
          @click:prepend="prependIconCallback"
        >
          Default Slot
        </v-input>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
  function appendIconCallback () {
    alert('click:append')
  }
  function prependIconCallback () {
    alert('click:prepend')
  }
</script>

<script>
  export default {
    methods: {
      appendIconCallback () {
        alert('click:append')
      },
      prependIconCallback () {
        alert('click:prepend')
      },
    },
  }
</script>

<style>
  #input-usage .v-input__prepend-outer,
  #input-usage .v-input__append-outer,
  #input-usage .v-input__slot,
  #input-usage .v-messages {
    border: 1px dashed rgba(0,0,0, .4);
  }
</style>
