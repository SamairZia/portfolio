<template>
  <v-app dark>
    <!-- <b-row>
      <b-col sm="12" md="3">
        <Navigation/>
      </b-col>
      <b-col sm="12" md="9">
        <v-content>
          <router-view></router-view>
        </v-content>
      </b-col>
    </b-row> -->
    <v-layout row>
      <v-flex xs3>
        <Navigation/>
      </v-flex>
      <v-flex xs9>
        <v-content>
          <router-view></router-view>
        </v-content>
      </v-flex>
    </v-layout>
  </v-app>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import Navigation from "@/components/Navigation";

export default {
  name: "App",
  components: {
    Navigation
    // HelloWorld
  },
  data() {
    return {
      //
    };
  }
};
</script>

<style src="../public/assets/css/style.css"></style>
