<template>
  <div class="q-pa-md">
    <q-carousel
      animated
      v-model="slide"
      arrows
      navigation
      infinite
      autoplay

    >
      <q-carousel-slide :name="1" img-src="../../assets/Austrian-forwarder.jpg" />
      <q-carousel-slide :name="2" img-src="../../assets/shipping_forwarder_freight_services.jpg" />
      <q-carousel-slide :name="3" img-src="../../assets/Sea-Freight-Forwarding-Services.jpg" />
      <q-carousel-slide :name="4" img-src="../../assets/PRIMELOGISTICS.jpg" />
    </q-carousel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slide: 3
    }
  }
}
</script>
