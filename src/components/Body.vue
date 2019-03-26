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
                    <img src="image_w_1.jpg"
                         alt="" width="439px" height="439px">
                    <v-container fluid grid-list-sm xs4 style="height: 439px;" class="scroll-y">
                        <v-layout row wrap justify-center>
                            <v-flex v-for="i in 6" :key="i">
                                <img  :src="`image_w_${i + 1}.jpg`"
                                       width="204px" height="204px" alt="">
                            </v-flex>
                        </v-layout>
                    </v-container>
                </v-layout>
                <v-divider style="margin-top: 30px" class="mb-3"></v-divider>
                <a id="select">Color: Select</a>
                <v-layout row>
                </v-layout>
            </v-flex>


            <v-flex shrink style="background: red; width: 355px;">
                <a>dsdfsdfdad</a>
            </v-flex>
        </v-layout>
    </div>
</template>

<script>
    export default {}
</script>

<style scoped lang="scss">
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
</style>