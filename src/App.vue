<template>
    <h3>模板语法</h3>
    <p>{{ rawhtml }}</p>
    <p v-html="rawhtml"></p>
    <p @click="increment">{{ count }}</p>
</template>

<script>
import { nextTick } from "vue";

export default {
    data() {
        return {
            rawhtml: "<span style=\"color: red;\">nihao</span>",
            count: 1,
        };
    },
    methods: {
        increment() {
            this.count++;
            nextTick(() => {
                this.count++;
            });
        },
    },
    mounted() {
        // this.increment();
    },
};
</script>
