<template>
  <v-card elevation="5" class="pa-3">
    <v-card-title class="text-center">{{ data.headline }}</v-card-title>
    <v-carousel v-if="data.images">
      <v-carousel-item v-for="(image, index) in data.images" :key="index">
        <v-img :src="image.sm_url" lazy-src="@/assets/placeholder.svg" />
      </v-carousel-item>
    </v-carousel>
    <v-image v-else src="@/assets/placeholder.svg" />
    <v-card-text>
      <v-list>
        <v-list-item v-if="data.street_address">
          <v-list-item-icon>
            <v-icon color="black"> mdi-home-circle </v-icon>
          </v-list-item-icon>
          <v-list-item-content>{{ data.street_address }}</v-list-item-content>
        </v-list-item>
        <v-list-item v-if="data.address.neighborhood">
          <v-list-item-icon>
            <v-icon color="black"> mdi-map-outline </v-icon>
          </v-list-item-icon>
          <v-list-item-content>{{
            data.address.neighborhood
          }}</v-list-item-content>
        </v-list-item>
        <v-list-item
          v-if="
            (data.amenities && data.amenities.length > 0) ||
            (data.room_amenities && data.room_amenities.length > 0)
          "
        >
          <v-list-item-icon>
            <v-icon color="black"> mdi-plus </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Amenities</v-list-item-title>
            <div>
              <v-chip
                class="ma-2"
                x-small
                v-for="(amenity, index) in data.amenities"
                :key="index"
              >
                {{ amenity.display_name }}
              </v-chip>
              <v-chip
                class="ma-2"
                x-small
                v-for="(room_amenity, index) in data.room_amenities"
                :key="index"
              >
                {{ room_amenity }}
              </v-chip>
            </div>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon color="black"> mdi-bed </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Number of bedrooms</v-list-item-title>
            <v-list-item-content>{{
              data.total_room_count
            }}</v-list-item-content>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon color="black"> mdi-bed-empty </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Number of available bedrooms</v-list-item-title>
            <v-list-item-content>{{
              data.available_room_count
            }}</v-list-item-content>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon color="black"> mdi-car </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Parking spots available</v-list-item-title>
            <v-list-item-content>{{
              data.parking_spots_available
            }}</v-list-item-content>
          </v-list-item-content>
        </v-list-item>
        <v-list-item>
          <v-list-item-icon>
            <v-icon color="black"> mdi-currency-usd </v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>Room prices</v-list-item-title>
            <div>
              <v-chip
                class="ma-2"
                x-small
                v-for="(price, index) in data.room_prices"
                :key="index"
              >
                ${{ price }}
              </v-chip>
            </div>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-card-text>
  </v-card>
</template>

<script>
export default {
  name: "Property",

  components: {},

  props: {
    data: {
      type: Object,
      default: () => {},
    },
  },
};
</script>