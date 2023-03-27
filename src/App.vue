<script lang="ts" setup>
import { ref } from 'vue'
import { NSwitch, NForm, NGrid, NFormItemGi } from 'naive-ui'

const show = ref(false)
const show1 = ref(false)
const show2 = ref(false)
</script>

<template>
  <NForm>
    <p>with v-if, it's fine to hide / show</p>
    <NSwitch v-model:value="show1"></NSwitch>
    <NGrid>
      <NFormItemGi v-if="show1">222</NFormItemGi>
    </NGrid>
    <p>with layoutShiftDisabled, it's fine to hide / show</p>
    <NSwitch v-model:value="show2"></NSwitch>
    <NGrid layoutShiftDisabled>
      <NFormItemGi v-show="show2">333</NFormItemGi>
    </NGrid>
    <p>
      with v-show and no layoutShiftDisabled, it's not good to hide / show, at this time, if you
      switch the other two, it's also got error in console
    </p>
    <NSwitch v-model:value="show"></NSwitch>
    <NGrid>
      <NFormItemGi v-show="show">111</NFormItemGi>
    </NGrid>
  </NForm>
</template>
