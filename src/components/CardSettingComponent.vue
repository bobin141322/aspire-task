<template>
    <ul class="setting-list">
        <li>
            <a class="freeze"></a>
            <span class="setting-text">Freeze card</span>
        </li>
        <li>
            <a class="spend-limit"></a>
            <span class="setting-text">Set spend limit</span>
        </li><li>
            <a class="gpay"></a>
            <span class="setting-text">Add to GPay</span>
        </li><li>
            <a class="replace-card"></a>
            <span class="setting-text">Replace card</span>
        </li><li>
            <a class="cancle-card"></a>
            <span class="setting-text">Cancel card</span>
        </li>
    </ul>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
export default defineComponent({
  name: 'CardSettingComponent',
});
</script>