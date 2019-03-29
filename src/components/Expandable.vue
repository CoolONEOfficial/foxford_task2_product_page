<template>
    <div>
        <div id="box" :style="`${expanded ? 'min-height' : 'max-height'}: ${expanded ? 'auto' : height}; overflow: hidden;`">
            <slot></slot>
            <div id="gd" :style="`background-image: ${expanded ? 'unset' : 'linear-gradient(to bottom, transparent 70% , #fafafa )'};`"></div>
        </div>
        <v-layout class="mt-1" row @click="expanded = !expanded">
            <v-icon small color="#003980" class="pr-2">fas fa-chevron-{{expanded ? 'up' : 'down'}}</v-icon>
            <a>{{ expanded ? textClose : textOpen }}</a>
        </v-layout>
    </div>
</template>

<script>
    export default {
        name: "Expandable",
        props: [
            'height',
            'textOpen',
            'textClose',
        ],
        data() {
            return {
                'expanded': false,
            }
        },
    }
</script>

<style scoped>
    #box {
        position: relative;
        overflow: hidden;
    }

    #gd {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        text-align: center;
        margin: 0; padding: 70px 0;
    }
</style>