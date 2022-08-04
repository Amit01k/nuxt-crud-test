<template>
    <div>

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
        <div class="">

            <h6 class="text-center text-lg bg-gray-700 text-gray-100 mx-32 rounded-lg mb-5 m-2">Please choose items to
                your bucket</h6>
            <div class="flex flex-row ml-64 space-x-2 ">
                <div class="basis-1/4 bg-red-400 rounded-md ">
                    <div class="text-center text-lg">{{ apple.name }}</div>
                    <div class="text-center text-lg">{{ apple.count }}</div>
                    <div class="text-center"><button @click="per? add() : al()"
                            class="m-3 bg-slate-50 rounded-full text-lg h-10 w-10">+</button><button @click="per? remove() : al()"
                            class="m-3 bg-slate-50 rounded-full text-lg h-10 w-10">-</button></div>
                </div>
                <div class="basis-1/4 bg-orange-500 h-80 rounded-md">
                    <div class="text-center text-lg">{{ orange.name }}</div>
                    <div class="text-center text-lg">{{ orange.count }}</div>
                    <div class="text-center"><button @click="per? add1() : al()"
                            class="m-3 bg-slate-50 rounded-full text-lg h-10 w-10">+</button><button
                            @click="per? remove1() : al()" class="m-3 bg-slate-50 rounded-full text-lg h-10 w-10">-</button></div>
                </div>
                <div class="basis-1/4 bg-blue-200 rounded-md">
                    <div class="text-center text-lg">{{ grapes.name }}</div>
                    <div class="text-center text-lg">{{ grapes.count }}</div>
                    <div class="text-center"><button @click="per? add2() : al()"
                            class="m-3 bg-slate-50 rounded-full text-lg h-10 w-10">+</button><button @click="per? remove2() : al()"  class="m-3 bg-slate-50 rounded-full text-lg h-10 w-10">-</button></div>
                </div>
            </div>
        </div>
        <div class="m-8">
            <div>
                <h4 class="text-center">Basket stack</h4>
            </div>
            <center>

                <table class="w-64  items-center justify-center text-center">
                    <tr class="border-solid border-2 border-indigo-600 w-10"
                        v-for="(basket, index) in basket.slice().reverse()" :key="index">
                        <td :class="classes[basket]">{{ basket }}</td>
                    </tr>
                </table>
            </center>

            <!-- <div>{{ basket.join(",") }}</div><br /> -->
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            "apple": {
                name: "Apple",
                count: 10,
                color: ""
            },
            "orange": {
                name: "Orange",
                count: 10,
                color: ""
            },
            "grapes": {
                name: "Grapes",
                count: 10,
                color: ""
            },
            basket: [],
            classes: {
                "Apple": "apple",
                "Grapes": "grapes",
                "Orange": "orange"
            },
            per: false,
        }


    },
    created() {
        this.per = this.$route.params.per;
        if (this.per === "all") {
            this.per = true;
        }
        else {
            this.per = false
        }
        console.warn(this.per)
    },

    methods: {
        add() {
            if (this.apple.count > 0) {
                this.apple.count = this.apple.count === 0 ? 0 : this.apple.count - 1;
                this.basket.push(this.apple.name)

            }
            else {
                alert("you already aaded 10 item")
            }

        },
        remove() {
            if (this.basket.at(-1) == this.apple.name) {
                this.apple.count = this.apple.count === 10 ? 10 : this.apple.count + 1;
                this.basket.pop()
            }
            else {
                alert("You have selected invalid item")
            }
        },
        add1() {
            if (this.orange.count > 0) {
                this.orange.count = this.orange.count === 0 ? 0 : this.orange.count - 1;
                this.basket.push(this.orange.name)
            }
            else {
                alert("You have selected invalid item")
            }
        },
        remove1() {
            if (this.basket.at(-1) == this.orange.name) {
                this.orange.count = this.orange.count === 10 ? 10 : this.orange.count + 1;
                this.basket.pop()
            }
            else {
                alert("You have selected invalid item ")
            }
        },
        add2() {
            if (this.grapes.count > 0) {
                this.grapes.count = this.grapes.count === 0 ? 0 : this.grapes.count - 1;
                this.basket.push(this.grapes.name)
            }
            else {
                alert("You have selected invalid item ")
            }

        },
        remove2() {
            console.warn(this.basket.at(-1))
            if (this.basket.at(-1) == this.grapes.name) {
                this.grapes.count = this.grapes.count === 10 ? 10 : this.grapes.count + 1;
                this.basket.pop()
            }
            else {
                alert("You have selected invalid item ")
            }
        },
        al(){
            alert("You dont have access")
        }
    }
}
</script>
<style>
.apple {
    background-color: red;
}

.orange {
    background-color: orange;
}

.grapes {
    background-color: greenyellow;
}
</style>