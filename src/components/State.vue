<template>
    <chart-label
        class="vue-workflow-chart-state"
        :class="stylingClassState"
        :anchor="center"
        :text="label"
        @click="$emit('click', id)" />
</template>

<script>
import Label from "./Label.vue";

export default {
    name: "State",
    components: {
        chartLabel: Label,
    },
    props: {
        id: {
            type: String,
            required: true,
        },
        label: {
            type: String,
            required: true,
        },
        stylingClass: {
            type: String,
            default: "",
        },
        center: {
            type: Object,
            required: true,
        },
    },
    computed: {
        stylingClassState() {
            return (this.stylingClass) ? `vue-workflow-chart-state-${this.stylingClass}` : "";
        },
    },
};
</script>
