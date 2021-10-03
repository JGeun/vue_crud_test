<template>
  <v-app>
    <v-main v-bind:style="myStyle">
        <Main :style="{'position':'relative'}"/>
    </v-main>
  </v-app>
</template>

<script>

import Main from './components/Main';

export default {
  name: 'App',

  components: {
    Main,
  },

  data(){
    return{
      myStyle:{
        display: "relative",
        width: "1400px",
        margin: "0 auto",
        backgroundImage: `url(${require("@/assets/image0.jpg")})`,
        backgroundSize: "100% 100%",
        backgroundRepeat: "no-repeat"
      }
    }
  }
};
</script>
