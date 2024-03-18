<template>
  <v-row class="ma-1 pa-1">
    <v-col>
      <v-img
        :src="require('@/assets/avatars/my-avatar.svg')"
        style="border-radius: 50%;"
      >
      </v-img>
    </v-col>
    <v-col cols="10" class="ma-1 pa-1 mb-3">
      <v-row>
        <v-textarea
          v-model="tweet"
          rows="2"
          row-height="5"
          :rules="countTweet"
        />
      </v-row>
      <v-row>
        <v-col cols="1">
          <v-img :src="require('@/assets/icons/imagen.svg')"></v-img>
        </v-col>
        <v-col cols="1">
          <v-img :src="require('@/assets/icons/gift.svg')"></v-img>
        </v-col>
        <v-col cols="1">
          <v-img :src="require('@/assets/icons/estadisticas.svg')"></v-img>
        </v-col>
        <v-col cols="1">
          <v-img :src="require('@/assets/icons/reaccion.svg')"></v-img>
        </v-col>
        <v-col cols="1">
          <v-img :src="require('@/assets/icons/calendario.svg')"></v-img>
        </v-col>
        <v-col>
          <v-row align="center" justify="end">
            <v-btn rounded color="primary">
              <span style="text-transform: none;">
                tweet
              </span>
            </v-btn>
          </v-row>
        </v-col>
      </v-row>
    </v-col>
    <v-row class="ma-2 pa-2 mb-3">
      <ui-tweets />
    </v-row>
  </v-row>
</template>
<script>
import uiTweets from '~/components/twitter/ui-tweets.vue'
export default {
  components: { uiTweets },
  data () {
    return {
      reglas: {
        countTweet: [
          v => v.length < 260 || 'Max 259 characters'
        ]
      }
    }
  }
}
</script>
<style scoped>
  .btnTweet{
    width: Fixed (77px);
    height: Fixed (39px);
    top: 59px;
    left: 491px;
    padding: 15px, 93px, 15px, 93px;
    border-radius: 10px;
    gap: 10px;
    opacity: 0.5px;
    background-color: #1DA1F2;
  }
</style>
