<template>
  <v-app id="inspire">
    <v-navigation-drawer 
      v-model="drawer"
      disable-resize-watcher
      temporary
      fixed
      right
      app>
      <v-toolbar flat>
        <v-list>
          <v-list-tile>
            <v-list-tile-title class="title">
              Account Info
            </v-list-tile-title>
            <v-btn icon>
              <v-icon @click.stop="drawer = !drawer">close</v-icon>
            </v-btn>
          </v-list-tile>
        </v-list>
      </v-toolbar>

      <v-divider></v-divider>

      <v-toolbar flat class="transparent"> 
        <v-list class="pa-0">
          <v-list-tile avatar>
            <v-list-tile-avatar>
              <img src="https://randomuser.me/api/portraits/men/85.jpg">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>Ryan Fauzi</v-list-tile-title>
              <v-list-tile-sub-title>@tekon92</v-list-tile-sub-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-toolbar>

      <v-divider></v-divider>

      <v-layout row align-center justify-center >
        <v-flex xs6>
            <p class="text-xs-center">
              <nuxt-link to="/tekon92/following">339 Following</nuxt-link>
            </p>
          </v-flex>
          <v-flex xs6>
            <p class="text-xs-center">
              <nuxt-link to="/tekon92/followers">339 Followers</nuxt-link>
            </p>
          </v-flex>
      </v-layout>
      <v-divider></v-divider>

      <v-list dense>
        <template v-for="item in items">

          <v-layout
            v-if="item.heading"
            :key="item.heading"
            row
            align-center
          >


            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
            <v-flex xs6 class="text-xs-center">
              <v-switch v-model="item.model"></v-switch>
            </v-flex>
          </v-layout>
          
            <v-divider
              v-else-if="item.divider"
              :key="item.divider"
            >
            </v-divider>
         

          <v-list-tile v-if="item.icon" :key="item.text" :to="'/' +item.route">
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title>
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>

          <v-list-tile v-if="item.s_text" :key="item.s_text">
            <!-- <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action> -->
            <v-list-tile-content>
              <v-list-tile-title>
                {{ item.s_text }} 
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>

    <v-toolbar
      color="blue darken-3"
      dark
      app
      fixed
    >
      <!-- menu -->
      <div>
      <v-btn icon>
        <nuxt-link to="/"><v-icon>home</v-icon></nuxt-link>
      </v-btn>
      <v-btn icon>
        <nuxt-link to="/explore"><v-icon>fullscreen_exit</v-icon></nuxt-link>
      </v-btn>
      <v-btn icon>
        <nuxt-link to="/notifications"><v-icon>notifications</v-icon></nuxt-link>
      </v-btn>
      <v-btn icon>
        <nuxt-link to="/messages"><v-icon>email</v-icon></nuxt-link>
      </v-btn>
      </div>
      <!-- end of menu -->
      <v-spacer></v-spacer>
      <!-- search -->
      <v-text-field
        flat
        solo-inverted
        hide-details
        prepend-inner-icon="search"
        label="Search"
        class="hidden-xs-only"
      ></v-text-field>
      <!-- end of search -->
      <v-spacer></v-spacer>
      <!-- hamburger -->
      <v-toolbar-title class="ml-0 pl-3">
        <v-avatar size="32px" tile>
          <!-- <img
            src="https://cdn.vuetifyjs.com/images/logos/logo.svg"
            alt="Vuetify"
            class="hidden-sm-and-down"
          > -->
          <img src="https://randomuser.me/api/portraits/men/85.jpg" class="hidden-sm-and-down">
        </v-avatar>
        <span class="hidden-sm-and-down">Ryan Fauzi</span>
        <!-- <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon> -->
        <v-btn icon>
          <v-icon @click.stop="drawer = !drawer">expand_more</v-icon>
        </v-btn>
      </v-toolbar-title>
      <!-- end of hamburger -->
    </v-toolbar>
    <v-content>
      <v-container fluid grid-list-md>
        <router-view></router-view>
      </v-container>
    </v-content>
    <!-- button -->
    <v-btn
      fab
      bottom
      right
      color="pink"
      dark
      fixed
      @click="dialog = !dialog"
    >
      <v-icon>add</v-icon>
    </v-btn>
    <v-dialog v-model="dialog" width="800px">
      <v-card>
        <v-card-title
          class="grey lighten-4 py-4 title"
        >
          Create Contact
        </v-card-title>
        <v-container grid-list-sm class="pa-4">
          <v-layout row wrap>
            <v-flex xs12 align-center justify-space-between>
              <v-layout align-center>
                <v-avatar size="40px" class="mr-3">
                  <img src="//ssl.gstatic.com/s2/oz/images/sge/grey_silhouette.png"
                    alt="">
                </v-avatar>
                <v-text-field placeholder="Name">
                </v-text-field>
              </v-layout>
            </v-flex>
            <v-flex xs6>
              <v-text-field
                prepend-icon="business"
                placeholder="Company"
              ></v-text-field>
            </v-flex>

            <v-flex xs6>
              <v-text-field placeholder="Job Title"></v-text-field>
            </v-flex>
            <v-flex xs12>
              <v-text-field
                prepend-icon="mail"
                placeholder="email"
              ></v-text-field>
            </v-flex>
            <v-flex xs12>
              <v-text-field
                type="tel"
                prepend-icon="phone"
                placeholder="(000) 000 - 0000"
                mask="phone"
              ></v-text-field>
            </v-flex>
            <v-flex xs12>
              <v-text-field
                prepend-icon="notes"
                placeholder="Notes"
              ></v-text-field>
            </v-flex>
          </v-layout>
        </v-container>
        <v-card-actions>
          <v-btn flat color="primary">More</v-btn>
          <v-spacer></v-spacer>
          <v-btn flat color="primary" @click="dialog = false">Cancel</v-btn>
          <v-btn flat @click="dialog = false">Save</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
    <!-- end of button -->
    <v-footer app></v-footer>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      dialog: false,
      drawer: false,
      items: [
        { divider: true },
        { counter: 200, text: 'following', route: 'following'},
        { counter: 300, text: 'followers', route: 'followers'},
        { divider: true },
        { icon: 'contacts', text: 'Profile', route: 'tekon92'},
        { icon: 'list', text: 'Lists', route: 'tekon92/lists'},
        { icon: 'bookmarks', text: 'Bookmarks', route: 'tekon92/bookmarks'},
        { icon: 'flash_on', text: 'moments', route: 'tekon92/moments'},
        { divider: true },
        { icon: 'branding_watermark', text: 'Twitter Ads', route: 'ads'},
        { icon: 'timeline', text: 'Analytics', route: 'analytics'},
        { divider: true },  
        { s_text: 'Settings and Privacy' },
        { s_text: 'Help Center' },
        { s_text: 'Log Out' },
        { s_text: 'Send Feedback' },
        { s_text: 'Switch to legacy Twitter' },
        { divider: true },
        { heading: 'Data Saver', model: false},
        { heading: 'Dark Mode', model: false}
      ]
    }),

    props: {
      source: String
    }
  }
</script>

<style scoped>
.v-icon {
    color: #fff !important;
}
a.nuxt-link-exact-active.nuxt-link-active {
    color: #fff;
}

div[role=listitem] .v-icon,div[role=listitem] a.nuxt-link-exact-active.nuxt-link-active {
  color: black !important;
}
</style>
