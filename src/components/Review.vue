<template>
    <v-layout column>
        <v-layout row>
            <rating :stars="stars"></rating>
            <span class="py-2 pl-1 pb-3">{{ `${helpful} visitors found this helpful` }}</span>
        </v-layout>
        <h3>{{ title }}</h3>
        <div class="mt-4"></div>
        <expandable height="100px" text-open="view more" text-close="view less">
            <span style="font-size: 12pt;">{{ text }}</span>
        </expandable>
        <v-layout class="mt-3" style="color: grey;" row>
            <a><strong>{{ nickname }}</strong></a>
            <span v-if="location != null" class="px-1">{{` | ${location} | `}}</span>
            <span>{{ date }}</span>
        </v-layout>
    </v-layout>
</template>

<script>
    import Rating from "./Rating";
    import Expandable from "./Expandable";

    export default {
        name: "Review",
        components: {Expandable, Rating},
        props: [
            "short",
            "stars",
            "title",
            "text",
            "helpful",
            "nickname",
            "location",
            "date",
            "positive",
        ],
    }
</script>

<style scoped>

</style>