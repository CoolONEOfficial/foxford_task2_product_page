<template>
    <div>
        <div id="mainH">
            <v-layout row justify-center>
                <v-flex xs1>
                    <a id="logo">sears</a>
                </v-flex>
                <v-flex xs7>
                    <v-layout column>

                        <v-layout row pt-3>
                            <a>sdf</a>
                            <a>sdfsdf</a>
                        </v-layout>

                        <v-text-field class="pa-0 ma-0"
                                      color="white"
                                      solo
                                      style="max-height: 30px;"

                        ></v-text-field>

                    </v-layout>
                </v-flex>
            </v-layout>
        </div>
        <div id="bottomH">
        </div>
    </div>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style scoped lang="scss">
    @import "../styles/vars";

    @font-face {
        font-family: 'Helvetica Neue Cyr Thin';
        src: url('../assets/fonts/HelveticaNeueCyr-Thin.eot');
        src: url('../assets/fonts/HelveticaNeueCyr-Thin.eot?#iefix') format('embedded-opentype'),
        url('../assets/fonts/HelveticaNeueCyr-Thin.woff') format('woff'),
        url('../assets/fonts/HelveticaNeueCyr-Thin.ttf') format('truetype');
        font-weight: normal;
        font-style: normal;
    }

    .v-container {
        padding: 0 !important;
    }

    #logo {
        font-family: 'Helvetica Neue Cyr Thin', sans-serif;
        font-weight: 100;
        font-style: normal;
        font-size: 45pt;
        color: white;
    }

    #mainH {
        background: $primary;
        height: 88px;
    }

    #bottomH {
        background: $secondary;
        height: 3em;
    }

</style>