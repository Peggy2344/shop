<template lang="pug">
  #home
    b-row
      b-col(cols="12" md="6" lg="3" v-for="(item, index) in items" :key="index")
        b-card(:title="item.name" :img-src="item.img" img-top :sub-title="'$'+item.price")
          b-button(variant="info" @click="addCart(item)")
            font-awesome-icon(:icon="['fas', 'shopping-cart']")
            | &nbsp;加入購物車
</template>

<script>

export default {
  name: 'Home',
  data () {
    return {
      items: [
        {
          img: 'https://e.ecimg.tw/items/DYAJCHA900AP7EG/000002_1604373280.jpg',
          name: 'Airpods Pro',
          price: 6090
        },
        {
          img: 'https://f.ecimg.tw/items/DYAN70A900AUPA5/000002_1599102543.jpg',
          name: '小米手環5',
          price: 845
        },
        {
          img: 'https://c.ecimg.tw/items/DCAN8JA9009OS4V/000002_1596181202.jpg',
          name: '羅技M720滑鼠',
          price: 888
        },
        {
          img: 'https://b.ecimg.tw/items/DMBF05A900AWDE6/000002_1601278839.jpg',
          name: 'Dyson V8 無限吸塵器',
          price: 12900
        }
      ]
    }
  },
  methods: {
    addCart (item) {
      // 呼叫 mutations
      this.$store.commit('addCart', item)
    }
  }
}
</script>
