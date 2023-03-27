<script lang="ts" setup>
import { ref } from 'vue'
import { NSwitch, NForm, NGrid, NFormItemGi } from 'naive-ui'

const show = ref(false)
const show1 = ref(false)
const show2 = ref(false)
</script>

<template>
  <NForm>
    <p>使用v-if 正常切换</p>
    <NSwitch v-model:value="show1"></NSwitch>
    <NGrid>
      <NFormItemGi v-if="show1">222</NFormItemGi>
    </NGrid>
    <p>添加 layoutShiftDisabled 正常切换</p>
    <NSwitch v-model:value="show2"></NSwitch>
    <NGrid layoutShiftDisabled>
      <NFormItemGi v-show="show2">333</NFormItemGi>
    </NGrid>
    <p>使用v-show且不添加 layoutShiftDisabled, 隐藏时报错, 此时切换另外两个也会报错</p>
    <NSwitch v-model:value="show"></NSwitch>
    <NGrid>
      <NFormItemGi v-show="show">111</NFormItemGi>
    </NGrid>
  </NForm>
</template>
