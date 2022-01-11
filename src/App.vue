<template>
<h1>DC Heroes {{heroesCount}}</h1>
<h1>{{fullname}}</h1>
<h1>{{fname}} {{lname}}</h1>
<p>{{randC}}</p>
<p>{{randC}}</p>
<p>{{randM()}}</p>
<p>{{randM()}}</p>
 <div v-for="(product ) in dcHeroes" v-bind:key="product">
   {{product.name}}
 </div>
 <form @submit.prevent="addhero">
 <input v-model="newHero" placeholder="Type Name"/>
 <button type="submit">Add</button>
 </form>
 <button @click='setfullName'>setfullName</button>
 <small>Total Heroesm count in the list {{heroesCount}}</small>
</template>
<script>
export default{ 
  computed:{
    heroesCount(){
     return this.dcHeroes.length;
    },
    randC(){
      return Math.random();
    },


    
    setfullName(){
     this.fullname='Set Full Name';
    },
    fullname:{
      get(){
           return ` Full Name :${this.fname}    ${this.lname}`;
      },
      set(fullname){
        const values=fullname.split(" ");
        this.fname=values[0];
        this.lname=values[1];
      }
      
     
    }
  },
  methods:{
  addhero(){
    if(this.dcHeroes!==''){
          this.dcHeroes.unshift({name:this.newHero});
          this.newHero="";
    }
        
  },
   randM(){
      return Math.random();
    }
  } ,
    data(){
        return{
           isActive:false,
           newHero:"",
           fname:"abu",
           lname:"sayed",
           dcHeroes:[{name:'Superman'},{name:'Superwoman'},{name:'Batman'},{name:'Batwoman'}],
          
        }
    },
   
}
</script>