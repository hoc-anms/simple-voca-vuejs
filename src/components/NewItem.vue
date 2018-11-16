<template>
  <div class="row">
      <form >
          <div class="row">
               <div class="col-sm-8 offset-sm-2 col-md-6 offset-md-3 form-group">
                     <label for="">
                        You can saying something
                        <textarea class="form-group" v-model="item" name="" id="" cols="30" rows="10"></textarea>
                     </label>
                </div>
          </div>
          <div class="row">
              <div class="col-sm-8 offset-sm-2 col-md-6 offset-md-3 form-group">
                <button class="btn btn-success" @click.prevent="createNew">
                    Add
                </button>
              </div>    
          </div>

      </form>
  </div>
</template>

<script>
export default {
  props:['items'],
  data: function() {
    return {
      item: ""
    };
  },
  methods: {
    createNew() {
      if(this.item===''){
        return false;
      }else if(this.items.includes(this.item)){
        return alert('this item is exits in card ');
      } else{
         this.$emit("itemAdded", this.item);
         this.item = "";
      }
     
    }
  }
};
</script>

<style scoped>
textarea {
  width: 100%;
  resize: none;
}
form {
  width: 100%;
}
</style>
