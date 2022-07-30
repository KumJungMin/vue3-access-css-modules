<template>
  <div :class="$style.myClass">hello world</div>
  <p>using useCssModule: {{ $newStyle.myClass }}</p>
  <P>using getCurrentInstance:{{ $style.myClass }}</P>
</template>

<script setup>
import { getCurrentInstance, useCssModule } from 'vue'

const { $style } = getCurrentInstance().type.__cssModules
console.log('myClass', $style.myClass)

const $newStyle = useCssModule()
console.log('useCssModule: ', $newStyle.myClass)
</script>

<style lang="scss" module>
.myClass {
  color: blue;
}
</style>
