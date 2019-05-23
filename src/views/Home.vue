<template>
  <div class="home">
    <Counter :prop-counter-message="ObjectHomeMessage"></Counter>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Counter  from '@/components/Counter'

export type MessageT = {
  message: string,
  people: PeopleT,
  friends: FriendsT
}
export type PeopleT = {
  firstName: string,
  lastName: string
}

export type FriendsT = PeopleT[]

@Component({
  components: {
    Counter,
  }
})

export default class Home extends Vue {
  // data (Object required for observer)
  ObjectHomeMessage: MessageT

  // created
  constructor() {
    super()
    let people1: PeopleT = {'firstName': 'tim', 'lastName': 'chouette'}
    let people: PeopleT = {'firstName': 'michel', 'lastName': 'commun'}
    this.ObjectHomeMessage = {'message': 'message init', 'people': people, 'friends': [people1]}
  }

  // method
  mounted() {
    let count = 0
    setInterval(() => {
      count = count + 1
      this.ObjectHomeMessage.message = 'message ' + count
      this.ObjectHomeMessage.friends[0].lastName = 'aaaa' + count
    }, 1000)
  }
}
</script>
