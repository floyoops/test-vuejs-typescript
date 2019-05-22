<template>
    <div class="counterSub">
        <h1>counter sub</h1>
        <div>propCounterSubMessage: {{ propCounterSubMessage.message }}</div>
        <div>localCounterSubMessage: {{ localCounterSubMessage.message }}</div>
    </div>
</template>

<script lang="ts">
import {Component, Prop, Vue} from "vue-property-decorator";
import {MessageT} from '@/views/Home.vue';

@Component
export default class CounterSub extends Vue {
    // props
    @Prop(Object) propCounterSubMessage: MessageT

    // data
    localCounterSubMessage: MessageT = this.propCounterSubMessage
}
</script>
