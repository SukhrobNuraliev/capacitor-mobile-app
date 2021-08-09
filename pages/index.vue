<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo d-flex justify-center">
        <!-- <NuxtLogo />
        <VuetifyLogo /> -->
        <v-img
          :aspect-ratio="16 / 9"
          :width="width"
          src="https://www.teahub.io/photos/full/35-358390_call-of-duty-mobile-all-characters.jpg"
        ></v-img>
      </v-card>
      <v-card>
        <v-card-title class="headline"> Welcome to Conda Mobile </v-card-title>
        <v-card-text>
          <p>
            Thank you for developing with Conda and I look forward to bringing
            more exciting features in the future.
          </p>
          <div class="text-xs-right">
            <em><small>&mdash; Sukhrob Nuraliev</small></em>
          </div>
          <hr class="my-3" />
        </v-card-text>
        <v-card-actions>
          <v-spacer />
          <v-btn color="green darken-2" nuxt to="/inspire">
            Continue
            <v-icon right dark> mdi-pistol </v-icon>
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>
