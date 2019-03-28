<template>
    <div>
        <v-layout justify-center row>
            <v-flex xs6>
                <v-breadcrumbs class="pt-2 pb-1 pl-2"
                               :items="['Home', 'Appliances', 'Refrigerators', 'French Door Refrigerators'].map(value => ({text: value}))"></v-breadcrumbs>
                <h1 id="title">Kenmore 72597 27.8 cu. ft. Smart 4-Door Refrigerator - Black Stainless Steel</h1>
                <v-layout row class="py-2">
                    <a class="pr-3" id="subtitle" :key="item"
                       v-for="item of ['★★★★★', '5 reviews', 'Description', 'Specifications']">{{ item }}</a>
                </v-layout>
                <v-divider></v-divider>
                <v-layout row>
                    <img :src="`image_${color.charAt(0)}_1.jpg`"
                         alt="" width="439px" height="439px">
                    <v-container fluid grid-list-sm xs4 style="height: 439px;" class="scroll-y">
                        <v-layout row wrap justify-center>
                            <v-flex v-for="i in 6" :key="i">
                                <img :src="`image_${color.charAt(0)}_${i + 1}.jpg`"
                                     width="204px" height="204px" alt="">
                            </v-flex>
                        </v-layout>
                    </v-container>
                </v-layout>
                <v-divider style="margin-top: 30px;" class="mb-3"></v-divider>
                <a id="select">Color: Select</a>
                <v-layout row>
                    <v-card :style="'padding: 2px; margin: 3px; background: ' + (color === item ? '#002859' : 'white') + ';'"
                            v-for="item in ['white', 'black']" :key="item">
                        <img @click="color = item" class="pa-0 ma-0" :src="`color_${item}.jpg`" alt="" width="36px"
                             height="36px">
                    </v-card>
                </v-layout>
                <v-divider style="margin-top: 30px;"></v-divider>
                <v-layout row>
                    <img v-for="icon in Array(3).keys()" :key="icon" :src="`share_icon_${icon + 1}.png`" alt=""
                         class="ma-2" width="16px" height="16px">

                    <img src="icon_like.png" alt=""
                         class="ma-2 ml-4" width="14px" height="14px">
                    <a style="color: grey;" class="pt-1">Like It</a>

                    <img src="icon_want.png" alt=""
                         class="ma-2 ml-4" width="14px" height="14px">
                    <a style="color: grey;" class="pt-1">Share It</a>

                    <img src="icon_have.png" alt=""
                         class="ma-2 ml-4" width="14px" height="14px">
                    <a style="color: grey;" class="pt-1">Have It</a>
                    <v-spacer></v-spacer>
                    <v-icon color="#003980" class="pr-2">far fa-heart</v-icon>
                    <a class="pt-1 pr-2">add to list</a>
                    <a class="pt-1 pr-3">add to registry &#9207;</a>
                </v-layout>
                <v-divider class="mb-3"></v-divider>
                <v-layout row>
                    <h2 id="description">Description</h2>
                    <span id="item-description" class="pl-4"
                          style="font-size: 14pt">Item # 04672595000 Model # 72595</span>
                </v-layout>
                <v-layout row class="pt-2">
                    <v-layout column>
                        <span style="font-size: 12pt;">
                        &bull; 27.8 cu. ft. Capacity<br>
                        &bull; CleanFlow Air Filter
                        </span>
                    </v-layout>
                    <v-layout column>
                        <span style="font-size: 12pt;">
                        &bull; Kenmore Smart<br>
                        &bull; In-Door Ice & Water Dispenser
                        </span>
                    </v-layout>
                </v-layout>
            </v-flex>

            <v-flex shrink style="width: 355px;" class="pt-5 mx-3">
                <v-card class="mb-3">
                    <v-layout column class="justify-center text-xs-center" style="font-size: 10pt;">
                        <v-flex style="background-color: #f5f5f5" class="py-1" xs12>
                            Sold by <strong>Sears</strong>
                        </v-flex>
                        <v-divider></v-divider>
                        <v-layout row class="justify-center pt-3">
                            <v-flex xs4>
                                <v-layout column class="text-xs-left">
                                    <a>Regular price</a><br>
                                    <strong>Your savings</strong>
                                    <v-divider class="mt-1"></v-divider>
                                </v-layout>
                            </v-flex>
                            <v-flex xs4>
                                <v-layout column class="text-xs-right">
                                    <s>$4959.99</s><br>
                                    <strong>- $3061.00</strong>
                                    <v-divider class="mt-1"></v-divider>
                                </v-layout>
                            </v-flex>
                        </v-layout>
                        <strong id="price">$1898.99</strong>
                        <span class="pb-2">No credit required. Lease <strong
                                class="text-red">$85.45/week</strong></span>
                        <v-divider class="mx-3"></v-divider>
                        <a class="my-2 text-red"><i>Spend $60+, get $60 CASHBACK in points 6 instlmnts</i></a>
                        <v-divider></v-divider>
                        <span class="my-2">Get <strong>$78.99 CASHBACK</strong> in points</span>
                        <v-divider class="mx-3"></v-divider>
                        <span class="my-2">Layaway Eligible</span>
                        <v-flex style="background-color: #f5f5f5" class="py-2 text-xs-left" xs12>
                            <v-layout row>
                                <v-radio class="ma-2 pl-1" value="true"></v-radio>
                                <span><strong class="text-red">FREE</strong><strong> Delivery</strong><br>Enter location for availability</span>
                            </v-layout>
                        </v-flex>
                        <v-divider class="mr-3 ml-5"></v-divider>
                        <v-flex style="background-color: #f5f5f5" class="py-2 text-xs-left" xs12>
                            <v-layout row>
                                <v-radio class="ma-2 pl-1" value="true"></v-radio>
                                <span><strong class="text-red">FREE</strong><strong> Store Pickup</strong><br>Enter location for availability</span>
                            </v-layout>
                        </v-flex>
                        <v-divider></v-divider>
                        <v-layout row justify-center>
                            <v-card class="my-3 ml-3"><span class="px-3" style="font-size: 18pt;">-</span></v-card>
                            <v-card class="my-3 pt-1"><span class="px-4" style="font-size: 14pt;">1</span></v-card>
                            <v-card class="my-3 mr-3"><span class="px-3" style="font-size: 18pt;">+</span></v-card>
                            <v-card class="my-3 mr-3 pt-1" color="red">
                                <span class="px-3"
                                      style="color: white; font-size: 14pt;">Add to Cart</span>
                            </v-card>
                        </v-layout>
                    </v-layout>
                </v-card>
                <div class="pl-3">
                    <a>Learn about our regular price offer</a><br>
                    <span>Questions? Call (888) 349-4067</span><br>
                    <a>Meet with an expert in our store</a><br>
                    <a>View Alaska/Hawaii Pricing</a>
                </div>
            </v-flex>
        </v-layout>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                'color': 'black'
            }
        }
    }
</script>

<style scoped lang="scss">
    @import "../styles/vars";

    @font-face {
        font-family: 'Open Sans Light';
        font-style: normal;
        font-weight: 300;
        src: url(https://fonts.gstatic.com/s/opensans/v13/DXI1ORHCpsQm3Vp6mXoaTRa1RVmPjeKy21_GQJaLlJI.woff) format('woff');
    }

    #title {
        font-family: "Open Sans Light", sans-serif;
        font-weight: 300;
        line-height: 1.25;
        font-size: 1.7rem;
    }

    #subtitle {
        font-family: "Open Sans Light", sans-serif;
        font-weight: 600;
        font-size: 11pt;
    }

    #select {
        font-family: "Open Sans Light", sans-serif;
        font-weight: 600;
        color: #001733;
    }

    #price {
        font-family: "Open Sans", sans-serif;
        font-weight: 600;
        color: $red;
        font-size: 26pt;
    }

    #description {
        font-family: "Open Sans", sans-serif;
        font-weight: 600;
    }

    #item-description {
        font-family: "Open Sans Light", sans-serif;
        font-weight: 600;
        font-size: 11pt;
    }

    .text-red {
        color: $red;
    }
</style>