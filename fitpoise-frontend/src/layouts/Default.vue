<template>
  <v-app>
    <v-app-bar app absolute dark>
                    <v-app-bar-nav-icon></v-app-bar-nav-icon>
                    <v-toolbar-title>FitPoise</v-toolbar-title>
                    <v-text-field
                      placeholder="Search"
                      class="ml-8"
                      style="max-width: 350px;"
                      prepend-inner-icon="mdi-magnify"
                      outlined
                      rounded
                      dense
                      hide-details
                    />
                    <v-spacer></v-spacer>
                    <v-btn icon>
                      <v-icon dark>mdi-account</v-icon>
                    </v-btn>
    </v-app-bar>

       <v-parallax
    dark
    src="https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg"
  >
    <v-row
      align="center"
      justify="center"
    >
      <v-col
        class="text-center"
        cols="12"
      >
        <h1 class="display-1 font-weight-thin mb-4">
          {{$static.metadata.siteName}}
        </h1>
        <h4 class="subheading">
          {{$static.metadata.siteDescription}}
        </h4>
      </v-col>
    </v-row>
  </v-parallax>


    <v-main>
      <slot/>
    </v-main>

    <v-footer padless>
      <v-col class="text-center" cols="12">
        Copyright {{ new Date().getFullYear() }} — <strong>{{ $static.metadata.siteName }}</strong> (All rights reserved)
      </v-col>
    </v-footer>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName,
    siteDescription
  }
}
</static-query>
