<template>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <v-card color="green darken-2">
        <v-card-title class="text-h5"> Unlimited music now </v-card-title>

        <v-card-subtitle
          >Listen to your favorite artists and albums whenever and wherever,
          online and offline.</v-card-subtitle
        >

        <v-card-actions>
          <v-btn text> Listen Now </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>

    <v-col v-for="(item, i) in items" :key="i" cols="12" class="my-0">
      <v-card :color="item.color" dark>
        <div class="d-flex flex-no-wrap justify-space-between">
          <div>
            <v-card-title class="text-h5" v-text="item.title"></v-card-title>

            <v-card-subtitle v-text="item.artist"></v-card-subtitle>

            <v-card-actions>
              <v-btn
                v-if="item.artist === 'Ellie Goulding'"
                class="ml-2 mt-3"
                fab
                icon
                height="40px"
                right
                width="40px"
              >
                <v-icon>mdi-play</v-icon>
              </v-btn>

              <v-btn v-else class="ml-2 mt-5" outlined rounded small>
                START RADIO
              </v-btn>
            </v-card-actions>
          </div>

          <v-avatar class="ma-3" size="125" tile>
            <v-img :src="item.src"></v-img>
          </v-avatar>
        </div>
      </v-card>
    </v-col>

    <v-col cols="12">
      <v-card :loading="loading" class="mx-auto my-2" max-width="374">
        <template slot="progress">
          <v-progress-linear
            color="deep-purple"
            height="10"
            indeterminate
          ></v-progress-linear>
        </template>

        <v-img
          height="250"
          src="https://droidjournal.com/wp-content/uploads/2020/04/COD.jpg"
        ></v-img>

        <v-card-title>Call of Duty: Warzone</v-card-title>

        <v-card-text>
          <v-row align="center" class="mx-0">
            <v-rating
              :value="4.5"
              color="amber"
              dense
              half-increments
              readonly
              size="14"
            ></v-rating>

            <div class="grey--text ms-4">4.5 (413)</div>
          </v-row>

          <div class="my-4 text-subtitle-1">$ • Blizzard, Activision</div>

          <div>
            Small plates, salads & sandwiches - an intimate setting with 12
            indoor seats plus patio seating.
          </div>
        </v-card-text>

        <v-divider class="mx-4"></v-divider>

        <v-card-title>Tonight's availability</v-card-title>

        <v-card-text>
          <v-chip-group
            v-model="selection"
            active-class="deep-purple accent-4 white--text"
            column
          >
            <v-chip>5:30PM</v-chip>

            <v-chip>7:30PM</v-chip>

            <v-chip>8:00PM</v-chip>
          </v-chip-group>
        </v-card-text>

        <v-card-actions>
          <v-btn color="deep-purple lighten-2" text @click="reserve">
            Reserve
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>

    <v-col cols="12">
      <v-carousel
        cycle
        height="400"
        hide-delimiter-background
        show-arrows-on-hover
      >
        <v-carousel-item v-for="(slide, i) in slides" :key="i">
          <v-card class="mx-auto" max-width="344">
            <v-img
              :src="slide"
              height="200px"
            ></v-img>

            <v-card-title> Top western road trips </v-card-title>

            <v-card-subtitle> 1,000 miles of wonder </v-card-subtitle>

            <v-card-actions>
              <v-btn color="orange lighten-2" text> Explore </v-btn>
              <v-spacer></v-spacer>
            </v-card-actions>
          </v-card>
        </v-carousel-item>
      </v-carousel>
    </v-col>

    <v-col cols="12">
      <v-card class="mx-auto" color="#26c6da" dark max-width="400">
        <v-card-title>
          <v-icon large left> mdi-twitter </v-icon>
          <span class="text-h6 font-weight-light">Twitter</span>
        </v-card-title>

        <v-card-text class="text-h5 font-weight-bold">
          "Turns out semicolon-less style is easier and safer in TS because most
          gotcha edge cases are type invalid as well."
        </v-card-text>

        <v-card-actions>
          <v-list-item class="grow">
            <v-list-item-avatar color="grey darken-3">
              <v-img
                class="elevation-6"
                alt=""
                src="https://cdn.wccftech.com/wp-content/uploads/2020/03/WCCFcallofdutymodernwarfare201921.jpg"
              ></v-img>
            </v-list-item-avatar>

            <v-list-item-content>
              <v-list-item-title>Sukhrob</v-list-item-title>
            </v-list-item-content>

            <v-row align="center" justify="end">
              <v-icon class="mr-1"> mdi-heart </v-icon>
              <span class="subheading mr-2">256</span>
              <span class="mr-1">·</span>
              <v-icon class="mr-1"> mdi-share-variant </v-icon>
              <span class="subheading">45</span>
            </v-row>
          </v-list-item>
        </v-card-actions>
      </v-card>
    </v-col>

    <v-col cols="12">
      <v-card class="mx-auto" max-width="400">
        <v-list-item two-line>
          <v-list-item-content>
            <v-list-item-title class="text-h5">
              San Francisco
            </v-list-item-title>
            <v-list-item-subtitle
              >Mon, 12:30 PM, Mostly sunny</v-list-item-subtitle
            >
          </v-list-item-content>
        </v-list-item>

        <v-card-text>
          <v-row align="center">
            <v-col class="text-h2" cols="6"> 23&deg;C </v-col>
            <v-col cols="6">
              <v-img
                src="https://cdn.vuetifyjs.com/images/cards/sun.png"
                alt="Sunny image"
                width="92"
              ></v-img>
            </v-col>
          </v-row>
        </v-card-text>

        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-send</v-icon>
          </v-list-item-icon>
          <v-list-item-subtitle>23 km/h</v-list-item-subtitle>
        </v-list-item>

        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-cloud-download</v-icon>
          </v-list-item-icon>
          <v-list-item-subtitle>48%</v-list-item-subtitle>
        </v-list-item>

        <v-slider
          v-model="time"
          :max="6"
          :tick-labels="labels"
          class="mx-4"
          ticks
        ></v-slider>

        <v-list class="transparent">
          <v-list-item v-for="item in forecast" :key="item.day">
            <v-list-item-title>{{ item.day }}</v-list-item-title>

            <v-list-item-icon>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-subtitle class="text-right">
              {{ item.temp }}
            </v-list-item-subtitle>
          </v-list-item>
        </v-list>

        <v-divider></v-divider>

        <v-card-actions>
          <v-btn text> Full Report </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data: () => ({
    items: [
      {
        color: "#1F7087",
        src: "https://cdn.wallpapersafari.com/87/77/I1HAMP.jpg",
        title: "Supermodel",
        artist: "Foster the People",
      },
      {
        color: "#952175",
        src: "https://i.pinimg.com/236x/83/84/8a/83848a96de54c40aee70b6c2caa0dd18.jpg",
        title: "Halcyon Days",
        artist: "Ellie Goulding",
      },
    ],
    colors: [
      "indigo",
      "warning",
      "pink darken-2",
      "red lighten-1",
      "deep-purple accent-4",
    ],
    slides: ["https://wallpapercave.com/wp/Pzb3zCA.jpg", "https://wallpaperaccess.com/thumb/2214535.jpg", "https://wallpaperaccess.com/full/1794118.jpg", "https://wallpapercave.com/wp/plkOzyU.jpg", "https://wallpapers.com/images/high/call-of-duty-hd-desktop-wallpaper-for-4k-obvdwdno806279o8.jpg"],
    labels: ["SU", "MO", "TU", "WED", "TH", "FR", "SA"],
    time: 0,
    forecast: [
      {
        day: "Tuesday",
        icon: "mdi-white-balance-sunny",
        temp: "24\xB0/12\xB0",
      },
      {
        day: "Wednesday",
        icon: "mdi-white-balance-sunny",
        temp: "22\xB0/14\xB0",
      },
      { day: "Thursday", icon: "mdi-cloud", temp: "25\xB0/15\xB0" },
    ],
  }),
};
</script>