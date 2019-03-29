<template>
    <v-layout column>
        <v-layout row>
            <rating :stars="stars"></rating>
            <span class="pt-1 pl-1 pb-3">{{ `${helpful} visitors found this helpful` }}</span>
        </v-layout>
        <h3>{{ title }}</h3>
        <div class="mt-2"></div>
        <expandable v-if="text.length > 0" height="100px" text-open="view more" text-close="view less">
            <span style="font-size: 12pt;">{{ text }}</span>
        </expandable>
        <h3 v-if="positive" class="pt-3">I would recommend this product to a friend.</h3>
        <v-layout class="mt-3" style="color: grey;" row>
            <a v-if="short"><strong>{{ nickname }}</strong></a>
            <a v-else style="color: grey;">{{ nickname }}</a>
            <span class="px-1">{{location.length > 0 ? ` | ${location} | ` : ''}}</span>
            <span>{{ date }}</span>
        </v-layout>
        <v-layout v-if="!short" class="pt-3" row>
            <h3 class="pt-2 pr-3">Was this helpful?</h3>
            <v-btn>Yes</v-btn>
            <v-btn>No</v-btn>
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