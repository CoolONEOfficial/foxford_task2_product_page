<template>
    <div>
        <div id="mainH">
            <v-layout row justify-center>
                <v-flex xs1>
                    <a id="logo">sears</a>
                </v-flex>
                <v-flex xs5>
                    <v-layout column>

                        <v-layout row>
                            <a class="pr-3 py-2" :key="item" style="color: white; font-size: 10pt;"
                               v-for="item of ['Deals', 'Coupons', 'Weekly Ad', 'Gift Ideas \u23F7', 'Credit Card \u23F7', 'Store Locator', 'Kmart.com', 'Help']">
                                {{ item }}
                            </a>
                        </v-layout>

                        <div class="password-wrapper">
                            <input id="password-field" class="input">
                            <div class="icon-wrapper">
                                <span class="ion ion-search field-icon toggle-password"></span>
                            </div>
                        </div>

                    </v-layout>
                </v-flex>
                <v-flex xs2>
                    <v-layout column align-end>
                        <a class="pr-3 py-2" :key="item" style="color: white; font-size: 10pt;">
                            <b>FREE SHIPPING ON</b> $59+
                        </a>
                        <v-layout row>
                            <a style="color: white; font-size: 10pt;">
                                Sign in<br>
                                <b>Account & Points &#9207;</b>
                            </a>
                            <a class="pl-3" style="color: white; font-size: 10pt;">
                                Check Your<br>
                                <b>Order Status</b>
                            </a>
                            <img src="../assets/cart.png" alt="" style="height: 20px;" class="ma-2 ml-3"/>
                        </v-layout>
                    </v-layout>
                </v-flex>
            </v-layout>
        </div>
        <div id="bottomH">
            <v-layout row justify-center>
                <a class="px-4 py-2" :key="item" style="color: white; font-size: 13px;"
                   v-for="item of ['Appliances', 'Tools', 'Mattresses', 'Clothing', 'Shoes', 'Baby', 'Jewelry', 'Fitness', 'Auto', 'Home', 'Electronics', 'Outdoor', 'Parts & Services', 'Toys' ]">
                    {{ item }}
                </a>
                <a class="px-4 pt-2 pb-1 mb-2" :key="item" style="color: white; font-size: 13px; background: #002859;">
                    More
                </a>
            </v-layout>
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
        font-size: 45pt;
        color: white;
    }

    #mainH {
        background: $primary;
        height: 88px;
    }

    #bottomH {
        background: $secondary;
        height: 2.5em;
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
                    color: white;
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