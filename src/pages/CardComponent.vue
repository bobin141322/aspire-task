<template>
<div class="top-card">
  <CardHeaderComponent/>
</div>
<div class="tab">
    <button class="active">My debit card</button>
    <button>All company cards</button>
</div>
<div id="debit-card" class="tabcontent">
  <div class="col-6 card-content">
    <DetailFlatCardComponent/>
    <CardSettingComponent class="destop-control"/>
  </div>
  <div class="col-6 detail-box">
     <CardSettingComponent class="mobile-control"/>
    <CardDetailComponent/>
  </div>
</div>
</template>


<script lang="ts">
import CardHeaderComponent from 'components/CardHeaderComponent.vue';
import DetailFlatCardComponent from 'components/DetailFlatCardComponent.vue';
import CardSettingComponent from 'components/CardSettingComponent.vue';
import CardDetailComponent from 'components/CardDetailComponent.vue';
import { defineComponent} from 'vue';

export default defineComponent({
  name: 'CardContainer',
  components: {DetailFlatCardComponent, CardSettingComponent, CardDetailComponent, CardHeaderComponent},
  setup() {
      const cards = [{
          id:1,
          number: '4151 5000 0000 0008',
          name: 'TRan Van A',
          expireDate: '08/2028'
      }];
      return cards;
  }
});
</script>