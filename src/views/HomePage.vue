<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>SmartEvent</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content class="ion-padding">

      <!-- Banner -->
      <div class="banner">
        <h1>SmartEvent</h1>
        <p>Descubra eventos incríveis perto de você</p>
      </div>

      <!-- Botão principal -->
      <ion-button expand="block" size="large" router-link="/eventos">
        Explorar Eventos
      </ion-button>

      <!-- Menu rápido -->
      <div class="menu">
        <ion-card router-link="/eventos">
          <ion-card-content>
            Eventos
          </ion-card-content>
        </ion-card>

        <ion-card router-link="/favoritos">
          <ion-card-content>
            Favoritos
          </ion-card-content>
        </ion-card>

        <ion-card router-link="/perfil">
          <ion-card-content>
            Perfil
          </ion-card-content>
        </ion-card>
      </div>

    </ion-content>
  </ion-page>
</template>

<script setup>
import {
  IonPage,
  IonHeader,
  IonToolbar,
  IonTitle,
  IonContent,
  IonButton,
  IonCard,
  IonCardContent
} from '@ionic/vue';
</script>

<style scoped>
.banner {
  text-align: center;
  margin-bottom: 30px;
}

.banner h1 {
  font-size: 28px;
  font-weight: bold;
}

.banner p {
  color: gray;
}

.menu {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 15px;
  margin-top: 20px;
}

ion-card {
  text-align: center;
  font-size: 18px;
  cursor: pointer;
  border-radius: 12px;
}

ion-card:hover {
  transform: scale(1.03);
  transition: 0.2s;
}
</style>