<template>
  <v-navigation-drawer fixed permanent class="navigation-color" style="width:25%;">
    <center class="pt-4" style="">
    <v-avatar size="120">
      <img src="../../public/assets/img/szy.png" alt="">
    </v-avatar>
    <h1 class="display-1 mt-4 roboto-font">Samair Zia</h1>
    <!-- <p class="title mt-3" style="color:#b92c37">Front-end Developer</p> -->
    <p class="title mt-3 roboto-font" style="color:#FFAA00">Front-end Developer</p>
    <v-list>
      <v-list-tile
        v-for="item in items"
        :key="item.title"
        @click=""
      >

        <v-list-tile-content>
        <v-list-tile-title style="text-align:center"><a :href='item.link'>{{ item.title }}</a> </v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
    <a href="https://www.linkedin.com/in/samairzia" target="_blank"><i class='fab fa-linkedin social-icons'></i></a>
    <a href="https://www.facebook.com/SamairZia95" target="_blank"><i class='fab fa-facebook social-icons'></i></a>
    </center>
  </v-navigation-drawer>
</template>

<script>
export default {
  data(){
    return {
      items: [
          { title: 'About Me', link: '#about'},
          { title: 'Experience', link: '#experience'},
          { title: 'Skills & Eduation', link: '#skills'},
          { title: 'Portfolio', link: '#portfolio'},
          { title: 'Contact', link: '#contact'},

        ]
    }
  }
}
</script>

<style src="../../public/assets/css/style.css">

</style>
