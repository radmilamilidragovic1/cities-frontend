<script setup>
import NavBar from '@/components/NavBar.vue'
import { RouterView } from 'vue-router'
import '@/styles/body.css'
import AuthForm from '@/components/AuthForm.vue'
</script>

<template>
  <NavBar/>
  <router-view />
  <AuthForm/>
</template>

<style scoped>
</style>
