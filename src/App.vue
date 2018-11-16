<template>
  <div class="container">
    <app-header :item-count="items.length" :max-item="maxItem"></app-header>
     <app-new-item @itemAdded="addItem" :items="items"></app-new-item>
     <app-item-layout :items="items" @itemRemoved="removeItem"></app-item-layout>
     <div class="row mt-3">
       <div class="col-sm-12 text-center">
         <div class="alert alert-info">
           Click on a Item to delete!
         </div>
       </div>
     </div>
   
  </div>
</template>

<script>
import Header from './components/Header.vue';
import ItemLayout from './components/ItemsLayout.vue';
import NewItem from './components/NewItem.vue'
export default {
  data: function(){
    return{
      items: [
       
      ],
      maxItem: 10
    }
  },
  components:{
    appItemLayout:ItemLayout,
    appNewItem: NewItem,
    appHeader: Header,

  },
  methods:{
    addItem(item){
      if(this.items.length>=this.maxItem){
        return alert('Max! pls remove item first!')
      } else
        this.items.push(item);
    },
    removeItem(index){
      this.items.splice(index,1);
    }
  }
}
</script>

<style>
  
</style>
