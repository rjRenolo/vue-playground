<template>
  <div id="app" class="flex flex-col items-center h-vh bg-gray-0">
    <div class="form-container p-4 border">
      <form @submit.prevent="addItem()">
        <h1 class="text-center">Add Something to the List</h1>
        <div class="input-group flex">
          <input v-model="item_to_add" type="text" class="border rounded-md p-1">
          <input type="submit" value="Add" class="py-1 px-2">
        </div>
        <span v-if="form_error" class="text-xs text-red-400">Error, please fill this input.</span>
      </form>
    </div>
    <div class="list-container w-1/4">
      <ul>
        <li v-for="item in items" :key="item.id">{{item.title}}</li>
      </ul>
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data : function(){
    return ({
      fullName : 'Jhon Roland Renolo',
      item_to_add : '',
      form_error: false,
      items: [
        {
          id: 0,
          title: 'Hello'
        },
        {
          id: 1,
          title: 'World'
        }
      ]
    })
  },
  methods : {
    addItem(){
      if(this.item_to_add == ''){
        this.form_error = true
      }else{
        this.form_error ? this.form_error = false :  ''
        var latestCount = this.items.length
        var item = {
          id: latestCount,
          title: this.item_to_add,
        }
        this.items = [...this.items, item]
        this.item_to_add = ''
      }
    }
  }
}
</script>
