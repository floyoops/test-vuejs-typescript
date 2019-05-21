<template>
    <div class="counterSub">
        <h1>counter sub</h1>
        <div>propCounterSubMessage: {{ propCounterSubMessage }}</div>
        <div>localCounterSubMessage: {{ localCounterSubMessage }}</div>
    </div>
</template>

<script lang="ts">
import {Component, Prop, Vue} from "vue-property-decorator";

@Component
export default class CounterSub extends Vue {
    @Prop(String) propCounterSubMessage: string
    localCounterSubMessage = this.propCounterSubMessage

    mounted() {
        console.log('mounted localCounterSubMessage')
    }
}
</script>
