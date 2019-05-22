<template>
  <div class="home">
    <Counter :prop-counter-message="ObjectHomeMessage"></Counter>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Counter  from '@/components/Counter'

export type MessageT = {
  message: string
}

@Component({
  components: {
    Counter,
  }
})


export default class Home extends Vue {
  // data (Object required for observer)
  ObjectHomeMessage: MessageT = {'message': 'message init'}

  mounted() {
    let count = 0
    setInterval(() => {
      count = count + 1
      this.ObjectHomeMessage.message = 'message ' + count
    }, 1000)
  }
}
</script>
