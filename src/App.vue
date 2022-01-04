<template>
<h1>DC Heroes</h1>
 <div v-for="(product ) in dcHeroes" v-bind:key="product">
   {{product.name}}
 </div>
 <form @submit.prevent="addhero">
 <input v-model="newHero" placeholder="Type Name"/>
 <button type="submit">Add</button>
 </form>
</template>
<script>
export default{ 
  methods:{
  addhero(){
    if(this.dcHeroes!==''){
this.dcHeroes.unshift({name:this.newHero});
          this.newHero="";
    }
        
  }
  } ,
    data(){
        return{
           isActive:false,
           newHero:"",
           dcHeroes:[{name:'Superman'},{name:'Superwoman'},{name:'Batman'},{name:'Batwoman'}]
        }
    }
}
</script>