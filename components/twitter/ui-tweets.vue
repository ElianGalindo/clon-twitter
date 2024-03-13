<template>
  <v-row v-if="tweets.length > 0">
    <v-card v-for="tweet in tweets" :key="tweet.tweet_id" class="cardTweet">
      <v-row>
        <v-col align="center" justify="center">
          <v-img
            :src="require('@/assets/avatars/brawl.jpg')"
            style="border-radius: 50%; width: 40px; height:40px;"
          >
          </v-img>
        </v-col>
        <v-col cols="10" class="ma-1 pa-1">
          <v-row>
            <v-col cols="2">
              <p>{{ tweet.user.username }}</p>
            </v-col>
            <v-col cols="2">
              <p>@{{ tweet.user.username }}</p>
            </v-col>
            <v-col cols="2">
              <p>{{ tweet.creation_date }}</p>
            </v-col>
            <v-col justify="end">
              <v-img :src="require('@/assets/icons/elipsis.svg')" style="max-width:20px;"></v-img>
            </v-col>
          </v-row>
          <v-row>
            <p>{{ tweet.text }}</p>
          </v-row>
          <v-row class="mb-2">
            <v-col cols="2">
              <v-img :src="require('@/assets/icons/comentario.svg')" style="max-width:20px;"></v-img>
            </v-col>
            <v-col cols="2">
              <v-img :src="require('@/assets/icons/repost.svg')" style="max-width:20px;"></v-img>
            </v-col>
            <v-col cols="2">
              <v-img :src="require('@/assets/icons/like.svg')" style="max-width:20px;"></v-img>
            </v-col>
            <v-col cols="2">
              <v-img :src="require('@/assets/icons/view.svg')" style="max-width:20px;"></v-img>
            </v-col>
            <v-col cols="2">
              <v-row>
                <v-col>
                  <v-img :src="require('@/assets/icons/bookmarks.svg')" style="max-width:20px;"></v-img>
                </v-col>
                <v-col>
                  <v-img :src="require('@/assets/icons/share.svg')" style="max-width:20px;"></v-img>
                </v-col>
              </v-row>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </v-card>
  </v-row>
  <p v-else>Loadin tweets...</p>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return {
      tweets: []
    }
  },
  created () {
    this.fetchTweets()
  },
  methods: {
    async fetchTweets () {
      const options = {
        method: 'GET',
        url: 'https://twitter154.p.rapidapi.com/user/tweets',
        params: {
          username: 'BrawlStars',
          limit: '40',
          user_id: '857888651895820288',
          include_replies: 'false',
          include_pinned: 'false'
        },
        headers: {
          'X-RapidAPI-Key': 'dc756c4b53msh9fd7ba95c0e213fp107443jsn6bc3ecf42dd6',
          'X-RapidAPI-Host': 'twitter154.p.rapidapi.com'
        }
      }

      try {
        const response = await axios.request(options)
        this.tweets = response.data.results // Almacenamos los tweets en la variable tweets
        console.log('$$resultado => ', response.data.results)
      } catch (error) {
        console.error('Hubo un problema con la operación axios:', error)
      }
    }
  }
}
</script>
<style scoped>
  .cardTweet{
    width: 100%;
  }
</style>
