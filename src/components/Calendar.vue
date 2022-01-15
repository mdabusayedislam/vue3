<template>
<div class="m-auto">
     <h1 class="text-2xl my-2 text-center">Vue Calendar</h1>
 
        <section class="flex mx-2 justify-between">
                <h2 class="font-bold">{{currentMonthName}}</h2>
                <h2 class="font-bold">{{currentYear}}</h2>
        </section>
        <section class="flex  my-2">
                <p 
                class="text-center" 
                style="width:14.28%" 
                v-for="day in days" :key="day">{{day}}</p>
        </section>
        <section class="flex flex-wrap my-2">  
               <p 
                class="text-center" 
                style="width:14.28%" 
                v-for="day in startDay()" 
                :key="day"
                ></p>  
                <p 
                class="text-center" 
                style="width:14.28%" 
                v-for="day in dayInMonths()" 
                :key="day"
                :class="currentDateClass(day)"
                >{{day}}</p>
        </section>
        <section class="flex justify-between my-2">          
            <button class="px-2 border rounded" @click="prev()">prev</button>
              <button class="px-2 border rounded" @click="next()">next</button>
        </section>


      
</div>
</template>

<script>
export default {
  data(){
      return{
          currentMonth:new Date().getMonth(),         
          currentYear:new Date().getFullYear(),
          days:['Sun','Mon','Tue','Wed','Thu','Fri','Sat']
      }
  },
 
  methods:{
      dayInMonths(){          
          return new Date(this.currentYear,this.currentMonth+1,0).getDate()
      },
       startDay(){
          return new Date(this.currentYear,this.currentMonth,1).getDay();
      },  
      next(){
          if(this.currentMonth===11){
                 this.currentMonth=0
                 this.currentYear++;
          }
          else{
                 this.currentMonth++;
          }
         
      },  
      prev(){
          if(this.currentMonth===0){
               this.currentMonth=11
               this.currentYear--; 
          }
          else{
              this.currentMonth--;
          }
         
      },
      currentDateClass(day){
          const calendarFullDate=new Date(this.currentYear,this.currentMonth,day).toDateString();
          const currentFullDate=new Date().toDateString();
          return calendarFullDate===currentFullDate?'text-yellow-600':'';
      }    
  },
  computed:{
       currentMonthName(){
          return  new Date(this.currentYear,this.currentMonth,1).toLocaleDateString('default',{month:'long'})
       }
  }
}
</script>

<style>

</style>