<template>
  <div class="q-pa-md">
    <div ref="scrollTargetRef" style="max-height: 300px; overflow: auto;">
      <q-infinite-scroll @load="onLoadRef" :offset="250" :scroll-target="$refs.scrollTargetRef">
        <div v-for="(item, index) in itemsRef" :key="index" class="caption">
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate voluptas eveniet porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam exercitationem aut, natus minima, porro labore.</p>
        </div>
        <template v-slot:loading>
          <div class="row justify-center q-my-md">
            <q-spinner-dots color="primary" size="40px" />
          </div>
        </template>
      </q-infinite-scroll>
    </div>

    <div id="scroll-target-id" style="max-height: 300px; overflow: auto;">
      <q-infinite-scroll @load="onLoadId" :offset="250" scroll-target="#scroll-target-id">
        <div v-for="(item, index) in itemsId" :key="index" class="caption">
          <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rerum repellendus sit voluptate voluptas eveniet porro. Rerum blanditiis perferendis totam, ea at omnis vel numquam exercitationem aut, natus minima, porro labore.</p>
        </div>
        <template v-slot:loading>
          <div class="row justify-center q-my-md">
            <q-spinner-dots color="primary" size="40px" />
          </div>
        </template>
      </q-infinite-scroll>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      itemsRef: [{}, {}, {}, {}, {}, {}, {}],
      itemsId: [{}, {}, {}, {}, {}, {}, {}]
    }
  },

  methods: {
    onLoadRef (index, done) {
      setTimeout(() => {
        if (this.itemsRef) {
          this.itemsRef.push({}, {}, {}, {}, {}, {}, {})
          done()
        }
      }, 2000)
    },

    onLoadId (index, done) {
      setTimeout(() => {
        if (this.itemsId) {
          this.itemsId.push({}, {}, {}, {}, {}, {}, {})
          done()
        }
      }, 2000)
    }
  }
}
</script>
