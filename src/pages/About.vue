<template>

    <b-container>
  

     <div style="margin-top: 40px; margin-bottom: 40px; text-align: left ">
        <h1>{{'About1'|localize}} <span style="color: #e16262;" >Employee Concept</span> </h1>
      </div>

        <b-row align-v="center">
                   
          <b-col class="md-6" style=" text-align: left;  " >
                <h1>Адаптация</h1>                 

                <p>Повышаем эффективность HR-процессов<br> за счет внедрения мобильных технологий</p>

          </b-col>

          <b-col  class="md-6" style=" margin: 10px; " >
            <div class="block-about-rect "> +2000           </div>
          </b-col>          
          
        </b-row>

        <b-row align-v="center"  class="p-4 bg-dark" style="background: green;">

          <b-col style=" margin: 10px; " >
            <img src="../imgs/yAlex.jpg">
          </b-col>  
              
          <b-col class="md-6" style=" text-align: left;  " >
                <h1>Адаптация</h1>                 

                <p>Повышаем эффективность HR-процессов<br> за счет внедрения мобильных технологий</p>

          </b-col>

          
        </b-row>

         <b-row align-v="center">
                   
          <b-col class="md-6" style=" text-align: left;  " >
                <h1>Адаптация</h1>                 

                <p>Повышаем эффективность HR-процессов<br> за счет внедрения мобильных технологий</p>

          </b-col>

          <b-col  class="md-6" style=" margin: 10px; " >
            <div class="block-about-rect "> Партнеры           </div>
          </b-col>          
          
        </b-row>
        
        <b-row>


        <b-col class="md-6" style=" text-align: left;  " >
                <h1>Адаптация</h1>                 

                <p>Повышаем эффективность HR-процессов<br> за счет внедрения мобильных технологий</p>





         </b-col>

          <b-col  class="md-6" style=" margin: 10px; " >
            
            <!-- <b-form @submit="onSubmit" @reset="onReset" v-if="show"> -->

            <!-- <div class="row"> -->
             <b-form-input v-model="text" placeholder="Enter your name"></b-form-input>
            <!-- </div> -->
             <b-form-input v-model="text" placeholder="Enter your contacts"></b-form-input>

            <!-- <div class="row"> -->
              <b-form-textarea v-model="text" placeholder="Enter your question"></b-form-textarea>
            <!-- </div> -->
            <div style="margin: 15px">
            <b-button style= "background:gray; margin-right: 12px;" type="submit" variant="primary">Submit</b-button>
            <b-button type="reset" variant="danger">Reset</b-button>
            </div>

          <!-- </b-form> -->

          </b-col>
          
          </b-row>

        



        </b-container>

  
</template>

<script>
import SiteLayout from '@/layouts/SiteLayout';
export default {
  name: 'About',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    SiteLayout
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.block-about-rect {
    background-color: #3f3f3f;
    color: #fff;
    width: 90%;
    height: 100%;
    padding: 20px;
    text-align: center;
    font-size: 36px;
    /* font-family: Circe Bold,Lucida Grande,sans-serif; */

}
</style>
