<template>
    <ion-page class="constructor">
        <h1>Customize</h1>
        <div class="demo">
            <ion-button @click="loadImage">Load image</ion-button>
            <img
                src="../assets/body.png"
                class="m-4 cakeImg"
                height="250"
                width="250"
                alt=""
            />
            <img
                src="../assets/eyes.png"
                class="m-4 cakeImg"
                height="250"
                width="250"
                alt=""
            />
            <img
                src="../assets/mouth.png"
                class="m-4 cakeImg"
                height="250"
                width="250"
                alt=""
            />
            <img id="test" src="" class="m-4" height="250" width="250" alt="" />
        </div>
        <ion-grid>
            <ion-row class="settings">
                <ion-col class="settings_menu" size="3">
                    <div
                        class="settings_menu_item"
                        :class="{ active: tab === 0 }"
                        @click="chgTab(0)"
                    >
                        <img
                            height="45"
                            width="45"
                            src="../assets/Shape.png"
                            alt="Shape"
                        />
                        <ion-label class="settings_menu_item_title">Shape</ion-label>
                    </div>
                    <div
                        class="settings_menu_item"
                        :class="{ active: tab === 1 }"
                        @click="chgTab(1)"
                    >
                        <img
                            height="45"
                            width="45"
                            src="../assets/flavor.png"
                            alt="Flavor"
                        />
                        <ion-label class="settings_menu_item_title">Flavor</ion-label>
                    </div>
                    <div
                        class="settings_menu_item"
                        :class="{ active: tab === 2 }"
                        @click="chgTab(2)"
                    >
                        <img
                            height="45"
                            width="45"
                            src="../assets/color.png"
                            alt="Color"
                        />
                        <ion-label class="settings_menu_item_title">Color</ion-label>
                    </div>
                    <div
                        class="settings_menu_item"
                        :class="{ active: tab === 3 }"
                        @click="chgTab(3)"
                    >
                        <img
                            height="45"
                            width="45"
                            src="../assets/topping.png"
                            alt="Toppings"
                        />
                        <ion-label class="settings_menu_item_title">Toppings</ion-label>
                    </div>
                    <div
                        class="settings_menu_item"
                        :class="{ active: tab === 4 }"
                        @click="chgTab(4)"
                    >
                        <img
                            height="45"
                            width="45"
                            src="../assets/write.png"
                            alt="Print"
                        />
                        <ion-label class="settings_menu_item_title">Write and Print</ion-label>
                    </div>
                </ion-col>
                <ion-col class="settings_items" size="9">
                    <ion-row class="menu_items">
                        <ion-col class="menu_card" size="5" v-for="i in 10" :key="i">
                            <ion-img
                                src="../assets/Shape.png"
                                alt="Shape"
                            />
                            <ion-label class="settings_menu_item_title">
                                circle - {{ i }}
                            </ion-label>
                        </ion-col>
                    </ion-row>
                </ion-col>
            </ion-row>
        </ion-grid>
    </ion-page>
</template>

<script>
import {
  IonGrid,
  IonRow,
  IonCol,
  IonLabel,
  IonButton,
  IonPage
} from "@ionic/vue";
import mergeImages from 'merge-images';
export default {
    name: 'Constructor',
    components: { IonGrid, IonRow, IonCol, IonLabel, IonButton, IonPage },
    data() {
        return {
            tab: 0
        }
    },
    methods: {
        chgTab(tab) {
            this.tab = tab;
        },
        loadImage() {
            console.log(document.querySelector('#test'))
            const data_list = [];
            const img_list = document.querySelectorAll('.cakeImg');
            for (const img of img_list) {
                data_list.push(img.src)
            }
            mergeImages(data_list)
                .then(b64 => document.querySelector('#test').src = b64);
        }
    }
}
</script>


<style>
.constructor {
    height: 80vh;
}
.demo {
    height: 40vh;
    background-color: grey;
}
.settings {
    height: 47vh;
    overflow: auto;
}
.settings_menu {
    height: 100%;
    overflow: auto;
    background-color: #9932cc;
    border-radius: 0 10px 10px 0;
}
.settings_menu_item {
    text-align: center;
    margin-top: 20px;
    height: 70px;

}
.settings_menu_item_title {
    color: white;
}
.settings_items {
    height: 47vh;
    overflow: auto;
}
.menu_items {
    flex-wrap: wrap;
}
.menu_card {
    height: 90px;
    background-color: grey;
    margin: 5px 10px;
}
.active {
    background-color: #e6e6fa;
}
.cakeImg {
    display: none;
}

</style>
