<template>
    <div>
        <v-layout justify-center row>
            <v-flex xs6>
                <v-breadcrumbs class="pt-2 pb-1 pl-2"
                               :items="['Home', 'Appliances', 'Refrigerators', 'French Door Refrigerators'].map(value => ({text: value}))"></v-breadcrumbs>
                <h1 id="title">Kenmore 72597 27.8 cu. ft. Smart 4-Door Refrigerator - Black Stainless Steel</h1>
                <v-layout justify-start row class="py-2">
                    <rating class="pr-2" :stars="rating"></rating>
                    <a class="pr-2 pt-1" id="subtitle" :key="item"
                       v-for="item of ['5 reviews', 'Description', 'Specifications']">{{ item }}</a>
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
                <div class="ml-3">
                    <a id="select">Color: Select</a>
                    <v-layout row>
                        <v-card :style="'padding: 2px; margin: 3px; background: ' + (color === item ? '#002859' : 'white') + ';'"
                                v-for="item in ['white', 'black']" :key="item">
                            <img @click="color = item" class="pa-0 ma-0" :src="`color_${item}.jpg`" alt="" width="36px"
                                 height="36px">
                        </v-card>
                    </v-layout>
                </div>
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
                    <v-icon small color="#003980" class="pr-2">far fa-heart</v-icon>
                    <a class="pt-1 pr-2">add to list</a>
                    <a class="pt-1 pr-3">add to registry &#9207;</a>
                </v-layout>
                <v-divider class="mb-3"></v-divider>
                <expandable height="427px" text-open="read full description" text-close="read less">
                    <v-layout row>
                        <h2 id="description">Description</h2>
                        <span id="item-description" class="pl-4"
                              style="font-size: 14pt">Item # 04672595000 Model # 72595</span>
                    </v-layout>
                    <v-layout row class="my-3">
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
                    <v-layout column align-start justify-start v-for="pair in [
                        [
                            'Resists Fingerprints for Quick & Easy Cleaning',
                            'Bring home the bacon and keep it fresh with the Kenmore 27.8 cu. ft. Smart 4 door refrigerator. Designed to be compatible with your Amazon Alexa™, this Kenmore Smart fridge makes it easy to keep tabs on your fridge status and make lists with Alexa or the Kenmore Smart app. Pairing modern conveniences with smart technology, this french door fridge has both the space and the smarts to keep your household running on time and well-stocked with fresh foods.',
                        ], [
                            'Stay in Touch with Your Fridge\'s Status',
                            'Control your Kenmore Smart refrigerator from anywhere with Alexa™. Through the app or with voice commands, you can Activate Accela Ice™ and Max Air Filter, adjust & monitor the temperature, monitor filter life and door open/close status, plus get alerts with any needs. Built-in diagnostics help prevent unnecessary service by making maintenance easier.',
                        ], [
                            'Plenty of Space',
                            'This Kenmore Smart fridge has 28.7 cu. ft. of interior space, plenty of room to stock up favorite snacks, leftovers and household staples. Adjustable interior storage makes putting the groceries away hassle-free while the dual freezer drawers make it easy to stash and organize frozen foods. Humidity-controlled crispers and a gourmet full-width pantry drawer keep fresh foods and deli favorites close at hand and at ideal temperatures. A Slide Away shelf gives you extra space when you need it for taller items.',
                        ], [
                            'Better Freezer Storage',
                            'The dual freezer drawers make organizing your frozen foods simple. The top drawer is perfect for household staples and smaller items while the bottom drawer has space enough for a large turkey and prepped meals.',
                        ], [
                            'Keeps Cool',
                            'Cool Edge™ direct door cooling keeps a steady supply of cold air circulating throughout your fridge, including bins and pantry drawers, to keep your foods at the ideal temperature. Multi air flow technology works with the CleanFlow Air Filter to circulate fresh air through a charcoal filter, removing food odors and keeping your fridge interior nice and fresh for your fresh foods.',
                        ], [
                            'Ice & Water At Your Fingertips',
                            'Grab fresh clear water right from the in-door dispenser. A deluxe water filter helps remove contaminates and give you fresh-tasting water and ice. Accela Ice gives you the option to speed up ice production, perfect for when you have guests over, while the slim in-door ice maker won\'t hog fridge space.',
                        ], [
                            'Added on October 20, 2017',
                            ''
                        ],
                    ]" :key="pair">
                        <strong>{{ pair[0] }}</strong>
                        <span class="my-3">{{ pair[1] }}</span>
                    </v-layout>
                    <h3 class="my-3">More information</h3>
                    <v-layout justify-space-between row>
                        <div v-for="(item, index) in ['Energy Guide', 'Owners manual - English', 'Return Policy']"
                             :key="index">
                            <img class="mr-2" :src="`description_icon_${index + 1}.png`" alt="" width="32px">
                            <a>{{ item }}</a>
                            <v-spacer></v-spacer>
                        </div>
                    </v-layout>
                </expandable>
                <v-divider class="mb-4 mt-5"></v-divider>
                <expandable height="427px" text-open="full specifications" text-close="less specifications">
                    <h2>Specifications</h2>
                    <v-layout column class="mt-3 ml-3" :key="key" v-for="[key, entry] of
                        Object.entries(
                            {
                                'Dimensions': {
                                    'Standard or Counter Depth': 'Standard Depth',
                                    'Depth w/ Handle': '36.25 (in.)',
                                    'Depth w/o Handle': '33.75 (in.)',
                                    'Height to Top of Case': '68.375 (in.)',
                                    'Height to Top of Hinge': '69.75 (in.)',
                                    'Depth w/ Door Open 90 Degrees': '48.25',
                                    'Width w/ Door Closed': '35.75 (In.)',
                                    'Width': '35 to 35 7/8 inches',
                                    'Depth without Door': '29.875 (in.)',
                                },
                                'Appliance Features': {
                                    'Defrost System': 'Frost-free (Automatic)',
                                    'Thru Door Dispenser': 'Ice & Water Dispenser',
                                    'Humidity-Controlled Crisper': 'Yes',
                                    'Ice Style': 'Crushed & Cubed',
                                    'Freezer Orientation': 'Drawer',
                                    'Features': 'Ice Dispenser',
                                },
                                'Product Overview': {
                                    'Built In': 'No',
                                    'Connected Products': 'Yes',
                                    'Works With': 'Amazon Alexa, Kenmore Smart App',
                                },
                                'Power & Performance': {
                                    'Kilowatt Hrs. per Year': '788',
                                    'Voltage': '115 (V)',
                                },
                                'Color': {
                                    'Door Color': 'Stainless',
                                    'Color Family': 'Stainless steel',
                                },
                                'Capacity': {
                                    'Freezer Capacity': '9.2 (Cu Ft)',
                                    'Overall Capacity': '27.8 (Cu Ft)',
                                    'Refrigerator Capacity': '18.6',
                                },
                                'Weight': {
                                    'Weight': '322 (lbs.)',
                                    'Weight, Shipping': '347',
                                },
                                'Storage': {
                                    'Gallon Door Storage': 'Yes',
                                    'Number of Freezer Door Bins': '2',
                                    'Number of Freezer Shelves/Baskets': '2',
                                    'Number of Refrigerator Drawers': '3',
                                    'Number of Refrigerator Door Bins': '7',
                                    'Adjustable Shelves': 'Yes',
                                    'Number of Refrigerator Shelves': '4',
                                },
                                'Controls': {
                                    'Control Location': 'Exterior',
                                },
                                'Warranty': {
                                    'General Warranty': '13 month limited',
                                },
                                'Materials': {
                                    'Refrigerator Shelf Material': 'Glass',
                                },
                                'Certifications & Ratings': {
                                    'ENERGY STAR Certified': 'No',
                                    'ADA Compliant': 'No',
                                },
                                'Filtration': {
                                    'Ice/Water Filter': 'Yes',
                                    'Water Filter': 'Yes',
                                    'Water Filter Replacement Part Number': '04609980000',
                                    'Air Filter Replacement Part Number': '04609918000',
                                },
                                'Lighting': {
                                    'Freezer Interior Light': 'Yes',
                                    'Refrigerator Interior Light': 'Yes',
                                },
                                'Product Includes': {
                                    'Power Cord Included': 'Yes',
                                    'Ice Maker': 'Yes',
                                    'Internal Water Dispenser': 'No',
                                    'Ice Dispenser': 'Yes',
                                },
                                'Adjustability': {
                                    'Adjustable Legs': 'Yes',
                                },
                            }
                        )">
                        <strong>{{ key }}:</strong>
                        <div :key="index" v-for="(entryPair, index) of
                            Object.entries(entry)">
                            <v-layout class="pl-3 py-1"
                                      :style="`background: ${index % 2 === 0 ? '#eee' : 'transparent'};`"
                                      row>
                                <v-flex xs6>
                                    {{ entryPair[0] }}:
                                </v-flex>
                                <v-flex xs6>
                                    {{ entryPair[1] }}
                                </v-flex>
                            </v-layout>
                        </div>
                    </v-layout>
                </expandable>
                <v-divider class="mb-4 mt-5"></v-divider>
                <h2>Ratings & Reviews</h2><br>
                <v-layout row>
                    <rating class="pr-2" :stars="rating"></rating>
                    <div style="font-size: 11pt" class="pt-1">
                        <strong>{{ rating }}.0 of 5 stars | </strong>
                        <a>write your review</a>
                    </div>
                </v-layout>
            </v-flex>

            <v-flex shrink id="right-form" class="pt-5 mx-3">
                <div>
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
                </div>
            </v-flex>
        </v-layout>
    </div>
</template>

<script>
    import Expandable from "./Expandable";
    import Rating from "./Rating";

    export default {
        components: {Rating, Expandable},
        data() {
            return {
                'color': 'black',
                'descriptionExpanded': false,
                'rating': 5,
            }
        },
        watch: {
            color: function (val) {
                this.rating = (val === 'white' ? 5 : 3);
            },
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

    #right-form {
        width: 355px;
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

    h2 {
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