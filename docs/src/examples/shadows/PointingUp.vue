<template>
  <div class="q-pa-md">
    <div
      class="flex inline shadow-box flex-center"
      v-for="n in 24" :key="n"
      :class="`shadow-up-${n}`"
    >
      .shadow-{{ n }}
    </div>
  </div>
</template>

<style lang="stylus" scoped>
@import '~quasar-variables'

.shadow-box
  width 90px
  height 90px
  margin 25px
  border-radius 50%
  font-size 12px
.doc-inset-shadow
  border 1px solid $grey-3
</style>
