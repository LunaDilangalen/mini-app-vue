<template>
  <div class="some-scripts">
    <button @click="sayToAndroid('Hello From Mini App')">Say Hello!</button>
    <button @click="someEventFunc()">Some Event Button</button>
    <button @click="sendData()">Send Some Data</button>
    <button @click="getGeolcation()">Get Geolocation</button>
    <button @click="getLatestLocation()">Get Geolocation V2</button>
  </div>
</template>

<script>
window.androidObj = function AndroidClass () {}

export default {
  methods: {
    sayToAndroid (message) {
      console.log('Hello World!')
      window.JSBridge.showMessageInNative(message)
    },
    someEventFunc () {
      console.log('The End is Worlding')
      window.EventCatcher.emitEvent('payment')
    },
    sendData () {
      var response
      const payload = {
        notificationID: 'someUUID',
        message: 'Transaction Successful'
      }
      response = window.JSBridge.receiveData(JSON.stringify(payload))
      console.log(response.concat(' Concat-ed this string in mini app client'))
    },
    getGeolcation () {
      var response
      response = window.JSBridge.displayGeolocation('send me geolocation')
      console.log(response)
    },
    getLatestLocation () {
      const request = {
        miniAppID: '0bf409ca-c677-4bb5-821e-d1a49745636d',
        message: 'Request for latest location'
      }
      var response = window.JSBridge.fetchLatestLocation(JSON.stringify(request))
      console.log('Latest Location: '.concat(response))
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
