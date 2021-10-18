<template>

<div class="card-header">
   <label>Available balance</label>
   <div class="card-bar">
       <span class="currency">
           S$
       </span>
       <span class="balance">3,000</span>
       <button class="add-new"><i></i> New card</button>

   </div>
</div>


</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'CardHeaderComponent',
});
</script>