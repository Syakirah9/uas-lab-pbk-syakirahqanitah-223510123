<template>
    <q-layout view="hHh lpR fFf">
      <q-header elevated class="bg-primary text-white" height-hint="98">
        <q-toolbar>
          <q-avatar size="lg" class="q-mr-sm">
            <img src="src/assets/PP1.jpeg" alt="Profile Picture">
          </q-avatar>
          <q-toolbar-title>
            <div class="profile-info">
              <div class="name">Syakirah Qanitah</div>
              <div class="id">223510123</div>
              <div class="class">Kelas 4A</div>
            </div>
          </q-toolbar-title>
          <q-space></q-space>
          <q-tabs align="right">
            <q-route-tab to="/tasks" label="TUGAS SYAKIRAH" />
          </q-tabs>
        </q-toolbar>
      </q-header>
  
      <q-page-container>
        <div class="fixed-container">
          <WeatherPage />
        </div>
        <router-view />
      </q-page-container>
    </q-layout>
  </template>
  
  <script>
  import WeatherPage from '../pages/WeatherPage.vue'
  
  export default {
    components: {
      WeatherPage
    }
  }
  </script>
  
  <style lang="scss">
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;700&display=swap');
  
  * {
    font-family: 'Poppins', sans-serif;
  }
  
  .bg-primary {
    background-color: #ff9b9b !important;
  }
  
  .text-white {
    color: #fff !important;
  }
  
  .q-toolbar {
    padding: 0.5rem;
    display: flex;
    align-items: center;
  }
  
  .q-toolbar-title {
    display: flex;
    align-items: center;
  }
  
  .profile-info {
    margin-left: 1rem;
  }
  
  .profile-info .name {
    font-size: 1.5rem;
    font-weight: bold;
  }
  
  .profile-info .id,
  .profile-info .class {
    font-size: 1.2rem;
  }
  
  .q-tabs {
    margin-left: 2rem;
  }
  
  .q-route-tab {
    font-size: 1.2rem;
    font-weight: bold;
  }
  
  .q-page-container {
    padding: 1rem;
  }
  
  .fixed-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    position: relative;
  }
  
  .weather-page {
    padding: 2rem;
    border: 1px solid #ccc;
    border-radius: 0.5rem;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    background: white;
    width: 100%;
    max-width: 400px;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
  }
  
  .weather-page .title {
    font-size: 1.4rem;
    font-weight: 600;
    color: #333;
    text-align: center;
    margin-bottom: 1rem;
  }
  
  .weather-page .search-section {
    display: flex;
    align-items: center;
    margin-bottom: 1rem;
  }
  
  .weather-page .search-input {
    flex-grow: 1;
    margin-right: 10px;
    max-width: 300px;
  }
  
  .weather-page .search-button {
    padding: 5px 15px;
    background-color: #ff9b9b;
    color: black !important;
    font-weight: 500;
  }
  
  .weather-page .loading-text,
  .weather-page .error-text {
    font-size: 1rem;
    color: #ff9b9b;
    font-weight: 500;
    text-align: center;
    margin-top: 1rem;
  }
  
  .weather-page .weather-info {
    font-size: 1rem;
    color: #333;
  }
  
  .weather-page .info-item {
    margin: 0.5rem 0;
  }
  </style>
  