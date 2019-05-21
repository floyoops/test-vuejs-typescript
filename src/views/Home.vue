<template>
  <div class="home">
    <Counter :prop-message="localHomeMessage"></Counter>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Counter  from '@/components/Counter'

@Component({
  components: {
    Counter,
  }
})
export default class Home extends Vue {
  localHomeMessage = 'message of home'

  mounted() {
    console.log('mounted home', this.localHomeMessage)
    let count = 0
    setInterval(() => {
      count = count + 1
      this.localHomeMessage = 'message ' + count
    }, 1000)
  }
}
</script>
