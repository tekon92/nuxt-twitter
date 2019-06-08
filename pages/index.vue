<template>
  <v-layout justify-center row fill-height>
    <v-flex md6>
      <v-card>
        <v-card-title primary-title v-if="$vuetify.breakpoint.mdAndUp">
          <div>
            <div class="headline font-weight-black">Home</div>
          </div>
          <v-spacer></v-spacer>
          <v-btn icon>
            <v-icon>whatshot</v-icon>
          </v-btn>
        </v-card-title>
        <v-divider></v-divider>
        <v-card-actions class="pa-3" v-if="$vuetify.breakpoint.mdAndUp">
          <v-list-tile-avatar color="grey darken-3">
            <v-img class="elevation-6"
              src="https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light">
            </v-img>
          </v-list-tile-avatar>
          <v-text-field flat solo-inverted hide-details label="what's happening?"></v-text-field>
          <div>
            <v-btn icon>
              <v-icon>insert_photo</v-icon>
            </v-btn>
            <v-btn icon>
              <v-icon>gif</v-icon>
            </v-btn>
            <v-btn icon>
              <v-icon>poll</v-icon>
            </v-btn>
          </div>
        </v-card-actions>
        <v-divider></v-divider>
        <Card>
        </Card>
        <v-card-actions>
          <v-btn color="primary" flat nuxt to="/inspire">Show More</v-btn>
        </v-card-actions>
      </v-card>
    </v-flex>

    <v-flex md4>
      <v-flex md12 v-if="$vuetify.breakpoint.mdAndUp" >
        <v-card>
            <v-card-title primary-title v-if="$vuetify.breakpoint.mdAndUp">
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

      <v-flex md12 v-if="$vuetify.breakpoint.mdAndUp" >
        <v-card>
            <v-card-title primary-title v-if="$vuetify.breakpoint.mdAndUp">
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
    </v-flex>
  </v-layout>
</template>

<script>
  import Logo from '~/components/Logo.vue'
  import VuetifyLogo from '~/components/VuetifyLogo.vue'
  import Card from '~/components/Card.vue'
  import CardList from '~/components/CardList.vue'
  import CardFollow from '~/components/CardFollow.vue'

  export default {
    components: {
      Logo,
      VuetifyLogo,
      Card,
      CardList,
      CardFollow
    }
  }

</script>
