<template>
  <v-container>
    <v-row class="text-center pt-3">
      <v-col cols="12">
        <h2 class="pa-3">Properties from {{ displayName }}</h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <div v-if="listingData && listingData.length > 0">
          <Property
            v-for="(listing, index) in listingData"
            :key="index"
            :data="listing"
          />
        </div>
        <p v-else-if="listingData && listingData.length == 0" class="text-center">
          Sorry, no properties available. 😞
        </p>
        <v-progress-circular v-else />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import axios from "axios";
import Property from "./Property.vue";
import { LISTING_API } from "@/api.js";

export default {
  name: "Listing",

  components: {
    Property,
  },

  props: {
    displayName: {
      type: String,
      default: () => "",
    },
    slug: {
      type: String,
      default: () => "",
    },
  },

  watch: {
    slug(oldSlug, newSlug) {
      if (oldSlug !== newSlug) {
        this.getPropertiesAPI(newSlug);
      }
    },
  },

  methods: {
    getPropertiesAPI(marketSlug) {
      axios
        .get(
          LISTING_API, { params: { market__slug: marketSlug } }
        )
        .then((response) => (this.listingData = response.data.results))
        .catch((error) => console.error(error))
        .finally(() => {});
    },
  },

  mounted() {
    this.getPropertiesAPI(this.slug);
  },

  data() {
    return {
      listingData: null,
    };
  },
};
</script>