<template>
  <q-page>
    <q-item v-ripple tag="label">
      <q-item-section avatar>
        <q-radio v-model="messageType" val="CUSTOM" color="teal" />
      </q-item-section>
      <q-item-section>
        <q-item-label>Custom Message</q-item-label>
      </q-item-section>
    </q-item>
    <q-item v-ripple tag="label">
      <q-item-section avatar>
        <q-checkbox v-model="messageType" val="CUSTOM" color="teal" />
      </q-item-section>
      <q-item-section>
        <q-item-label>Custom Message</q-item-label>
      </q-item-section>
    </q-item>
    <q-virtual-scroll
      :items="rowCountArray"
      style="height: 700px;"
    >
      <template v-slot="{ item }">
        <q-item>
          <q-item-section>
            <q-input
              :value="item"
            />
          </q-item-section>
        </q-item>
      </template>
    </q-virtual-scroll>
  </q-page>
</template>

<script>
export default {
  name: 'PageIndex',
  data () {
    return {
      virtualScrollElements: 1000,
      messageType: 'OTHER'
    }
  },
  computed: {
    rowCountArray () {
      return [...Array(this.virtualScrollElements).keys()]
    }
  }
}
</script>
