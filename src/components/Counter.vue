<template>
    <div class="counter">
        <h1>my counter</h1>
        <div>propCounterMessage: {{ propCounterMessage.message }}</div>
        <div>localCounterMessage: {{ localCounterMessage.message }}</div>
        <div>greet: {{ greet() }}</div>
        <div>computed: {{ greetComputed }}</div>
        <CounterSub :prop-counter-sub-message="localCounterMessage"></CounterSub>
    </div>
</template>

<script lang="ts">
import CounterSub from '@/components/CounterSub.vue';
import {Component, Prop, Vue} from "vue-property-decorator";
import {MessageT} from "@/views/Home.vue";

@Component({
    components: {
        CounterSub,
    }
})
export default class Counter extends Vue {
    // props
    @Prop(Object) propCounterMessage: MessageT

    // data
    localCounterMessage = this.propCounterMessage

    // method
    greet(): string {
        return 'greet ' + this.localCounterMessage.message
    }

    // computed
    get greetComputed(): string {
        return 'greet computed ' + this.localCounterMessage.message
    }
}
</script>

