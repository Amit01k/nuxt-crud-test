<template>
    <div class="flex justify-center mt-20">
        
        <div class="bg-orange-400 border-spacing-1 w-2/4 flex justify-items-center flex-col">
            <h1 class="text-2xl text-yellow-300 text-center">This is login page </h1>
            <p class="text-center">Email<input
                    class="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500 mx-auto "
                    type="email" v-model="email" /></p>
            <p class="text-center">Password <input
                    class="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500 mx-auto"
                    type="password" v-model="password" /></p>
            <div class="flex">
                <div class=" flex justify-center">
                    <button @click="login"
                class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-6 rounded-md mx-72 mt-4 mb-4 "> login</button>
                </div>
            </div>
        </div>
    
    </div>



</template>


<script>
import axios from "axios"
export default {
    name: "login",
    data() {
        return {
            email: "",
            password: "",
            per: ""


        }
    },
    methods: {
        async login() {
            let per;
            let result = await axios.get(
                `http://localhost:3000/users?email=${this.email}&password=${this.password}`


            );
            console.warn(result.data)
            // console.log(this.email)
            //let { email, password } = result
            // console.log(email)
            
            if (result.status == 200 && result.data.length > 0) {
                per = result.data[0].permission;
                this.$router.push({ name: "item", params: { per } })
            }
            else {
                alert("please enter correct email and password")
            }
            console.warn(per)
            //console.log(result)

        }
        // console.log(this.email,this.password)

    }
}




</script>