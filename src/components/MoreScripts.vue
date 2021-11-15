<template>
  <div class="some-scripts">
    <button @click="pay()">Pay</button>
    <button @click="promo()">Click 2 Win</button>
    <button @click="checkout()">Checkout</button>
    <button @click="somefunc()">Unknown</button>
  </div>
</template>

<script>

export default {
  methods: {
    pay () {
      const payload = {
        amount: 9999.99,
        status: 'success'
      }
      var response = window.EventCatcher.emitEvent('payment', JSON.stringify(payload))
      alert(response)
    },
    promo () {
      const payload = {
        message: 'You won 42069.99 PhP'
      }
      var response = window.EventCatcher.emitEvent('notification', JSON.stringify(payload))
      alert(response)
    },
    checkout () {
      const payload = {
        message: 'Request for geolocation'
      }
      var response = window.EventCatcher.emitEvent('getGeolocation', JSON.stringify(payload))
      alert(response)
    },
    somefunc () {
      const payload = {
        id: '2392810320',
        message: 'Request database access'
      }
      var response = window.EventCatcher.emitEvent('getDBAccess', JSON.stringify(payload))
      alert(response)
    }
  }
}
</script>

<!-- <style>
body {
  background-color: #93b874;
}
</style> -->
