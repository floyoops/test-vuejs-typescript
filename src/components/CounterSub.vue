<template>
    <div class="counterSub">
        <h1>counter sub</h1>
        <div>propCounterSubMessage: {{ propCounterSubMessage.message }}</div>
        <div>localCounterSubMessage: {{ localCounterSubMessage.message }}</div>
        <div>lastName: {{ localPeople.lastName }}</div>
        <ul>
            <li v-for="friend in localCounterSubMessage.friends">
                <span>{{ friend.lastName }}</span>
            </li>
        </ul>
    </div>
</template>

<script lang="ts">
import {Component, Prop, Vue} from "vue-property-decorator";
import {MessageT, PeopleT} from '@/views/Home.vue';

@Component
export default class CounterSub extends Vue {
    // props
    @Prop(Object) propCounterSubMessage: MessageT
    @Prop(Object) propPeople: PeopleT

    // data
    localCounterSubMessage: MessageT = this.propCounterSubMessage
    localPeople: PeopleT = this.propPeople
}
</script>
