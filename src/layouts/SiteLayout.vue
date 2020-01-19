<template>
  <div id="app">
    <!-- class="header" -->
  
      <!-- <div class="header__logo">Jetro</div> -->
      <!-- <div class="header__nav"> -->

        <b-navbar toggleable="sm" type="dark" class="header" tag="div" style="height:100px!important; position: initial; padding-left:20px; padding-right:50px">
       <!-- header__logo -->
          <b-navbar-brand tag="div" class="sm header__logo" href="#">
            
            <img width="230px" src="../imgs/ResVersion2.png">
          </b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <!-- header__nav -->
            <b-navbar-nav class="ml-auto">
            <!-- <div class="switch" style="margin-top: 30px">
              <label>
                English
                <input type="checkbox" v-model="isRuLocale" v-on:click="switchLang()">
                <span class="lever"></span>
                Русский
              </label>
            </div> -->



              <b-nav-item class="link-top-menu" id="top" to="/">{{'Menu_AboutService'|localize}}</b-nav-item>
              <b-nav-item class="link-top-menu" to="/function">{{'Menu_Function'|localize}}</b-nav-item>              
              <b-nav-item class="link-top-menu" to="/implementation">{{'Menu_Impl'|localize}}</b-nav-item>
              <b-nav-item class="link-top-menu" to="/about">{{'Menu_About'|localize}}</b-nav-item>
              <b-nav-item class="link-top-menu" to="/login">{{'Menu_System'|localize}}</b-nav-item>

              
            </b-navbar-nav>


          </b-collapse>
        </b-navbar>

        
        <!-- <router-link to="/login">Log into FCA</router-link>
        <router-link
          v-for="link in links"
          :key="link.url"
          active-class="active"
          :to="link.url"
          :exact="link.exact"
        >  
          <a href="#">{{link.title}}</a>
        </router-link> -->

        

      <!-- </div> -->

    
    <transition name="fade" appear>
    <slot></slot>
    </transition>

  </div>
</template>

<script>
import localizeFilter from '@/filters/localize.filter'
import { mapGetters, mapActions } from 'vuex'
// import localeFilter from '@/filters/localize.filter'
export default {
  
  name: 'site-layout',

  data: () => ({
    isRuLocale: false,
    
    links: [
      { title: localizeFilter('Menu_AboutService'), url: '/'},
      { title: localizeFilter('Menu_About'), url: '/about'},
      { title: localizeFilter('Menu_System'), url: '/login'}
      
    ]
  }),
  computed: {
    ...mapGetters(['info'])
  },
  methods: {
    ...mapActions(['updateInfo']),
    // async submitHandler() {
    //  async switchLang:  function (event) {
       async switchLang() {
      // if (this.$v.$invalid) {
        // this.$v.$touch()
        // return
      // }

      try {
         await this.updateInfo({
          // name: this.name,
          locale: this.isRuLocale ? 'en-US' : 'ru-RU'
        })
      } catch (e) {}
    }
  }

}

</script>

<style lang="sass">
@import 'bla.sass'
.header
  // border-bottom: 100px solid #e16262
  
  background: #e16262;


  &__logo
    float: left
    font-size: 50px 
    background: 
  &__nav
      float: right
      white-space: nowrap
      font-size: 15px 
      text-transform: uppercase
      a
        text-decoration: none
        padding: 10px 
        display: inline-block
.fade-enter-active, .fade-leave-active
  transition-property: opacity
  transition-duration: .25s
.fade-enter-active
  transition-delay: .25s
.fade-enter, .fade-leave-active
  opacity: 0


</style>

<style scoped>

.link-top-menu {
  padding-left: 0,5rem;
  padding-right: 1rem;
  
}

a {
  font-size: 18px!important;
  color: #ffffff!important;
}
a:hover  {
  
  color: #f7dfdf!important;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #353635;
  margin-top: 10px;
}
</style>
