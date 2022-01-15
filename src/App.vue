<template>
      <h1>DC Heroes {{heroesCount}}</h1>
      <ul>
            <li v-for="(hero, index) in dcHeros" :key="index">
                  <div>{{hero.name}}<button v-on:click="remove(index)">x</button></div>
            </li>
      </ul>     
      <form @submit.prevent="addhero">
            <input v-model="newHero" placeholder="Type Name"/>
            <button type="submit">Add</button>
      </form>
</template>
<script>
export default{ 
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