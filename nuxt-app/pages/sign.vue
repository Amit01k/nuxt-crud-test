<template>

<div>
    <h2>sign</h2>
    <div>
        <p >name<input type="text" v-model="name"/></p>
        <p>email<input type="email" v-model="email"/></p>
        <p>password<input type="password" v-model="password"/></p>
        <button @click="sign">sign</button>
    </div>
</div>




</template>

<script>
// import { sign } from 'crypto';
import axios from "axios"
import indexVue from "./index.vue"


export default{
    name:"sign",
    data()
    {
        return {
            name:'',
            email:'',
            password:'',


        }
    },
    methods:{
        async sign(){
            console.warn("this is called",this.name,this.email,this.password)
            let result= await axios.post("http://localhost:3000/users",{
                name:this.name,
                email:this.email,
                password:this.password
            })
            console.warn(result)
            if(result.status==201){
                console.log("ho gya")
                this.$router.push({name:"bucket"})
            }

            


}
    }
}


</script>