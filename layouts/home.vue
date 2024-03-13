<template>
  <v-app>
    <v-navigation-drawer
      absolute
      app
      left
      permanent
      width="300"
    >
      <v-list-item
        v-for="opcion in opcionesMenu"
        :key="opcion.titulo"
        :to="opcion.path"
        link
      >
        <v-list-item-icon>
          <v-img :src="opcion.icon"/>
        </v-list-item-icon>
        <v-list-item-content>
          <v-list-item-title>
            <span class="tituloMenu">
              {{ opcion.titulo }}
            </span>
          </v-list-item-title>
        </v-list-item-content>
      </v-list-item>
      <v-row align="center" justify="center" class="pa-0 ma-0">
        <v-btn class="btnTweet">
          <span class="textBtn">
            Tweet
          </span>
        </v-btn>
      </v-row>
      <v-row align="center" justify="center">
        <div style="display:flex; border: 2px;">
          <v-col>
            <v-img :src="require('@/assets/avatars/my-avatar.svg')" style="border-radius:50%; width:40px;">
            </v-img>
          </v-col>
          <v-col cols="8">
            <v-row class="my-0 flex-column">
              <p class="mb-1"><b>Elian Galindo</b></p>
              <p>@ElianG</p>
            </v-row>
          </v-col>
          <v-col>
            <v-img :src="require('@/assets/icons/elipsis.svg')" style="max-width:20px;"></v-img>
          </v-col>
        </div>
      </v-row>
    </v-navigation-drawer>
    <v-main>
      <Nuxt/>
    </v-main>
    <v-navigation-drawer
      absolute
      right
      permanent
      width="300"
      app
    >
      <v-row align="center" justify="center" class="pa-2 ma-2">
        <v-text-field
          v-model= "searchTwitter"
          filled
          rounded
          hide-details
          prepend-inner-icon="mdi-magnify"
          placeholder="Search Twitter"
        />
      </v-row>
      <v-row align="center" justify="center">
        <ui-happening/>
      </v-row>
      <v-card>
        who to follow
      </v-card>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      opcionesMenu: [
        { titulo: '', icon: require('@/assets/icons/twitter.svg'), path: '/' },
        { titulo: 'Home', icon: require('@/assets/icons/home.svg'), path: '/home' },
        { titulo: 'Explore', icon: require('@/assets/icons/explore.svg'), path: '/explore' },
        { titulo: 'Notifications', icon: require('@/assets/icons/notifications.svg'), path: '/notifications' },
        { titulo: 'Messages', icon: require('@/assets/icons/messages.svg'), path: '/messages' },
        { titulo: 'Bookmarks', icon: require('@/assets/icons/bookmarks.svg'), path: '/bookmarks' },
        { titulo: 'Lists', icon: require('@/assets/icons/lists.svg'), path: '/lists' },
        { titulo: 'Profile', icon: require('@/assets/icons/profile.svg'), path: '/profile' },
        { titulo: 'More', icon: require('@/assets/icons/more.svg'), path: '/more' }
      ],
      searchTwitter: ''
    }
  }
}
</script>
<style scoped>
  .tituloMenu{
    font-family: SF Compact Display;
    font-size: 19px;
    font-weight: 700;
    line-height: 23px;
    letter-spacing: 0em;
    text-align: left;
  }
  .btnTweet{
    width: 90%!important;
    padding: 5px!important;
    border-radius: 15px!important;
    margin: 10px!important;
    background-color: #1DA1F2 !important;
  }
  .textBtn{
    color: white!important;
    text-transform: none!important;
  }
  .btnSearch{
    background-color: #ebeef0;
    border-radius: 15px;
  }
</style>
