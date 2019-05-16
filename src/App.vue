<template>
  <div id="app">
    <Homepage/>
  </div>
</template>

<script>
import Homepage from '@/components/Homepage'

export default {
  name: 'app',
  components: { Homepage  }
}
</script>

<style>
    @import url('https://fonts.googleapis.com/css?family=Roboto');

    html, body {
        height: 100%;
    }

    body {
        margin: 0;
        font-family: 'Roboto';
    }

</style>
