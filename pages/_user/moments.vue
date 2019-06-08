<template>
  <v-layout justify-center row fill-height>
    <v-flex md6>
      <v-card>
        <v-card-title primary-title>
          <div>
            <div class="headline font-weight-black">Indonesia Trends</div>
          </div>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>settings</v-icon>
          </v-btn>
        </v-card-title>
        <v-divider></v-divider>
        <CardList></CardList>

        <v-card-actions>
          <v-btn color="primary" flat nuxt to="/inspire">Show More</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>

    <v-flex md4 v-if="$vuetify.breakpoint.mdAndUp">
      <v-card>
        <v-card-title primary-title>
          <div>
            <div class="headline font-weight-black">Who to follow</div>
          </div>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>settings</v-icon>
          </v-btn>
        </v-card-title>
        <v-divider></v-divider>
        <CardFollow></CardFollow>

        <v-card-actions>
          <v-btn color="primary" flat nuxt to="/inspire">Show More</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>
  </v-layout>
</template>

<script>

  export default {
    components: {
      
    }
  }

</script>
