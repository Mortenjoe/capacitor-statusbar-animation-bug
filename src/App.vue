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
    onMounted(async () => {
      try {
        await StatusBar.setStyle({ style: Style.Dark })
        await StatusBar.show({ animation: Animation.Slide })
      } catch (error) {
        console.log(error)
      }
    })
  }
});
</script>