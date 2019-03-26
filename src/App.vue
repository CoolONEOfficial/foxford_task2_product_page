<template>
    <v-app>
        <v-content>
            <Header/>
            <Body/>
        </v-content>
    </v-app>
</template>

<script>
    import Header from "./components/Header";
    import Body from "./components/Body";

    export default {
        name: 'App',
        components: {
            Body,
            Header,
        },
        data() {
            return {
                'primary': '#002859',
                'secondary': '#003980',
                'light': '#005ccc',
            }
        }
    }
</script>
