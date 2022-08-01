<template>

<div>
    <h2 >This is signUp page</h2>
    <div>
        <p >name<input class ="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500" type="text" v-model="name"/></p>
        <p>email<input class ="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500" type="email" v-model="email"/></p>
        <p>password<input class ="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500" type="password" v-model="password"/></p>
        <button @click="sign" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full m-6">sign</button>
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