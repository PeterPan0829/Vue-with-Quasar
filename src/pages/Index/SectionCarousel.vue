<template>
<div class="q-pa-md">
  <q-carousel animated v-model="slide" arrows navigation infinite autoplay>
    <q-carousel-slide :name="1" img-src="../../assets/Austrian-forwarder.jpg" />
    <q-carousel-slide :name="2" img-src="../../assets/shipping_forwarder_freight_services.jpg" />
    <q-carousel-slide :name="3" img-src="../../assets/Sea-Freight-Forwarding-Services.jpg" />
    <q-carousel-slide :name="4" img-src="../../assets/PRIMELOGISTICS.jpg" />
  </q-carousel>

  <q-input inverted-light color="white" placeholder="輸入運輸城市" :after="[{
    icon:'fas fa-search-location'
  }]" v-model="search">

        <q-autocomplete :static-data="{field: 'label', list: countries}" />
  </q-input>

</div>
</template>

<script>
export default {

  data () {
    return {
      slide: 3,
      search: '',
      countries: [{
        label: '台北市',
        icon: 'fas fa-map-marker-alt'
      },
      {
        label: '新北市',
        icon: 'fas fa-map-marker-alt'
      },
      {
        label: '台中市',
        icon: 'fas fa-map-marker-alt'
      },
      {
        label: '「網美景點」台中秋紅谷，秋季賞楓勝地',
        stamp: '台中市'
      },
      {
        label: '東京台場「獨角獸鋼彈」強勢來襲！精彩變身演出搶先看',
        stamp: '東京, 台場',
        rightTextColor: 'pink-13'
      }
      ]
    }
  },
  methods: {
    // advFilter (terms, { field, list }) {
    //   return _.filter(list, context => {
    //     return context[field].match(terms)
    //   })
    // }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->

<style lang="scss" scoped>
* {
  outline: 1px solid darkred;
}
</style>
