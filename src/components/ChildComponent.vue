<template>
  <h2>I'm child component</h2>

  <div :class="[$style.myClass, $style.button]">hello world</div>
  <p>using imported scss : {{ $style.button }}</p>
  <p>using imported scss : {{ $style.myClass }}</p>
</template>

<style lang="scss" module>
@import '../assets/utils.scss';

.myClass {
  color: red;
}
</style>
