<script setup lang="ts">
import { PropType, ref } from 'vue'

import { Colors } from '../../ enums/Colors.enums'

// interface
interface TabsArray {
  label: string
  value: string
}

// props
const props = defineProps({
  initialTab: {
    type: String,
    default: 'all'
  },
  tabs: {
    type: Array as PropType<TabsArray[]>,
    default: () => []
  }
})

const tab = ref(props.initialTab)
const tabList = ref(props.tabs)
</script>

<template>
  <section>
    <q-tabs
        v-model="tab"
        class="text-black"
        :style="{
          background: Colors.GRAY
        }"
        no-caps
        active-class="active-tab-class"
        indicator-color="secondary"
      >
        <q-tab
          v-for="tab in tabList"
          :key="tab.value"
          :name="tab.value"
          :label="tab.label"
          content-class="tab-item"
        />
      </q-tabs>
  </section>
</template>


<style scoped lang="scss">
@import url('./Tab.scss');
</style>
