<script lang="ts" setup>
    import { modalController, IonPage, IonHeader, IonTitle, IonToolbar, IonButtons, IonButton, IonIcon, IonContent, IonCard, IonCardContent } from "@ionic/vue";
    import { closeCircleOutline } from 'ionicons/icons';
    import { onBeforeMount, onMounted, onUnmounted } from "vue";

    console.log('setup');

    // vue component events are registered here, ionic modal events are registered in the Tab1Page parent component
    onBeforeMount(() => { // when you want to do something before the component is mounted
        console.log('onBeforeMount');
    });
    onMounted(() => { // when you need access to the rendered DOM
        console.log('onMounted');
    });
    onUnmounted(() => { // when you need access to the rendered DOM
        console.log('onUnmounted');
    });

</script>

<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>
                    Page info
                </ion-title>
                <ion-buttons slot="end" class="back-button">
                    <ion-button @click="modalController.dismiss()">
                        <ion-icon slot="icon-only" :icon="closeCircleOutline"></ion-icon>
                    </ion-button>
                </ion-buttons>
            </ion-toolbar>
        </ion-header>
        <ion-content class="ion-padding">
            <ion-card>
                <ion-card-content>
                    Info goes here
                </ion-card-content>
            </ion-card>
        </ion-content>
    </ion-page>
</template>
