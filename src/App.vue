<template>
  <div id="app" class="h-screen bg-gray-50">
    <div class="container flex justify-center align-center w-full">
      <div class="flex flex-col items-center bg-gray-50 border w-1/5 p-4 rounded-md border-gray-300 shadow-md justify-center">
        <h1 class="text-center text-xl text-green-400 mb-4">Hello <span class="font-medium text-blue-400 underline">{{fullName}}</span></h1>
        <input class="focus:border-light-blue-500 
                      w-full
                      focus:ring-1
                      focus:ring-light-blue-500 
                      focus:outline-none 
                      text-sm text-black 
                      placeholder-gray-500 
                      border 
                      border-gray-200 
                      rounded-md 
                      py-2 pl-2
                      mb-2" 
                      type="text" name="fullName" v-model="fullName">
          <button @click="sayIt()" class="w-1/2 border rounded-lg bg-blue-300 text-gray-50 py-1 text-lg font-medium hover:bg-blue-800 focus:outline-none">Say Hi</button>
      </div>
    </div>

    
  </div>
</template>

<script>

export default {
  name: 'App',
  data : function(){
    return ({
      fullName : 'Jhon Roland Renolo',
      is_say : false
    })
  },
  methods : {
    sayIt(){
      alert(`Hey ${this.fullName}!, You clicked the awsome button`)
    }
  }
}
</script>
