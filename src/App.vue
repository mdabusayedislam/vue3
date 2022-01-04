<template>
<h1>DC Heroes</h1>
 <div v-for="(product, num ) in dcHeroes" v-bind:key="product">
   {{num}}:{{product.a}}
 </div>
 <input v-model.lazy="newHero"/>
 <button v-bind:disabled="isActive">Add</button>
</template>
<script>
export default{  
    data(){
        return{
           isActive:false,
           newHero:"e",
           dcHeroes:[{a:'a'},{a:'b'},{a:'c'},{a:'d'}]
        }
    }
}
</script>