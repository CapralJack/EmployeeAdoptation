<template>
  
    <div class="hello">
      <div class="switch" style="float:left">
              <label style="color:#fff; margin-left:10px">
                English
                <input type="checkbox" v-model="isRuLocale" v-on:click="switchLang()">
                <span class="lever"></span>
                Русский
              </label>
      </div>
 <!-- class="block-hi" -->
      <div class="block-hi">
           
           
        
        <b-container>
        <b-row align-v="left">
                   
          <b-col class="md-6" style=" text-align: left; margin-top: 60px " >
                   
                <h1>{{'Hi1'|localize}}</h1>
                  <ul>
                      <li>{{'Hi2'|localize}}</li><br>
                      <li>{{'Hi3'|localize}}</li><br>
                      <li>{{'Hi4'|localize}}</li>
                  </ul>
                  <p style="font-size:18px">{{'Hi5'|localize}}</p>
           
          </b-col>

          <b-col  class="hi-block-background md-6"  style=" text-align: left; margin-top: 10px "  >
            <!-- <div</div> -->
          </b-col>
          
        </b-row>
        </b-container>
        
      </div>


      <div>
        <h4>{{'whywe'|localize}} <span class="red-font" >Employee &nbsp;Concept</span>? </h4>
      </div>


      <b-container>
        <b-row align-v="center">
          <b-col
          style="max-width: 40rem;"
          class="md-4"
          >
            <div class="why-element">
                <div class="why-speed color-green">
                  <img src="../imgs/icon_speed.png">
                </div>

                <div>
                  <h4>{{"Speed"|localize}}</h4>
                  <p>{{"Speed_Title"|localize}}</p>
                </div>
            </div>
         </b-col>
         <!-- 2 -->

         <b-col
          style="max-width: 40rem;"
          class="md-4"
         >
          <div class="why-element">
            <div class="why-speed color-red">
              <img src="../imgs/icon_speed.png">
            </div>

            <div>
              <h4>{{"Function"|localize}}</h4>
              <p>{{"Function_Title"|localize}}</p>
            </div>
          </div>
          </b-col>

          <b-col
          style="max-width: 40rem;"
          class="md-4"
         >
          <div class="why-element">
            <div class="why-speed color-red">
              <img src="../imgs/icon_speed.png">
            </div>

            <div>
              <h4>{{"Flexibility"|localize}}</h4>
              <p>{{"Flexibility_Title"|localize}}</p>
            </div>
          </div>
          </b-col>
          <b-col
          style="max-width: 40rem;"
          class="md-4"
         >
          <div class="why-element">
            <div class="why-speed color-red">
              <img src="../imgs/icon_speed.png">
            </div>

            <div>
              <h4>{{"Innovation"|localize}}</h4>
              <p>{{"Innovation_Title"|localize}}</p>
            </div>
          </div>
          </b-col>
                





        

        </b-row>
        
      </b-container>




      



      

      <h1 class="singlepost">Posts</h1>
      <post 
        v-for="post in posts"
        v-bind:heading="post.title"
        v-bind:subtitle="post.subtitle"
        v-bind:key="post.id"
      />
          
    </div>

</template>

<script>
import SiteLayout from '@/layouts/SiteLayout';
import localizeFilter from '@/filters/localize.filter'
import { mapGetters, mapActions } from 'vuex'

import Post from '@/components/Post';
export default {
  name: 'Homepage',
  data: ()  => ({
  // whywe: localizeFilter('whywe'),
  isRuLocale: false,
  
  speed: localizeFilter('Speed'),
  speed_title: localizeFilter('Speed_Title'),
   why: [
      { speed:'Speed'},
      { title: localizeFilter('Menu_About'), url: '/about'},
      { title: localizeFilter('Menu_System'), url: '/login'}
      
    ],
    posts: [
      {id: 1, title: "Blablablabla", subtitle: "Subtitle"},
      {id: 2, title: "222Blablablabla1", subtitle: "Subtitle"},
      {id: 3, title: "B333lablablabla2", subtitle: "Subtitle"},
      {id: 4, title: "444Blablablabla3", subtitle: "Subtitle"},
      {id: 5, title: "444Blablablabla3", subtitle: "Subtitle"},
      {id: 6, title: "444Blablablabla3", subtitle: "Subtitle"},
      {id: 7, title: "444Blablablabla3", subtitle: "Subtitle"},
        
    ]
    
  }),
  components: {
    SiteLayout,
    Post
  },

  computed: {
    ...mapGetters(['info'])
  },

  methods: {
    ...mapActions(['updateInfo']),

     async switchLang() {
       try {
         debugger
         await this.updateInfo({
          // name: this.name,
          locale: this.isRuLocale ? 'en-US' : 'ru-RU'
        })
      } catch (e) {}
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.singlepost {
  background: green;
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

.why-speed {
  /* text-align: center; */
  width: 100px;
  height: 100px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  border-radius: 100px;
  margin-bottom: 30px;
   /* padding-bottom: 30px; */
}

.color-cyan-spec {
  background-color:#64d0d4
}
.color-green-spec {
 background-color:#bfe549
}
.color-red-spec {
  background-color:#d91e47
}
.color-yellow-spec {
  background-color:#ffd82c
}
.color-green {
  background-color: #4cdbaa;
}

.color-red {
  background-color: #e16262;
}

.red-font {
 color: #e16262;
}

.block-hi {
  /* padding-top: 90px; */
  /* margin-bottom: 60px; */
  padding-top: 30px; 
  color: #fff;
  background: #e16262;/*e16262 f1ad9c*/
  
  background: linear-gradient(to bottom,#e16162,#ffffff); 
  min-height: 500px;

}

.wrapper {
    width: 1020px;
    padding: 0 20px;
    position: relative;

    margin: 0 auto;
}
.hi-block-background {
    background: url(../imgs/mob.png) no-repeat center;
    background-size: contain;
    /* width: 600px; */
    height: 400px;
     /* position: absolute;  */
    /* right: -60px; */
    /* top: -60px;  */
    min-width: 260px;
}
.hi-block-title {
  text-align: left;
  font-weight: 600;
  line-height: 1.15;
  font-size: 40px;
  margin-top: 0;
  margin-bottom: 10px;
}

.welcome-block-form {
  text-align: left;
    width: 520px;
    perspective: 500px;
}

.welcome-block-form-desc {
  text-align: left;
    font-size: 21px;
    font-weight: 300;
    line-height: 1.29;
    opacity: .9;
}

.welcome-block-form-desc ul {
    padding-left: 15px;
}


.why-element
{
  
  /* display: inline-block; */
  padding-top: 50px;
}
    
    
  

</style>
