<template>
  <meta name="mobile-web-app-capable" content="yes">
  <ion-app>
    <ion-router-outlet />
    <c-menu />
  </ion-app>
</template>

<script>
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import CMenu from './components/c-menu.vue'
export default {
  name: 'App',
  components: { IonApp, IonRouterOutlet, CMenu }
}
</script>