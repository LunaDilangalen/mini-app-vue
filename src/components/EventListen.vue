<template>
  <div class="event-listen">
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
      var response = window.Event.emit('payment', JSON.stringify(payload))
      alert(response)
    },
    promo () {
      const payload = {
        message: 'You won 42069.99 PhP'
      }
      window.Event.emit('notification', JSON.stringify(payload))
    },
    checkout () {
      const payload = {
        message: 'Request for geolocation'
      }
      window.Event.emit('location', JSON.stringify(payload))
    },
    somefunc () {
      const payload = {
        id: '2392810320',
        message: 'Request database access'
      }
      window.Event.emit('getDBAccess', JSON.stringify(payload))
    }
  }
}
</script>

<!-- <style>
body {
  background-color: #93b874;
}
</style> -->
