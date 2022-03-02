<template>
  <v-container>
    <v-row class="text-center pa-3">
      <v-col cols="12">
        <h2 class="pa-3">
          Welcome! 👋 Please select a city from the menu.
        </h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col class="d-flex justify-center pa-3" cols="12">
        <v-img
          max-width="300px"
          max-height="300px"
          src="@/assets/house_lg.png"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "Welcome",
};
</script>
