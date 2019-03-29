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
                    <v-layout column align-start justify-start v-for="pair in description" :key="pair">
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
                    Object.entries(specs)">
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
                <v-layout row class="mb-3">
                    <rating class="pr-2" :stars="rating"></rating>
                    <div style="font-size: 11pt" class="pt-1">
                        <strong>{{ rating }}.0 of 5 stars | </strong>
                        <a>write your review</a>
                    </div>
                </v-layout>
                <div class="pl-3">
                    <i style="font-size: 12pt; color: grey;">25% of customers would recommend this product</i><br>
                    <div style="font-size: 12pt;" class="my-3">
                        <strong>Rating Breakdown </strong>
                        <small style="color: grey;">(8 Reviews)</small>
                    </div>
                    <v-layout v-for="(rating, index) in [1, 1, 3, 2, 1]" :key="index" row>
                        <strong class="mr-1">{{ 5 - index}}</strong>stars
                        <div :style="`height: 5px; width: ${46 * rating}px; background: #003980;`"
                             class="ml-3 mt-2"></div>
                        <div :style="`height: 5px; width: ${46 * (5 - rating)}px; background: #f2f2f2;`"
                             class="mt-2"></div>
                        <a class="ml-3">{{ rating }} reviews</a>
                    </v-layout>
                </div>
                <v-divider class="mb-4 mt-3"></v-divider>
                <div class="ml-4 mb-2 mt-5">
                    <h3>Most Helpful Reviews</h3>
                    <v-layout row class="ml-3 mt-2 mb-5">
                        <v-flex xs6 class="my-3">
                            <h3>Praise</h3>
                            <review short=true v-bind="reviews
                            .filter((review) => review.positive)
                            .sort((a, b) => a.helpful - b.helpful)[0]"></review>
                        </v-flex>
                        <v-divider class="mx-4" vertical></v-divider>
                        <v-flex xs6 class="my-3">
                            <h3>Criticism</h3>
                            <review short=true v-bind="reviews
                            .filter((review) => !review.positive)
                            .sort((a, b) => a.helpful - b.helpful)[0]"></review>
                        </v-flex>
                    </v-layout>
                </div>
                <v-divider></v-divider>
                <v-layout row class="px-3" align-center style="background: #EEE;">
                    <h3 class="pr-3">Sort by:</h3>
                    <v-select :items="[
                        'Top Rated',
                        'Newest',
                        'Oldest',
                        'Most Helpful',
                        'Low Rated',
                        'Verified Purchase',
                    ]">
                    </v-select>
                </v-layout>
                <div v-for="review in reviews" :key="review">
                    <v-divider class="mb-3"></v-divider>
                    <review class="mb-3 mx-3" v-bind="review"></review>
                </div>
                <v-divider></v-divider>
                <v-layout row class="px-3" align-center style="background: #EEE;">
                    <h3 class="pr-3">Sort by:</h3>
                    <v-select :items="[
                        'Top Rated',
                        'Newest',
                        'Oldest',
                        'Most Helpful',
                        'Low Rated',
                        'Verified Purchase',
                    ]">
                    </v-select>
                </v-layout>
                <v-divider></v-divider>
                <v-layout row class="my-4">
                    <img style="margin-left: 250px;" src="image_kenmore.jpg" alt="">
                    <v-layout class="ml-5" column>
                        <a v-for="item in [
                            'Kenmore French Door Refrigerators',
                            'Kenmore French Door Refrigerators',
                            'All Kenmore',
                        ]" :key="item">{{ item }}</a>
                    </v-layout>
                </v-layout>
                <v-divider></v-divider>
                <h2 class="mt-4 mb-3">Regular Price Offer</h2>
                <span>Choose the price you want to pay:</span>
                <v-layout class="my-3" align-start row v-for="item in [
                    [
                        '$1799.99',
                        'Save $2160.00 today',
                        'Pay this price & save on today\'s order',
                    ],
                    [
                        '$3959.99',
                        '& receive a gift card',
                        'Pay this price & receive a Sears gift card for 10% more than you will save with the price above. Not valid with discounts or coupons.',
                    ],
                ]" :key="item">
                    <v-radio class="mr-2 mt-1"></v-radio>
                    <div>
                        <span class="mr-3" style="font-size: 16pt;">{{ item[0] }}</span>
                        <strong>{{ item[1] }}</strong><br>
                        <span style="font-size: 12pt;">{{ item[2] }}</span>
                    </div>
                </v-layout>
                <div style="padding-left: 40px;">
                    <strong>How it works:</strong><br>
                    <span class="mr-1">Select this option & place your order. After your order is placed, email your salescheck #, first & last name, & telephone number to:</span>
                    <a>saveonall@customerservice.sears.com</a><br>
                    <span class="mb-3">Please allow up to 30 days for processing.</span>
                </div>
                <v-divider class="my-4"></v-divider>
            </v-flex>

            <v-flex shrink id="right-form" class="pt-5 mx-3">
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
    import Expandable from "./Expandable";
    import Rating from "./Rating";
    import Review from "./Review";

    export default {
        components: {Review, Rating, Expandable},
        data() {
            return {
                'color': 'black',
                'descriptionExpanded': false,
                'rating': 5,
                'reviews': [
                    {
                        "stars": 3,
                        "title": "Do Not Buy This Product",
                        "text": "My refrigerator is only six months old and the computer board has gone out. The part is unavailable and Sears cannot tell me when they will have it. I purchased the extended warranty from Sears and they have refused to replace my unit. Therefore, it will be after the new year before this is resolved. Six weeks without the unit is unacceptable! I would not buy this product from Sears.",
                        "helpful": 58,
                        "nickname": "wilshell01",
                        "location": "Rowlett, TX",
                        "date": "Thu, Dec 20, 2018",
                        "positive": false,
                    },
                    {
                        "stars": 3,
                        "title": "ok fridge",
                        "text": "The fingerprint resistant part I love. However, this fridge isn't as roomy as the one I exchanged it for. I guess it's because the freezer is at the bottom. Tall bottles have to go on the door or be laid down, can't stand upright because the spacing of the shelves is small. Had the one I had before been fingerprint resistant like this one, I wouldn't have exchanged it...but still not happy with the purchase.",
                        "helpful": 21,
                        "nickname": "Deone",
                        "location": "Santa Rosa, CA",
                        "date": "Sat, Jun 30, 2018",
                        "positive": false,
                    },
                    {
                        "stars": 2,
                        "title": "Great look, but very poor quality",
                        "text": "Bought this fridge during Memorial Day sale, and got it for a good price. Could not get it delivered until June 20th. This fridge looks great in out kitchen, but we are having some fan or motor issues already. The doors on this fridge close very hard, and we have started to hear a grinding noise which gets very loud until you move the fridge. I called for service and I will be waiting 3 weeks to get a tech out to check on the problem. I also called to have this unit replaced, since I don't think I should have to call for service on such a new unit. The replacement is going to take 6 weeks. Very disappointed. I hope the replacement works better than this. We replaced a 13 year old Kenmore side by side which was still working. That one was made by Whirlpool, this unit is made by LG. Due to the low price, I am sure many of these units were sold during the last two summer holiday sales. Need to see more reviews from other owners.",
                        "helpful": 23,
                        "nickname": "AM_NY",
                        "location": "Congers, NY",
                        "date": "Sun, Jul 8, 2018",
                        "positive": false,
                    },
                    {
                        "stars": 5,
                        "title": "Great refrigerator!!!",
                        "text": "Giving this fridge anything other that 5 stars is nonsense. It is huge! We are a family of 4 and still have 1 shelf that's not being used because its so big. The 2 compartment freezer helps organize items and has much more space than I thought. it's quiet, makes ice quickly. The smart fridge features are great if your into that king of thing. Overall A++",
                        "helpful": 44,
                        "nickname": "Oscar8325",
                        "location": "King City, CA",
                        "date": "Fri, Jul 20, 2018 ",
                        "positive": true,
                    },
                    {
                        "stars": 4,
                        "title": "I like this fridge. Does not dissappoint.",
                        "text": "Most people write in because they don't like something. Not true here. I bought this fridge on Memorial Day. Looks beautiful in my kitchen. Replaced a 30 year old still working whirlpool. Don't make em like that today. LOL. I knew I was on my last leg so I replaced it with this fridge. No problems so far. has an app too. It is roomy ...so much space inside. I did't expect that but am pleasantly surprised. I can put a full sheet birthday cake inside no problem. It does have a little draw back in that tall drinks must go on door. Not a big deal though. Door wide enough to hold 1 gal milk, 1 bottle wine and 2 half gals of apple juice. We don't do soda at my house but it would hold a 2 liter as well. I put my water bottles , tea bottles and Gatorade on second shelf left. Sliding shelf allows you to add more tall bottles as well. Love love the 2 freezer drawers. I feel more organized. Veggies etc in the top. Meat in bottom. easy peasy. Finger print proof. Yippee. Get this one. Best price 27 cubic feet of space. Mine works great to date. BTW Sears has the best repair service if you need it. I have used them many times in the past. I also bought dishwasher so all appliances would match. LOL.",
                        "helpful": 39,
                        "nickname": "kidneykim",
                        "location": "Salt Lake City, UT",
                        "date": "Tue, Jul 24, 2018",
                        "positive": true,
                    },
                    {
                        "stars": 3,
                        "title": "Broken after 9 months and Sears doesn’t care",
                        "text": "",
                        "helpful": 54,
                        "nickname": "Monica64",
                        "location": "",
                        "date": "Sat, Aug 18, 2018 via mobile",
                        "positive": false,
                    },
                    {
                        "stars": 1,
                        "title": "Worst Purchase Ever - 2nd delivery -7 days at home waiting on technicians",
                        "text": "Honestly the worst purchase I have ever made in 50 years. After 30 years of Kenmore appliances, the first one sounded like a motorcycle. 2nd delivery has never made ice, gives constant errors. Bought June 24, went the entire summer without ice, 7 tech visits so far, can't fix it, won't replace. I will keep you updated. Now Sept 6, and over 8 hours on the phone waiting for Sears customer service to either say, \"there is nothing I can do\" or worse \"accidentally\" disconnect me after 2 hours of waiting. After seven visits with no repair, they keep asking if I want to buy an extended warranty. DO NOT BUY APPLIANCES FROM SEARS.",
                        "helpful": 55,
                        "nickname": "jtklaus",
                        "location": "Mulvane, KS",
                        "date": "Thu, Sep 6, 2018",
                        "positive": false,
                    },
                    {
                        "stars": 3,
                        "title": "Shop smart",
                        "text": "Positives: roomy and I like the smart app. Negatives: needs more light near the pullout bins at bottom of cooler and bottom of freezer. The door on the right does not pull closed so you better make sure it closes completely. Filter replaces are very expensive.",
                        "helpful": 45,
                        "nickname": "B6210",
                        "location": "Lumberton, NC",
                        "date": "Sat, Nov 17, 2018",
                        "positive": false,
                    },
                ],
                'description': [
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
                ],
                'specs': {
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
                },
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

    .v-text-field--box .v-input__slot,
    .v-text-field--outline .v-input__slot {
        min-height: auto !important;
        display: flex !important;
        align-items: center !important;
    }
</style>