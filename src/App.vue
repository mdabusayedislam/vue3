<template>
<h1>DC Heroes</h1>
 <div v-for="(product, num ) in dcHeroes" v-bind:key="num">
   {{num}}:{{product.a}}
 </div>
</template>
<script>
export default{  
    data(){
        return{
           dcHeroes:[{a:'a'},{a:'b'},{a:'c'},{a:'d'}]
        }
    }
}
</script>