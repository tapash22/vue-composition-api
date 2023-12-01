<template>
    <div class="nav-box">
        <ul >
            <li class="navigation" v-for="list in lists" :key="list.id">
               {{ list.name }} 
            </li>
           
        </ul>
    </div>
</template>

<script>
export default {
    data(){
        return{
            lists:[
                {
                    id:1,
                    name:'Explorer'
                },
                {
                    id:2,
                    name:'Generate'
                },
                {
                    id:3,
                    name:'Collaborate'
                },
                {
                    id:4,
                    name:'Evaluate'
                },
                {
                    id:5,
                    name:'Communicate'
                },
            ]
        }
    }
}
</script>

<style scoped>
.nav-box{
    background: rgba(128, 128, 128, 0.669);
    box-shadow: 2px 2px 3px black;
    height: auto;
    padding: 0;
    margin: 0;
}
ul{
    display: flex; justify-content: center; padding: 10px;list-style: none;grid-gap: 20px;
}
</style>