<template>
  <div class="tr person" @click="edit">
    <div class="td index">
      {{index}}
    </div>
    <div class="td">
      <div class="info">
        <img
          class="avatar"
          :src="item.value.avatar"
          :key="item.value.avatar"
        />
        <span>{{item.value.name}}</span>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: ['item', 'index'],

  created() {
    console.log('created')
  },

  beforeUnmount() {
    console.log('destroyed')
  },

  methods: {
    edit() {
      // eslint-disable-next-line vue/no-mutating-props
      ((this.item as any).value as any).name += '#'
    },
  },
})
</script>

<style scoped>
.index {
  color: rgba(0, 0, 0, 0.2);
  width: 55px;
  text-align: right;
  flex: auto 0 0;
}

.person .td:first-child {
  padding: 12px;
}

.person .info {
  display: flex;
  align-items: center;
  height: 48px;
}

.avatar {
  width: 50px;
  height: 50px;
  margin-right: 12px;
}
</style>
