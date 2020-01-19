<template>

  <b-container>
        
     <div style="margin-top: 40px; margin-bottom: 40px; text-align: left ">
        <h1>{{'Implem1'|localize}} <span style="color: #e16262;" >Employee Concept</span>? </h1>
      </div>

        <b-row align-v="center">
                   
          <b-col class="md-6" style=" text-align: left;  " >
                <h1>Адаптация</h1>                 

                <p>Повышаем эффективность HR-процессов<br> за счет внедрения мобильных технологий</p>

          </b-col>

          <b-col  class="md-6" style=" margin: 10px; " >
            <img width="270px" src="../imgs/impl1.jpg">
          </b-col>          
          
        </b-row>

        <b-row align-v="center">

          <b-col  class="md-6" style=" margin: 10px; " >
            <img width="270px" src="../imgs/impl1.jpg">
          </b-col>                     
          
          <b-col class="md-6" style=" text-align: left;  " >
                <h1>Адаптация</h1>                 

                <p>Повышаем эффективность HR-процессов<br> за счет внедрения мобильных технологий</p>

          </b-col>

          
        </b-row>

        </b-container>

</template>

<script>
import SiteLayout from '@/layouts/SiteLayout';
import localizeFilter from '@/filters/localize.filter'
export default {
  
}
</script>
