<template>
  <div>
    <v-container>
      <div class="row">
        <div class="col-md-5 col-sm-5 col-xs-12">
          <v-carousel hide-delimiter-background show-arrows-on-hover cycle>
            <v-carousel-item
              v-for="(image, index) in productData.images"
              :key="index"
              :src="`${$axios.defaults.baseURL}/thumbnails/${image}`"
            />
          </v-carousel>
        </div>
        <div class="col-md-7 col-sm-7 col-xs-12">
          <v-breadcrumbs class="pb-0" :items="breadcrums" />
          <div class="pl-6">
            <p class="display-1 mb-0">
              {{ productData.name }}
            </p>
            <v-card-actions class="pa-0">
              <p class="headline font-weight-light pt-3">
                &#8377;{{ productData.minprice }}
                <span
                  style=""
                  class="subtitle-1 font-weight-thin"
                >Minimum Price</span>
              </p>
              <v-spacer />
              <v-rating
                v-model="rating"
                class=""
                background-color="warning lighten-3"
                color="warning"
                dense
              />
              <span class="body-2 font-weight-thin"> 25 REVIEWS</span>
            </v-card-actions>
            <p class="subtitle-1 font-weight-thin">
              {{ productData.description }}
            </p>
            <v-btn class="primary white--text" outlined tile dense>
              <v-icon>mdi-cart</v-icon> Buy
            </v-btn>
            <v-btn class="ml-4" outlined tile>
              ADD TO COMPARE
            </v-btn>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-sm-12 col-xs-12 col-md-12">
          <v-tabs>
            <v-tab>Description</v-tab>
            <v-tab>Materials</v-tab>
            <v-tab>REVIEWS</v-tab>
            <v-tab-item>
              <p class="pt-10 subtitle-1 font-weight-thin">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ultricies mi eget mauris pharetra et. Vel pretium lectus quam id
                leo in vitae turpis massa. Orci dapibus ultrices in iaculis
                nunc. At auctor urna nunc id cursus metus. Integer feugiat
                scelerisque varius morbi enim nunc. Aliquam sem et tortor
                consequat id porta nibh venenatis cras. Pellentesque pulvinar
                pellentesque habitant morbi tristique senectus et netus.
                Malesuada nunc vel risus commodo viverra maecenas. Neque
                volutpat ac tincidunt vitae semper quis.
              </p>
            </v-tab-item>
            <v-tab-item>
              <p class="pt-10 subtitle-1 font-weight-thin">
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
                eiusmod tempor incididunt ut labore et dolore magna aliqua.
                Ultricies mi eget mauris pharetra et. Vel pretium lectus quam id
                leo in vitae turpis massa. Orci dapibus ultrices in iaculis
                nunc. At auctor urna nunc id cursus metus. Integer feugiat
                scelerisque varius morbi enim nunc. Aliquam sem et tortor
                consequat id porta nibh venenatis cras. Pellentesque pulvinar
                pellentesque habitant morbi tristique senectus et netus.
                Malesuada nunc vel risus commodo viverra maecenas. Neque
                volutpat ac tincidunt vitae semper quis.
              </p>
            </v-tab-item>
            <v-tab-item>
              <v-list three-line="true" avatar="true">
                <v-list-item-group v-model="item" color="primary">
                  <v-list-item
                    v-for="(item, i) in items"
                    :key="i"
                    inactive="true"
                  >
                    <v-list-item-avatar>
                      <v-img :src="item.avatar" />
                    </v-list-item-avatar>
                    <v-list-item-content>
                      <v-list-item-title v-html="item.title" /><v-rating
                        v-model="rating"
                        class=""
                        background-color="warning lighten-3"
                        color="warning"
                        dense
                      />
                      <v-list-item-subtitle v-html="item.subtitle" />
                    </v-list-item-content>
                  </v-list-item>
                </v-list-item-group>
              </v-list>
            </v-tab-item>
          </v-tabs>
          <v-card-text class="pa-0 pt-4" tile outlined>
            <p class="subtitle-1 font-weight-light pt-3 text-center">
              YOU MIGHT ALSO LIKE
            </p>
            <v-divider />
            <div class="row text-center">
              <div class="col-md-2 col-sm-4 col-xs-12 text-center">
                <v-hover v-slot="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2">
                    <v-img
                      class="white--text align-end"
                      height="200px"
                      src="/img/image_ph.jpg"
                    >
                      <v-card-title>Bags & Purses </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary text-center">
                      <div>Upto 60% + Extra 10%</div>
                      <div>Baggit, Zara, Fossil</div>
                    </v-card-text>

                    <div class="text-center">
                      <v-btn class="ma-2" outlined color="info">
                        Explore
                      </v-btn>
                    </div>
                  </v-card>
                </v-hover>
              </div>
              <div class="col-md-2 col-sm-4 col-xs-12 text-center">
                <v-hover v-slot="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2">
                    <v-img
                      class="white--text align-end"
                      height="200px"
                      src="/img/image_ph.jpg"
                    >
                      <v-card-title>T-Shirt </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary text-center">
                      <div>Upto 50%</div>
                      <div>Zara, Selected, Celio</div>
                    </v-card-text>

                    <div class="text-center">
                      <v-btn class="ma-2" outlined color="info">
                        Explore
                      </v-btn>
                    </div>
                  </v-card>
                </v-hover>
              </div>
              <div class="col-md-2 col-sm-4 col-xs-12 text-center">
                <v-hover v-slot="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2">
                    <v-img
                      class="white--text align-end"
                      height="200px"
                      src="/img/image_ph.jpg"
                    >
                      <v-card-title>Jeans </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary text-center">
                      <div>Upto 60% + Extra 10%</div>
                      <div>Jack & Jones, Levis</div>
                    </v-card-text>

                    <div class="text-center">
                      <v-btn class="ma-2" outlined color="info">
                        Explore
                      </v-btn>
                    </div>
                  </v-card>
                </v-hover>
              </div>
              <div class="col-md-2 col-sm-4 col-xs-12 text-center">
                <v-hover v-slot="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2">
                    <v-img
                      class="white--text align-end"
                      height="200px"
                      src="/img/image_ph.jpg"
                    >
                      <v-card-title>Shirts </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary text-center">
                      <div>Upto 60% + Extra 10%</div>
                      <div>Nike, Adidas, Puma</div>
                    </v-card-text>

                    <div class="text-center">
                      <v-btn class="ma-2" outlined color="info">
                        Explore
                      </v-btn>
                    </div>
                  </v-card>
                </v-hover>
              </div>
              <div class="col-md-2 col-sm-4 col-xs-12 text-center">
                <v-hover v-slot="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2">
                    <v-img
                      class="white--text align-end"
                      height="200px"
                      src="/img/image_ph.jpg"
                    >
                      <v-card-title>Shoes </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary text-center">
                      <div>Upto 60% + Extra 10%</div>
                      <div>Nike, Adidas, Puma</div>
                    </v-card-text>

                    <div class="text-center">
                      <v-btn class="ma-2" outlined color="info">
                        Explore
                      </v-btn>
                    </div>
                  </v-card>
                </v-hover>
              </div>
              <div class="col-md-2 col-sm-4 col-xs-12 text-center">
                <v-hover v-slot="{ hover }" open-delay="200">
                  <v-card :elevation="hover ? 16 : 2">
                    <v-img
                      class="white--text align-end"
                      height="200px"
                      src="/img/image_ph.jpg"
                    >
                      <v-card-title>Jackets </v-card-title>
                    </v-img>

                    <v-card-text class="text--primary text-center">
                      <div>Upto 60% + Extra 10%</div>
                      <div>Nike, Adidas, Puma</div>
                    </v-card-text>

                    <div class="text-center">
                      <v-btn class="ma-2" outlined color="info">
                        Explore
                      </v-btn>
                    </div>
                  </v-card>
                </v-hover>
              </div>
            </div>
          </v-card-text>
        </div>
      </div>
    </v-container>
    <v-card class="accent">
      <v-container>
        <v-row no-gutters>
          <v-col class="col-12 col-md-4 col-sm-12">
            <v-row>
              <v-col class="col-12 col-sm-3 pr-4 hidden-sm-only" align="right">
                <v-icon class="display-2">
                  mdi-truck
                </v-icon>
              </v-col>
              <v-col class="col-12 col-sm-9 pr-4">
                <h3 class="font-weight-light">
                  FREE SHIPPING & RETURN
                </h3>
                <p class="font-weight-thin">
                  Free Shipping over $300
                </p>
              </v-col>
            </v-row>
          </v-col>
          <v-col class="col-12 col-md-4 col-sm-12">
            <v-row>
              <v-col class="col-12 col-sm-3 pr-4" align="right">
                <v-icon class="display-2">
                  mdi-cash-usd
                </v-icon>
              </v-col>
              <v-col class="col-12 col-sm-9 pr-4">
                <h3 class="font-weight-light">
                  MONEY BACK GUARANTEE
                </h3>
                <p class="font-weight-thin">
                  30 Days Money Back Guarantee
                </p>
              </v-col>
            </v-row>
          </v-col>
          <v-col class="col-12 col-md-4 col-sm-12">
            <v-row>
              <v-col class="col-12 col-sm-3 pr-4" align="right">
                <v-icon class="display-2">
                  mdi-headset
                </v-icon>
              </v-col>
              <v-col class="col-12 col-sm-9 pr-4">
                <h3 class="font-weight-light">
                  020-800-456-747
                </h3>
                <p class="font-weight-thin">
                  24/7 Available Support
                </p>
              </v-col>
            </v-row>
          </v-col>
        </v-row>
      </v-container>
    </v-card>
  </div>
</template>
<script>
export default {
  props: {
    id: String
  },
  data: () => ({
    productData: Object,
    images: Array,
    rating: 4.5,
    breadcrums: [
      {
        text: 'Home',
        disabled: false,
        href: 'breadcrumbs_home'
      },
      {
        text: 'Clothing',
        disabled: false,
        href: 'breadcrumbs_clothing'
      },
      {
        text: 'T-Shirts',
        disabled: true,
        href: 'breadcrumbs_shirts'
      }
    ],
    item: 5,
    items: [
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
        title: 'Lorem ipsum dolor?',
        subtitle:
          "<span class='text--primary'>Ali Connors</span> &mdash; Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Nisl tincidunt eget nullam non. Tincidunt arcu non sodales neque sodales ut etiam. Lectus arcu bibendum at varius vel pharetra. Morbi tristique senectus et netus et malesuada.\n" +
          '\n'
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
        title:
          'Lorem ipsum dolor <span class="grey--text text--lighten-1">4</span>',
        subtitle:
          "<span class='text--primary'>to Alex, Scott, Jennifer</span> &mdash; Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore"
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
        title: 'Lorem ipsum dolor',
        subtitle:
          "<span class='text--primary'>Sandra Adams</span> &mdash; Lorem ipsum dolor sit amet, consectetur adipiscing elit"
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
        title: 'Lorem ipsum dolor',
        subtitle: ''
      },
      {
        avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
        title: 'Lorem ipsum dolor',
        subtitle:
          "<span class='text--primary'>Britta Holt</span> &mdash; Lorem ipsum dolor sit amet, consectetur adipiscing elit"
      }
    ]
  }),
  mounted () {
    this.$axios
      .get(`/product?slug=${this.$route.params.slug}`)
      .then((res) => {
        this.productData = res.data
      })
      .catch((error) => {
        console.log('Product Module. Error', error)
      })
  }
}
</script>
