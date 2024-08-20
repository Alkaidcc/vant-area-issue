<template>
  <div>
    <van-field :model-value="formModel.addrName" name="addrName" label="目的地" is-link readonly placeholder="请选择地区"
      @click="showAreaPicker = true" />
    <van-popup v-model:show="showAreaPicker" :lazy-render="false" round position="bottom">
      <van-area ref="areaRef" :model-value="formModel.addrCode" title="目的地" :area-list="areaList" />
    </van-popup>
  </div>
</template>

<script setup lang="ts">
import { areaList } from '@vant/area-data'
import { ref, watch } from 'vue'
const formModel = defineModel<any>()
const props = defineProps({
  code: {
    type: String
  }
})
const showAreaPicker = ref(false)
const areaRef = ref()
watch(formModel, (val) => {
  console.log('val',val)
  console.log('options', areaRef.value.getSelectedOptions())
})
</script>

<style lang="less" scoped></style>
