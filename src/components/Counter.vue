<template>
    <div class="counter">
        <h1>my counter</h1>
    </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'
@Component
export default class Counter extends Vue {
    mounted: {
        console.log('mounted')
    }
}


</script>

