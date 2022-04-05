<template>
  <v-app>
    <v-app-bar app elevation="5">
      <div class="d-flex align-center">
        <h1 class="font-weight-bold">Bungalow 🏠</h1>
      </div>

      <v-spacer></v-spacer>

      <v-menu class="d-flex">
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            v-if="selectedMarketData"
            color="primary"
            v-bind="attrs"
            v-on="on"
            class="d-flex"
          >
            <v-img
              height="25px"
              max-width="25px"
              :src="selectedMarketData.img_md"
              lazy-src="@/assets/placeholder.svg"
            />
            <div class="pa-2">{{ selectedMarketData.display_name }}</div>
          </v-btn>
          <v-btn v-else color="primary" v-bind="attrs" v-on="on">
            Where would you like to live? 💭
          </v-btn>
        </template>
        <v-list v-for="(market, index) in marketData" :key="index">
          <v-list-item @click="setSelectedMarket(market)">
            <v-list-item-avatar>
              <v-img :src="market.img_md" lazy-src="@/assets/placeholder.svg" />
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title>{{ market.display_name }}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <v-main>
      <Listing v-if="selectedMarketData" :slug="selectedMarketData.slug" :displayName="selectedMarketData.display_name" />
      <Welcome v-else />
    </v-main>
  </v-app>
</template>

<script>
import axios from "axios";
import Listing from "./components/Listing";
import Welcome from "./components/Welcome";
import { MARKETS_API } from "@/api.js";

export default {
  name: "App",

  components: {
    Listing,
    Welcome,
  },

  data() {
    return {
      marketData: null,
      selectedMarketData: null,
      marketSlug: null,
    };
  },

  mounted() {
    this.getMarketsAPI();
  },

  methods: {
    getMarketsAPI() {
      axios
        .get(MARKETS_API)
        .then((response) => (this.marketData = response.data.results))
        .catch((error) => console.error(error))
        .finally(() => {});
    },
    setSelectedMarket(selectedMarketData) {
      this.selectedMarketData = selectedMarketData;
      this.marketSlug = selectedMarketData.slug;
    },
  },
};
</script>