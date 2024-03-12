<template>
  <v-card class="loginCard">
    <v-row align="center" justify="center" class="mt-2">
      <a href="https://www.twitter.com" target="_blank">
        <img src="@/assets/icons/twitter.svg" alt="">
      </a>
    </v-row>
    <v-row align="center" justify="center">
      <span class="titleCard">Bienvenido a Twitter</span>
    </v-row>
    <v-row align="center" justify="center">
      <v-btn outlined rounded class="mt-2" id="btnContainer">
        <img src="@/assets/icons/google.svg" alt="">
        <span style="text-transform: none;">
          Login with Google
        </span>
      </v-btn>
    </v-row>
    <v-row align="center" justify="center">
      <v-btn outlined rounded class="mt-4" id="btnContainer">
        <img src="@/assets/icons/apple.svg" alt="">
        <span style="text-transform: none;">
          Entra con Apple
        </span>
      </v-btn>
    </v-row>
    <v-row align="center" justify="center" class="mt-2">
      <span>_________________Or_________________</span>
    </v-row>
    <v-row align="center" justify="center" class="mt-3">
      <input type="text" placeholder="Celular, email o celular" outlined class="inputEmail"/>
    </v-row>
    <v-row align="center" justify="center">
      <v-btn outlined rounded class="mt-4" id="btnLogin">
        <span style="text-transform: none;">
          Avanzar
        </span>
      </v-btn>
    </v-row>
  </v-card>
</template>

<script>
export default {

}
</script>
<style scoped>
.loginCard{
  width: 40vw;
  height: 60vh;
  background-color: #fff;
  border-radius: 16px;
}
.titleCard{
  font-family: Chirp;
  font-size: 31px;
  font-weight: 700;
  line-height: 37px;
  letter-spacing: 0em;
  text-align: left;

}
#btnContainer{
  width: 296px;
  height: 39px;
  border-radius: 22px;
  border: 1px solid;
  border-color: #cbd1d3;
}
.inputEmail{
  width: 303px;
  height: 56px;
  top: 512px;
  border: 1px solid;
}
#btnLogin{
  width: 300px;
  height: 36px;
  border-radius: 80px;
  background-color: rgba(0, 0, 0, 1);
  color: white;
}
</style>
