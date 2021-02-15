<template>
    <nav id="nav">
        <p class="logo">THIS IS A TRAVEL WEBSITE</p>
        <ul class="nav-links">
            <li class="links">
                <router-link  to="/">home</router-link></li>
                <li v-for="destination in destinations" :key="destination.name" class="links">
                    <router-link :to="{
                        name:'destinationdetails',
                        params:{id:destination.id}
                        }">
                        {{destination.name}}
                        </router-link>
                </li>
            
        </ul>
    </nav>
</template>

<script>
import store from '@/store.js'
export default {
    data(){
        return{
            destinationid:this.$route.params.id,
            destinations:store.destinations
        }
    }
}
</script>
<style scoped>
#nav{
    display: flex;
    background-color: rgb(207, 199, 245);
}


#nav a {
  color: #2c3e50;
  text-decoration: none;
  font-weight: bold;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  padding: 0 10px;
}

#nav a.router-link-exact-active {
  color: #dd402b;
}
.nav-links{
    display: flex;
}
.links{
    padding-right: 20px;
    list-style: none;
}
.links:hover{
    text-decoration: underline;
}
.logo{
    font-size: 25px;
    color: #5f1159;
    font-weight: bold;
}
</style>