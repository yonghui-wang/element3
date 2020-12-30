<template>
  <div class="cascade-select">
    <el-select v-model="modelValues" :allow-create="true">
      <el-option
        v-for="op in selectDataList"
        :key="op.value"
        :value="op.value"
        >{{ op.label }}</el-option
      >
    </el-select>
    <p>testing...</p>
    <p v-for="op in selectDataList" :key="op.value">{{ op.value }}</p>
  </div>
</template>

<script>
import { defineComponent, ref } from 'vue'

const treeData = [
  {
    label: 'mxnet',
    value: 'mxnet'
  },
  {
    label: 'tensorflow',
    value: 'tensorflow'
  },
  {
    label: 'pytorch',
    value: 'pytorch'
  }
]

export default defineComponent({
  name: 'cascade-select',
  // eslint-disable-next-line @typescript-eslint/no-empty-function
  setup(props, context) {
    const modelValues = ref('')
    const selectDataList = ref([])
    // selectDataList.value = [
    //   {
    //     label: 'tdfgdrflow',
    //     value: 'tendfgdlow'
    //   }
    // ]

    setTimeout(() => {
      selectDataList.value = treeData
    }, 5000)

    return {
      modelValues,
      selectDataList
    }
  }
})
</script>
