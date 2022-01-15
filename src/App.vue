<template>
   <AppHeader/>
      <div class="w-full flex">
            <div class="m-auto">
                 <DcHeros/>
                  <Calendar/>   
            </div>
               
      </div>
      
</template>
<script>
import AppHeader from './components/AppHeader';
import Calendar from './components/Calendar';
export default{   
    //components:{AppHeader,DcHeros}     
    components:{AppHeader,Calendar}              
        
}
</script>