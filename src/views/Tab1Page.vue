<script setup lang="ts">
import { IonPage, IonHeader, IonToolbar, IonTitle, IonContent, IonButton, IonButtons, IonFab, IonFabButton, IonIcon, modalController } from '@ionic/vue';
import { chevronBackOutline } from 'ionicons/icons';
import ExploreContainer from '@/components/ExploreContainer.vue';
import SampleModal from '@/components/SampleModal.vue';

const presentModal = async () => {
  const modal = await modalController.create({
      component: SampleModal,
      breakpoints: [0, 0.65],
      initialBreakpoint: 0.65,
  });
  return modal.present();
}
</script>

<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
          <ion-buttons slot="start">
            <ion-fab>
              <ion-fab-button size="small">
                <ion-icon :icon="chevronBackOutline"></ion-icon>
              </ion-fab-button>
            </ion-fab>
          </ion-buttons>
        <ion-title style="margin-left: 40px">Tab 1</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content :fullscreen="true">

      <ExploreContainer name="Tab 1 page" />

      <ion-button :router-link="'/tabs/tab2'" expand="block">Go to Tab2 (full path)</ion-button>
      <ion-button :router-link="'tab2'" expand="block">Go to Tab2 (relative path)</ion-button>
      <br>
      <ion-button @click="presentModal" expand="block">Open Modal</ion-button>

    </ion-content>
  </ion-page>
</template>
