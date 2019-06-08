<template>
  <v-card class="mx-auto">
    <v-list v-for="item in items" :key="item.username" @click="">
      <v-card-title>
      <v-icon
        left
      >
        repeat
      </v-icon>
      <span class="caption">tekon92 retweeted</span>
      <v-spacer></v-spacer>
      <v-icon
        right
      >
        expand_less
      </v-icon>
    </v-card-title>

    <v-list-tile class="mb-5">
      <v-list-tile-avatar color="grey darken-3" class="justify-center align-center">
      <v-img
        class="elevation-6"
        :src="item.avatar"
      ></v-img>
    </v-list-tile-avatar>

    <v-card-text class="body-1 pl-0">
      <p class="caption"><span class="font-weight-bold">{{ item.fullname }} </span>{{ item.username }} . 42m</p>
      {{ item.tweet }}
    </v-card-text>
    </v-list-tile>

    <v-card-actions :class="{'ml-5': !$vuetify.breakpoint.xs}">
      <v-list-tile class="grow">
       
        <v-layout row :justify-start="$vuetify.breakpoint.mdAndUp" :justify-center="$vuetify.breakpoint.smAndDown"> 
          <v-flex xs2>
            <v-icon>
            comment
          </v-icon>
          <span class="caption">{{ item.comment }}</span>
          </v-flex>
           <v-flex xs2>
            <v-icon>
            repeat
          </v-icon>
          <span class="caption">{{ item.retweet }}</span>
          </v-flex>
           <v-flex xs2>
            <v-icon>
            star_border
          </v-icon>
          <span class="caption">{{ item.like }}</span>
          </v-flex>
           <v-flex xs2>
            <v-menu >
            <template v-slot:activator="{ on }">
              <v-btn
                dark
                icon
                v-on="on"
              >
                <v-icon>star_border</v-icon>
              </v-btn>
            </template>

            <v-list>
              <v-list-tile
                v-for="(button, i) in buttons"
                :key="i"
                @click=""
              >
                <v-list-tile-title>{{ button.title }}</v-list-tile-title>
              </v-list-tile>
            </v-list>
          </v-menu>
          </v-flex>
        </v-layout>
      </v-list-tile>
    </v-card-actions>
    <v-divider></v-divider>
    </v-list>
  </v-card>
</template>

<script>
export default {
  data () {
    return ({
      items: [
          { avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg', fullname: 'Ryan Fauzi', username: '@tekon92', tweet: 'Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.', comment: 20, retweet: 50, like: 100 },
          { avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg', fullname: 'Jokowi', username: '@jokowi', tweet: 'Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.', comment: 10, retweet: 30, like: 50 },
          { avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg', fullname: 'Bernadeschi', username: '@berna', tweet: 'Turns out semicolon-less style is easier and safer in TS because most gotcha edge cases are type invalid as well.', comment: 25, retweet: 14, like: 5 }
        ],
      buttons: [
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me' },
        { title: 'Click Me 2' }
      ]
    })
  }
}
</script>

<style>

</style>
