  <script lang="ts">
  import { Component, Prop } from 'vue-property-decorator';
  
  interface Cake {
    name: string;
    image: string;
    description: string;
    ingredients: string[];
    price: number;
  }
  
  @Component
  export default class CakeCard extends Vue {
    @Prop() cake!: Cake; 
  }
  </script>

<template>
    <ion-card>
      <ion-card-header>
        <ion-card-title>{{cake.name}}</ion-card-title>
      </ion-card-header>
      <ion-img :src="cake.image"></ion-img>
      <ion-card-content>
        <p>{{cake.description}}</p>
        <p>Ingredients: {{cake.ingredients.join(', ')}}</p>
        <p>Price: {{cake.price}}</p>
      </ion-card-content>
    </ion-card>
  </template>
  
  