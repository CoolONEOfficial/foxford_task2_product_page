<template>
    <div>
        <div id="mainH">
            <v-layout row justify-center>
                <v-flex xs1>
                    <a id="logo">sears</a>
                </v-flex>
                <v-flex xs5>
                    <v-layout column>

                        <v-layout row pt-3>
                            <a>sdf</a>
                            <a>sdfsdf</a>
                        </v-layout>

                        <div class="password-wrapper">
                            <input id="password-field" type="password" class="input" name="password">
                            <div class="icon-wrapper">
                                <span class="ion ion-search field-icon toggle-password"></span>
                            </div>
                        </div>

                    </v-layout>
                </v-flex>
                <v-flex xs2>
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

    .bg-transparent {
        background-color: transparent !important;
    }

    @mixin size($w, $h) {
        width: $w;
        height: $h;
    }

    @mixin font-size($sizeValue: 1.6) {
        font-size: $sizeValue * 10 + px;
        font-size: $sizeValue + rem;
    }

    // styles
    body {
        background-color: $primary;
        .password-wrapper {
            width: 80%;
            border-radius: 5px;
            background-color: white;
            overflow: hidden;
            .input {
                border: none;
                font: small-caption;
                @include font-size(1.4);
                width: calc(100% - 50px);
                color: $secondary;
                outline: none;
                line-height: 1.8;
                padding-left: 15px;
            }
            .icon-wrapper {
                position: relative;
                display: inline;
                float: right;
                @include size(42px, 36px);
                background-color: $light;
                transition: background-color 0.25s ease-out;
                cursor: pointer;
                .ion-search {
                    @include font-size(2.0);
                    position: absolute;
                    top: 4px;
                    right: 10px;
                    color: #cccccc;
                    transition: color 0.25s ease-out;
                }
                &:hover {
                    transition: background-color 0.25s ease-in;
                    background-color: $secondary;

                }
            }
        }
    }
</style>