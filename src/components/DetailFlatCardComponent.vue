<template>
<div class="flat-card">
    <a class="show-card-link">Show card number</a>
    <div class="card-box" >
        <span class="white-logo"></span>
        <label class="card-name">Mark Henry</label>
        <label class="card-number">
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>
            <span class="dot"></span>0008</label>
        <p class="card-info">
            <span class="expired">Thru: 12/20</span>
            <span>CVC: <i>&lowast;&lowast;&lowast;</i></span>
        </p>
        <span class="visa-logo"></span>
    </div>
    <div class="indicator">
        <span class="dot active"></span>
        <span class="dot"></span>
        <span class="dot"></span>
    </div>
</div>
</template>
<script lang="ts">
import { defineComponent} from 'vue';
export default defineComponent({
  name: 'DetailFlatCardComponent'
});
</script>