<template>
  <v-col>
    <v-row>
      <ui-tweet />
    </v-row>
    <v-row>
      tweets
    </v-row>
  </v-col>
</template>
<script>
import uiTweet from '~/components/twitter/ui-tweet.vue'
export default {
  components: { uiTweet },
  layout: 'home'
}
</script>
