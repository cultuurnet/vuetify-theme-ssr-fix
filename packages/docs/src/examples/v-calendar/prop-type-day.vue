<template>
  <v-row>
    <v-col>
      <v-sheet height="400">
        <v-calendar color="primary" type="day">
          <template v-slot:day-header="{ present }">
            <div v-if="present" class="text-center">
              Today
            </div>
          </template>

          <template v-slot:interval="{ hour }">
            <div class="text-center">
              {{ hour }} o'clock
            </div>
          </template>
        </v-calendar>
      </v-sheet>
    </v-col>
  </v-row>
</template>
