<template>
  <ion-page>
    <!-- <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Cake</ion-title>
      </ion-toolbar>
    </ion-header> -->

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Cake</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <section class="searchBar">
          <div class="searchLine">
            <ion-searchbar placeholder="Custom Placeholder"></ion-searchbar>
          </div>
        </section>
        <!-- <section class="searchBar">
          <div class="searchLine">
            <ion-searchbar class="searchComp" placeholder="Custom Placeholder"></ion-searchbar>
          </div>
        </section> -->
        <section class="own_cake_section">
            <router-link class="own_cake" to="/constructor">
                <img
                    class="own_cake_img"
                    src="https://media.tenor.com/KnXJFeAVAHoAAAAi/cake-delivery-canada-cake-delivery-toronto.gif"
                    height="100"
                    width="100"
                />
                <div class="own_cake_title">
                    <h4 class="own_cake_header">Make your own cake!</h4>
                    <p class="own_cake_text">
                        No one can do it better than you
                    </p>
                </div>
            </router-link>
        </section>
        <section class="fast_delivery">
            <div class="fast_delivery_header">
                <img src="../assets/rocket.svg" height="30" width="30" />
                <h4 class="fast_delivery_title">Fast Delivery</h4>
                <a class="fast_delivery_all">See all</a>
            </div>
            <carousel :paginationEnabled="false">
                <slide v-for="i in 5" :key="i">
                    <div class="cake">
                        <div class="cake_img">
                            <img
                                src="../assets/cake1.png"
                                width="100"
                                height="100"
                                alt="cake"
                            />
                        </div>
                        <div class="cake_info">
                            <div class="cake_title">Pink Flowers</div>
                            <div class="cake_desc">Vanilla</div>
                            <div class="cake_price">8500₸</div>
                        </div>
                    </div>
                </slide>
            </carousel>
        </section>

      </div>
    </ion-content>
  </ion-page>
</template>

<script>
import {
  IonContent,
  IonHeader,
  IonPage,
  IonTitle,
  IonToolbar,
  IonSearchbar
} from "@ionic/vue";

import { logoIonic } from 'ionicons/icons';

export default {
  name: 'HomePage',
  components: { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonSearchbar },
  data() {
    return {
      eye: logoIonic,
      lockClosed: null
    }
  }
}
</script>


<style scoped>

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;

  color: #8c8c8c;

  margin: 0;
}

#container a {
  text-decoration: none;
}

.searchBar {
    margin-top: 30px;
    background-color: #ffb6c1;
    height: 70px;
}
.searchBar .searchLine {
    margin: 0 5px;
}

.searchBar .searchLine .search_input .form-control {
    height: 25px;
    border: 0px solid #ced4da;
    width: 137%;
}
.searchComp {
  padding-top: 15px;
}
.own_cake {
    margin: 20px 10px;
    background-color: #ffb6c1;
    border-radius: 3px;
    text-align: left;
    display: flex;
}

.own_cake .own_cake_img {
    padding: 20px;
}

.own_cake .own_cake_title .own_cake_header {
    margin-top: 25px;
    margin-bottom: 0;
}
.own_cake .own_cake_title .own_cake_text {
    color: #ff1493;
    font-size: 14px;
}
.fast_delivery_header {
    margin-left: 10px;
    display: flex;
}
.fast_delivery_title {
    text-align: left;
}
.fast_delivery_all {
    margin-top: 5px;
    position: absolute;
    right: 0;
    margin-right: 10px;
    cursor: pointer;
}
.cake {
    margin: 0 10px;
    box-shadow: 0 0 9px 3px #cccccc26, 0 0 3px #cccccc4d;
}
.cake_info {
    margin: 0 10px;
    border-radius: 0 0 3px 3px;
}
.cake_img {
    border-radius: 3px 3px 0 0;
    background-color: lightblue;
}
.cake_title {
    text-align: left;
}
.cake_desc {
    text-align: left;
    font-size: 10px;
}
.cake_price {
    text-align: left;
    font-size: 15px;
    color: #ff1493;
}
</style>
