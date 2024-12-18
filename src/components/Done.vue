<template>
    <section class="done">
      <h1 class="topic">How's It Done</h1>
      <div class="classdiv">
        <v-card
          class="card"
          max-width="344"
          v-for="n in 4"
          :key="n"
        >
          <div class="circle">{{ n }}</div>
          <v-card-text>
            <h2>adjective</h2>
            <div class="text-medium-emphasis">
              well meaning and kindly.<br />
              "a benevolent smile"
            </div>
          </v-card-text>
        </v-card>
      </div>
    </section>
  </template>
  
  <script>
  export default {
    name: "Done",
  };
  </script>
  
  <style scoped>
  .done {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    gap: 20px;
    margin-top: 50px;
  }
  
  .topic {
    width: 100%;
    display: flex;
    justify-content: center;
    font-weight: lighter;
    font-size: 6ch;
    margin-top: 60px;
  }
  
  .classdiv {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
    margin-top: 50px;
    width: 100%;
    max-width: 1200px;
    padding: 0 20px;
  }
  
  .circle {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background-color: #77abee;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 1.5rem;
    font-weight: bold;
    color: #333;
  }
  
  .card {
    width: 100%;
    max-width: 300px;
    height: 300px;
    padding: 20px;
    box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }
  
  @media screen and (max-width: 768px) {
    .classdiv {
      grid-template-columns: 1fr;
    }
  }
  </style>
  