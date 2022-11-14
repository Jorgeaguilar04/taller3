<template>
  <div class="about">
 <ul>
 <li v-for="(Typeservice,i) in Typeservice" :key="i"></li>
 <h1> {{Typeservice}}</h1>
 </ul>
  </div>
</template>

<script>
import Typeservice from "../services/api"
export default{
name: "Home",
data(){
return{
Typeservice: []
}
},
methods: {
 async getTypeservice () {
 const response= await Typeservice.getTypeservice()
 this.Typeservice = response.data
 }
 },
 created () {
 this.getTypeservice()
 }
 }
</script>