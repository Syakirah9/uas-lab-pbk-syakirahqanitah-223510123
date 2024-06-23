<template>
    <div class="q-pa-md centered-container">
      <q-page>
        <q-card class="weather-card">
          <q-card-section>
            <div class="title">Cek Suhu dan Cuaca</div>
          </q-card-section>
          <q-card-section class="search-section">
            <q-input
              v-model="city"
              placeholder="Masukkan Lokasi"
              dense
              outlined
              class="search-input"
            />
            <q-btn
              @click="fetchWeather"
              label="cari"
              dense
              flat
              class="search-button"
            />
          </q-card-section>
          <q-card-section v-if="loading">
            <div class="loading-text">Mengambil data...</div>
          </q-card-section>
          <q-card-section v-if="weather">
            <div class="weather-info">
              <div class="info-item">Lokasi: {{ city }}</div>
              <div class="info-item">Suhu: {{ weather.main.temp }}°C</div>
              <div class="info-item">Kondisi: {{ weather.weather[0].description }}</div>
            </div>
          </q-card-section>
          <q-card-section v-if="error">
            <div class="error-text">Error: {{ error }}</div>
          </q-card-section>
        </q-card>
      </q-page>
    </div>
  </template>
  
  
  <script>
  import axios from 'axios';
  
  export default {
    data() {
      return {
        city: '',
        weather: null,
        loading: false,
        error: null
      };
    },
    methods: {
      async fetchWeather() {
        this.loading = true;
        this.weather = null;
        this.error = null;
        try {
          const apiKey = '94bf6d59f86ae95e8071e78240546056';
          const response = await axios.get(
            `https://api.openweathermap.org/data/2.5/weather?q=${this.city}&units=metric&appid=${apiKey}`
          );
          this.weather = response.data;
        } catch (err) {
          this.error = 'Tidak dapat mengambil data cuaca. Silakan coba lagi.';
        } finally {
          this.loading = false;
        }
      }
    }
  };
  </script>
  
  
  <style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap');

* {
  font-family: 'Roboto', sans-serif;
}

.centered-container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  position: relative;
}

.weather-card {
  max-width: 400px;
  width: 100%;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background: linear-gradient(145deg, #ff9b9b, #ffffff);
  padding: 25px;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.title {
  font-size: 1.6rem;
  font-weight: 700;
  color: #333;
  text-align: center;
  margin-bottom: 1.5rem;
}

.search-section {
  display: flex;
  align-items: center;
  margin-bottom: 1.5rem;
}

.search-input {
  flex-grow: 1;
  margin-right: 10px;
  max-width: 300px;
}

.search-button {
  padding: 6px 18px;
  background-color: #ff9b9b;
  color: black !important;
  font-weight: 500;
}

.loading-text, .error-text {
  font-size: 1rem;
  color: #ff6b6b;
  font-weight: 500;
  text-align: center;
  margin-top: 1.5rem;
}

.weather-info {
  font-size: 1rem;
  color: #333;
}

.info-item {
  margin: 0.75rem 0;
}
</style>
