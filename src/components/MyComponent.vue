<template>
  <h2>I'm parent component</h2>

  <div :class="$style.myClass">hello world</div>
  <p>using useCssModule: {{ $newStyle.myClass }}</p>
  <P>using getCurrentInstance:{{ $style.myClass }}</P>

  <hr />
  <ChildComponent />
</template>

<script setup>
import ChildComponent from './ChildComponent.vue'
import { getCurrentInstance, useCssModule } from 'vue'

// 방법1
const { $style } = getCurrentInstance().type.__cssModules
console.log('myClass', $style.myClass)

// 방법2
const $newStyle = useCssModule()
console.log('useCssModule: ', $newStyle.myClass)
</script>

<style lang="scss" module>
.myClass {
  color: blue;
}
</style>
