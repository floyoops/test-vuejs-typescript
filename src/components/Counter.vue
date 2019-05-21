<template>
    <div class="counter">
        <h1>my counter</h1>
        <div>propMessage: {{ propMessage }}</div>
        <div>localMessage: {{ localMessage }}</div>
        <div>greet: {{ greet() }}</div>
        <div>greet computed: {{ greetComputed }}</div>
        <hr>
        <CounterSub :propCounterSubMessage="localMessage"></CounterSub>
    </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'
import CounterSub from '@/components/CounterSub.vue';

@Component({
    components: {
        CounterSub,
    }
})
export default class Counter extends Vue {
    @Prop(String) propMessage
    localMessage = this.propMessage
    greet(): string {
        return 'greet ' + this.localMessage
    }
    get greetComputed(): string {
        return 'greet computed ' + this.localMessage
    }
    created() {
        console.log('created counter')
    }
    mounted () {
        console.log('mounted counter', this.localMessage);
    }
}


</script>

