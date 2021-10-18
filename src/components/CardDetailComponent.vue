<template>
<div class="card-detail-list">
        <div class="card-detail-field has-bg">
            <a ></a>
            <span class="detail-text">Card details</span>
            <button class="arrow"></button>
        </div>
        <div class="transactions has-bg">
            <a></a>
            <span class="detail-text">Set spend limit</span>
            <button class="arrow"></button>
        </div>
        <ul>
          <li>
              <a class="storage"></a>
              <p class="detail-item">
                <span class="detail-title">
                  <label>Hamleys</label>
                  <span>+ S$ 150</span>
                </span>
                <span class="date">20 May 2020</span>
                <span class="action">Refund on debit card</span>
              </p>
          </li>
          <li>
              <a class="flights"></a>
              <p class="detail-item">
                <span class="detail-title">
                  <label>Hamleys</label>
                  <span>- S$ 150</span>
                </span>
                <span class="date">20 May 2020</span>
                <span class="action">Charged to debit card</span>
              </p>
          </li>
          <li>
              <a class="megaphone"></a>
              <p class="detail-item">
                <span class="detail-title">
                  <label>Hamleys</label>
                  <span>- S$ 150</span>
                </span>
                <span class="date">20 May 2020</span>
                <span class="action">Charged to debit card</span>
              </p>
          </li>
          <li>
              <a class="storage"></a>
              <p class="detail-item">
                <span class="detail-title">
                  <label>Hamleys</label>
                  <span>- S$ 150</span>
                </span>
                <span class="date">20 May 2020</span>
                <span class="action">Charged to debit card</span>
              </p>
          </li>
      </ul>
      <a class="view-all">View all card transactions</a>
</div>
</template>

<script lang="ts">
import { defineComponent} from 'vue';
export default defineComponent({
  name: 'CardDetailComponent',
});
</script>