<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <TimeSheet msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import TimeSheet from '@/components/TimeSheet.vue'

export default {
  name: 'Home',
  components: {
    TimeSheet
  }
}
</script>
