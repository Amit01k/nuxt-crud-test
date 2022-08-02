<template>
    <nav class="flex items-center justify-between flex-wrap bg-blue-700 p-6">
        <div class="flex items-center flex-shrink-0 text-white mr-6">
            <span class="font-semibold text-xl tracking-tight">Welcome!!</span>
        </div>
        <div>
            <!-- <a href="#" class="flex justify-endinline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0">LogOut</a> -->
            <nuxt-link to="/"
                class="flex justify-endinline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0">
                Logout</nuxt-link>
        </div>
    </nav>
    <div class="grid grid-cols-3 gap-5 mt-14">
        <div
            class="p-6 max-w-sm bg-red-800 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
            <a href="#">
                <h5 class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white">Apple</h5>
            </a>
            <!-- <div class="flex flex-1 justify-center p-9 text-4xl">{{ plusOne }}</div> -->
            <!-- <div class="flex flex-1 justify-center p-9 text-4xl">{{ apple }}</div> -->
            <div class="flex flex-1 justify-center">
                <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1" @click="addApple">+</button>
                <!-- <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1" @click="increment">+</button> -->
                <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1 "
                    @click="removeApple">-</button>
            </div>
        </div>
        <div
            class="p-6 max-w-sm bg-yellow-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
            <a href="#">
                <h5 class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white">Orange</h5>
            </a>
            <!-- <div class="flex flex-1 justify-center p-9 text-4xl">{{ plusoneone }}</div> -->
            <div class="flex flex-1 justify-center">
                <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                    @click="AddOrange">+</button>
                <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1 "
                    @click="removeOrange">-</button>
            </div>
        </div>
        <div
            class="p-6 max-w-sm bg-blue-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
            <a href="#">
                <h5 class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white">Grapes
                </h5>
            </a>
            <!-- <div class="flex flex-1 justify-center p-9 text-4xl">{{ plusoneotwo }}</div> -->
            <div class="flex flex-1 justify-center">
                <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1"
                    @click="addGrapes">+</button>
                <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1 "
                    @click="removeGrapes">-</button>
            </div>
        </div>
    </div>
    <div class="flex flex-1 justify-center box-border w-80 h-48
                border-4 bg-green-500 m4 rounded-sm">
        <div class="text-center p-5 ">
            <p class="text-lg text-slate-100 border-red-600 bg-red-400 rounded-md m-2 px-4">Apple</p>
            <p class="text-lg text-slate-100 border-red-600 bg-orange-400 rounded-md m-2 px-4">Orange</p>
            <p class="text-lg text-slate-100 border-red-600 bg-green-400 rounded-md m-2 px-4">Grapes</p>
        </div>
        <button @click="amit">hii amit click this</button>
       
        
    </div>
     <div>
            <p>{{appleStore}}</p>
            <p>{{orangeStore}}</p>
            <p>{{grapestore}}</p>
            <p>{{basket}}</p>
        </div>
</template>
    <script >
import { remove } from '@vue/shared'


    export default{
        data(){
            return{
                apple:'',
                orange:'',
                grapes:'',
                appleStore:[],
                orangeStore:[],
                grapestore:[],
                basket:[]
            }
            console.log(appele.length)
        },
        methods:{
            addApple(){
                this.appleStore.push("Apple")
                console.log("hii amti kaisa hai")
                // if(this.apple==10){

                // }
                // console.log(this.apple.length())

            },
            removeApple(){
                this.appleStore.pop()
            },
             addGrapes(){
                this.grapestore.push("grapes")
                console.log("hii amti kaisa hai")
                // if(this.apple==10){

                // }
                // console.log(this.apple.length())

            },
            removeGrapes(){
                this.grapestore.pop()
            },
             addOrange(){
                this.orangeStore.push("orange")
                console.log("hii amti kaisa hai")
                // if(this.apple==10){

                // }
                // console.log(this.apple.length())

            },
            removeOrange(){
                this.orangeStore.pop()
            }
        }

    }
    // const count = ref(0)
    // const one = ref(0)
    // const two = ref(0)
    // //console.log(two)
    // const plusOne = computed(() => count.value + 1)
    // const plusoneone = computed(() => one.value + 1)
    // const plusoneotwo = computed(() => two.value + 1)
    // function decrement() {
    //     count.value--
    // }
    // function increment() {
    //     count.value++
    //     console.log(count.value)
    // }
    // function decrementone() {
    //     one.value--
    // }
    // function incrementone() {
    //     one.value++
    //     console.log("oneone")
    // }
    
    // function decrementtwo() {
    //     two.value--
    // }
    // function incrementtwo() {
    //     two.value++
    //     console.log("oneone")
    // }
    
    </script>