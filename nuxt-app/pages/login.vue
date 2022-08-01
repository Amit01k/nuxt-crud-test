<template>

<div>
   <div>
    <h1>login</h1>
    <p>email<input type="email" v-model="email" /></p>
    <p>password <input type="password" v-model="password"/></p>
    <button @click="login"> login</button>
   </div>
</div>


</template>


<script>
import axios from "axios"
export default{
    name:"login",
    data(){
        return{
            email:"",
            password:""

        }
    },
    methods:{
        async login(){
            let result=await axios.get(
                `http://localhost:3000/users?email=${this.email}&password=${this.password}`

            )
            console.log(result)

            }
            // console.log(this.email,this.password)

    }
}




</script>