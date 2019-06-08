<template>
  <v-card>
        <v-list two-line subheader>
          <v-list-tile
            v-for="item in items"
            :key="item.title"
            @click=""
          >
            <v-list-tile-avatar>
              <img :src="item.avatar">
            </v-list-tile-avatar>

            <v-list-tile-content>
              <v-list-tile-title>{{ item.title }}</v-list-tile-title>
              <v-list-tile-sub-title>{{ item.subtitle }}</v-list-tile-sub-title>
            </v-list-tile-content>

            <v-list-tile-action>
              <v-btn round color="primary" dark>Follow</v-btn>
            </v-list-tile-action>
          </v-list-tile>
        </v-list>
      </v-card>
</template>

<script>
export default {
  data () {
      return {
        items: [
          { avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg', iconClass: 'grey lighten-1 white--text', title: 'Ryan Fauzi', subtitle: '@tekon92' },
          { avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg', iconClass: 'grey lighten-1 white--text', title: 'Jokowi', subtitle: '@jokowi' },
          { avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg', iconClass: 'grey lighten-1 white--text', title: 'Bernadeschi', subtitle: '@berna' }
        ]
      }
    }
}
</script>

<style>

</style>
