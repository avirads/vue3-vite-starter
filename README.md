To use this template
clone the package  : https://github.com/avirads/vue3-vite-starter.git
pnpm install
pnpm run dev

To create this template from scratch , the below steps were used:

Create a folder with the project name
cd into the folder
pnpm init

add project dependency
pnpm add vue@latest

add developer dependencies

pnpm add vite@latest 
pnpm add @vitejs/plugin-vue@latest -D

inside package.json
	remove main,test sections

	inside scripts section add
	    "dev": "vite",
	    "build": "vite build"    

Create vite.config.js

import { fileURLToPath, URL } from 'node:url'

import { defineConfig } from 'vite'
import vue from '@vitejs/plugin-vue'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [
    vue(),
  ],
  resolve: {
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    }
  }
})

Add a public folder and put favicon.ico inside it.
Add a index.html

<html>
  <head>
    <link rel="icon" href="/favicon.ico">
    <title>Vue Vite App</title>
  </head>
  <body>
    <div id="app"></div>
    <script type="module" src="/src/main.js"></script>
  </body>
</html>




Add src folder 


main.js


import { createApp } from 'vue'
import App from './App.vue'

createApp(App).mount('#app')


App.vue

<script setup>
import Component0 from './components/Component0.vue'
</script>

<template>
  <header>
    <div class="wrapper">
      <Component0 msg="hello world from vite vue" />
    </div>
  </header>

  <main>
    maina
  </main>
</template>

<style scoped>

</style>

Create components folder
Add Component0.vue
Component0.vue

<script setup>
defineProps({
  msg: {
    type: String,
    required: true
  }
})
</script>

<template>
  <div class="greetings">
    <h1>{{ msg }}</h1>
  </div>
</template>

<style scoped>

</style>

Execute pnpm run dev
Open browser and navigate to http://localhost:5173
