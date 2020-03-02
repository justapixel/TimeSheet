<template>
  <div class="home">
    <TimeSheet/>
  </div>
</template>

<script>
// @ is an alias to /src
import TimeSheet from '@/components/TimeSheet.vue';

export default {
  name: 'Home',
  components: {
    TimeSheet
  }
}
</script>
