<template>
    <div class="inputField">
     <div class="item">
       <input type="text" placeholder=" + New Item " v-model="newItem" class="input-text">
       <button class="addButton" @click="addItem">Add</button>
     </div>
     <shoppingListItem 
      v-for="item in items" 
      :key="item.id" 
      :item="item"
      @removeClicked="removeItem"
      />
    </div>
   </template>
   
     <script>
   import shoppingListItem from './shoppingListItem.vue'
   export default {
    components: {
      shoppingListItem
    },
     data() {
     return {
       newItem: '',
         items: [
         {title: 'Milk', completed: false, id: '1'},
         {title: 'Eggs', completed: false, id: '2'},
         {title: 'Butter', completed: false, id: '3'},
         {title: 'Cheese', completed: true, id: '4'},
         {title: 'Yoghurt', completed: true, id: '5'}
         ]
       }
     },
     methods: {
       addItem() {
        this.items.push({
         title: this.newItem, 
         completed: false,
         id: Math.random() 
       })
       this.newItem = ''
       },
       removeItem(id) {
         const index = this.items.findIndex(el => el.id === id)
         this.items[index].completed = true
       }
     }
   }
   </script>