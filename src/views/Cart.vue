<template lang="pug">
  #cart
    b-table(:items="items" :fields="fields" striped hover)
      template(v-slot:cell(action) = "data")
        b-button(variant="danger" @click="del(data.index)")
          font-awesome-icon(:icon="['fa','trash']")
</template>

<script>
export default {
  name: 'Cart',
  data () {
    return {
      fields: [
        {
          key: 'name',
          label: '商品名稱'
        },
        {
          key: 'price',
          label: '價格'
        },
        {
          key: 'action',
          label: '刪除'
        }
      ]
    }
  },
  computed: {
    items () {
      // 直接取 vuex 的 items
      // return this.$store.state.items
      // 直接呼叫 vuex 的 getters
      return this.$store.getters.items
    }
  },
  methods: {
    del (index) {
      this.$store.commit('delCart', index)
    }
  }
}
</script>
