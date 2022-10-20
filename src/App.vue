<template>
  <ion-app>
    <ion-router-outlet />
  </ion-app>
</template>

<script lang="ts">
import { IonApp, IonRouterOutlet } from '@ionic/vue';
import { defineComponent, onMounted } from 'vue';
import { StatusBar, Style, Animation } from "@capacitor/status-bar"

export default defineComponent({
  name: 'App',
  components: {
    IonApp,
    IonRouterOutlet
  },
  setup() {
    onMounted(() => {
      StatusBar.setStyle({ style: Style.Dark }).catch(() => {
        // error
      })
      StatusBar.show({ animation: Animation.Slide }).catch(() => {
        // error
      })
    })
  }
});
</script>