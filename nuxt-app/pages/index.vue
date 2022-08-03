<!-- <template>
<div class="bg-green-400 m-44">

    <nuxt-link to="first">go to bucket page</nuxt-link>
    <p class="text-center text-red-400 text-3xl ">Welcome to our Nuxt-crud-page</p>
    <div class="m-8 items-center ">
        <nuxt-link to="login" class="border border-gray-400 px-4 py-2 max-w-xs rounded bg-teal-600 text-white ">Login</nuxt-link>
    <nuxt-link to="sign" class="border border-gray-400 px-4 py-2 max-w-xs rounded bg-teal-600 text-white">Sign Up</nuxt-link>
    </div>

    <p class=" text-xl text-gray-200">Lorem ipsum dolor sit amet consectetur adipisicing elit. Repellendus, asperiores assumenda quae culpa quidem consequuntur laborum est, iste, voluptate magnam ullam exercitationem architecto quod pariatur vitae eveniet earum molestias. Ducimus harum ratione, omnis veritatis totam quod sit quo? Iusto aspernatur dolore modi voluptate error et soluta consequatur, facilis perspiciatis non. Ipsam ex ad quod, vel ut totam ratione enim sunt.</p>
</div>



</template>
 -->



 <template>

<div class="">
   <div class="bg-orange-400 border-spacing-1 m-32">
    <h1 class="text-2xl text-yellow-300 text-center">This is login page </h1>
    <p>email<input class ="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500  " type="email" v-model="email" /></p>
    <p>password <input class ="border border-gray-400 block px-4 py-1 w-1/4 rounded focus:outline-none focus:border-teal-500" type="password" v-model="password"/></p>
    <button @click="login" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded-full m-6"> login</button>
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
            

            );
            console.log(this.email)
           let {email,password}=result
           console.log(email)
            if(result.status==200&& result.data.length>0){
                this.$router.push({name:"item"})
            }
            else{
                alert("please enter correct email and password")
            }
            //console.log(result)

            }
            // console.log(this.email,this.password)

    }
}




</script>
