<script setup lang="ts">
import { register, ping, ipcHandle } from '../ipcApi'
import Versions from '../components/Versions.vue'

const testRegister = (): void => {
  register({ username: 'testuser', password: '123456' })
}
</script>

<template>
  <img alt="logo" class="logo" src="../assets/electron.svg" />
  <div class="creator">Powered by electron-vite</div>
  <div class="text">
    Build an Electron app with
    <span class="vue">Vue</span>
    and
    <span class="ts">TypeScript</span>
  </div>
  <p class="tip">Please try pressing <code>F12</code> to open the devTool</p>
  <div class="actions">
    <div class="action">
      <a href="https://electron-vite.org/" target="_blank" rel="noreferrer">Documentation</a>
    </div>
    <div class="action">
      <a target="_blank" rel="noreferrer" @click="ipcHandle">Send IPC</a>
    </div>
    <div class="action">
      <a href="#" target="_blank" rel="noreferrer" @click.prevent="ping">Ping</a>
    </div>
    <div class="action">
      <a href="#" target="_blank" rel="noreferrer" @click.prevent="testRegister">Register</a>
    </div>
  </div>
  <Versions />
</template>
