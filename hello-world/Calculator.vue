<style>
</style>

<template>
    <div>
        <h1>{{a}} + {{b}} = {{a+b}}</h1>
        <br/>
        <button @click="clickA">add a</button>
        <button @click="clickB">add b</button>
    </div>
</template>

<script type="text/javascript">
    export default{
            name:"WelcomePage",
            data:function(){
                return{
                    a:1,
                    b:2
                }
            },
            methods:{
                clickA(){
                  this.a++;
                },
                clickB(){
                  this.b++;
                }
            }
        }
</script>