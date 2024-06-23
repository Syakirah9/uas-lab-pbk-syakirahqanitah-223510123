<template>
    <div class="task-container">
      <q-page>
        <q-card class="task-card">
          <q-card-section>
            <div class="card-title">Tugas Syakirah Qanitah</div>
          </q-card-section>
          <q-list bordered padding>
            <q-item v-for="taskNumber in taskNumbers" :key="taskNumber" clickable @click="goToTask(taskNumber)">
              <q-item-section>
                <q-item-label>{{ `Ini tugas ${taskNumber}, Syakirah Qanitah` }}</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-card>
      </q-page>
    </div>
  </template>
  
  
  <script>
export default {
  data() {
    return {
      taskNumbers: [1, 2, 3, 4, 5, 6, 7]
    };
  },
  methods: {
    goToTask(taskNumber) {
      const taskLinks = {
        1: "https://tugas1-pbk-223510123.vercel.app/",
        2: "https://tugas2-praktikum-pbk.vercel.app/",
        3: "https://tugas3-praktikum-pbk.vercel.app/",
        4: "https://github.com/Syakirah9/Tugas4-Praktikum-PBK.git",
        5: "https://github.com/Syakirah9/Tugas5-Praktikum-PBK.git",
        6: "https://tugas6-praktikum-pbk.vercel.app/",
        7: "https://tugas7-praktikum-pbk.vercel.app/"
      };
      window.open(taskLinks[taskNumber], '_blank');
    }
  }
};
</script>

  
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap');

* {
  font-family: 'Roboto', sans-serif;
}

.task-container {
  background-image: url('src/assets/pp3.jpg');
  background-size: cover;
  background-position: center;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 16px;
}

.task-card {
  max-width: 450px;
  width: 100%;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  background: rgba(255, 182, 193, 0.9); /* Changed to pink */
}

.card-title {
  font-size: 1.6rem;
  font-weight: 700;
  color: #333;
  text-align: center;
  margin-bottom: 1rem;
}

.q-list {
  border-radius: 10px;
}

.q-item {
  padding: 12px 16px;
  border-radius: 5px;
  background-color: #ff9b9b;
  margin-bottom: 8px;
  cursor: pointer;
  transition: background-color 0.3s ease, box-shadow 0.3s ease;
  color: #fff;
  text-decoration: none;
}

.q-item:hover {
  background-color: #ff7f7f;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.q-item-label {
  font-weight: 500;
}
</style>
