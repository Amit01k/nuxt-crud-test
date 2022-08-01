<template>
    <nav class="flex items-center justify-between flex-wrap bg-blue-700 p-6">
    <div class="flex items-center flex-shrink-0 text-white mr-6">
        <span class="font-semibold text-xl tracking-tight">Welcome!!</span>
    </div>
        <div>
        <a href="#" class="flex justify-endinline-block text-sm px-4 py-2 leading-none border rounded text-white border-white hover:border-transparent hover:text-teal-500 hover:bg-white mt-4 lg:mt-0">LogOut</a>
        </div>
    </nav>
    <div class="grid grid-cols-3 gap-5 mt-14">
        <div class="p-6 max-w-sm bg-red-800 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
        <a href="#">
            <h5 class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white">Apple</h5>
        </a>
            <div class="flex flex-1 justify-center p-9 text-4xl">{{plusOne}}</div>
        <div class="flex flex-1 justify-center">
        <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1" @click="increment">+</button>
        <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1 " @click="decrement">-</button>
    </div>
    </div>
    <div class="p-6 max-w-sm bg-yellow-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
        <a href="#">
            <h5 class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white">Orange</h5>
        </a>
            <div class="flex flex-1 justify-center p-9 text-4xl">{{plusOne}}</div>
        <div class="flex flex-1 justify-center">
        <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1" @click="increment">+</button>
        <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1 " @click="decrement">-</button>
    </div>
    </div>
    <div class="p-6 max-w-sm bg-blue-500 rounded-lg border border-gray-200 shadow-md dark:bg-gray-800 dark:border-gray-700">
        <a href="#">
            <h5 class="mb-2 text-2xl text-center font-bold tracking-tight text-gray-900 dark:text-white">Grapes </h5>
        </a>
        <div class="flex flex-1 justify-center p-9 text-4xl">{{plusOne}}</div>
        <div class="flex flex-1 justify-center">
        <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1" @click="increment">+</button>
        <button class=" py-2 px-4 rounded-full h-14 w-14 bg-white text-black mx-1 " @click="decrement">-</button>
        </div>
    </div>
    </div>
   <div class="flex flex-1 justify-center box-border w-80 h-48
                border-4 bg-green-500 m4">
          <div>
            <h3>Heloo</h3>
        </div>
   </div>
    </template>
    <script setup>
    const count=ref(0)
    const plusOne=computed(()=>count.value + 1)
    function decrement(){
        count.value--
    }
    function increment(){
        count.value++
    }
    </script>