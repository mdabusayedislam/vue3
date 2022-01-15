<template>
              <h1 class="text-2xl text-center">DC Heroes {{heroesCount}}</h1>
                  <ul>
                        <li class="flex justify-between" v-for="(hero, index) in dcHeros" :key="hero.name">
                              <div>{{hero.name}}
                                 </div>    
                                    <button v-on:click="remove(index)">x</button>
                                    
                                   
                           
                        </li>
                  </ul>     
                  <form class="m-10" @submit.prevent="addhero">
                        <input 
                        class="border rounded"
                        v-model="newHero" 
                        placeholder="Type Name"/>
                        <button class="border rounded bg-gradient-to-t from-red-700 to-pink-500  text-white" type="submit">Add</button>
                  </form>
</template>

<script>
export default {
     computed:{
                  heroesCount(){
                        return this.dcHeros.length;  
                  }    
            },
      methods:{
                  addhero(){
                  if(this.dcHero!==''){
                        this.dcHeros.unshift({name:this.newHero});
                        this.newHero="";
                  }               
                  },  
                  remove(index){
                        this.dcHeros=this.dcHeros.filter((hero,i)=>i!=index)
                  },
                  },
    data(){
                        return{
                        newHero:"",                                  
                        dcHeros:[
                              {name:'Superman'},
                              {name:'Superwoman'},
                              {name:'Batman'},
                              {name:'Batwoman'}
                              ]          
                        }
            },   
           
}
</script>

<style>

</style>