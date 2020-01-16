<template>
  <div id="app">
  {{ info }}
</div>
</template>




<script>
import axios from 'axios';


export default {
  data () {
    return {
      info: null
    }
  },
  mounted () {
    // http://kafka-bridge-route-rvr.apps.cluster-avaya-fb13.avaya-fb13.example.opentlc.com/consumers/rvr-group/instances/rvr-consumer-aut/records
    
  const options = {
  headers: {'Accept': 'application/vnd.kafka.json.v2+json'}
};
    
    axios
      .get('http://kafka-bridge-route-rvr.apps.cluster-avaya-fb13.avaya-fb13.example.opentlc.com/consumers/rvr-group/instances/rvr-consumer/records',options)
      .then(response => (this.info = response))
  }
}
</script>
