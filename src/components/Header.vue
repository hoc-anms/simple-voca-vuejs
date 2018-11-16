<template>
  <div class="row mb-3 ">
      <div class="col-sm-12">
          <h3>Item Added</h3>
          <div class="progress">
            <div class="progress-bar progress-bar-striped bg-success" role="progressbar" :style="{width:(itemCount/maxItem)*100+'%'}" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100"></div>
          </div>
          <span>{{itemCount}} / {{maxItem}}</span>
      </div>
 </div>
</template>

<script>
import Items from './Items.vue'
export default {
  props:['itemCount','maxItem'],

  
}
</script>

<style>

</style>
