<template>
<h1 v-once>{{count}}</h1>
<!-- <h1 v-if="isShowing" v-html="title"></h1>
<h2 v-else-if="isShowing===null">Else if Block</h2>
<h2 v-else>Else Block</h2> -->
<p1>Something new</p1>
</template>
<script>
export default{
    data(){
        return{
            title:`<h1>Hey vue 3</h1>`,
            isShowing:true,
            count:0
        }
    },
    mounted(){
            setInterval(()=>{
this.count++;
            },1000)
    }
}

</script>