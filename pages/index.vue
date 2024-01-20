<script setup>
const { data } = await useFetch('/api/disney');
const characters = data;
</script>

<template>
  <main class="main-container">
    <header>
      <strong><h1 class="page-title">DISNEY CHARACTERS</h1></strong>
    </header>

    <section>
      <ul class="characters-list">
        <li v-for="character in characters.data" :key="character.id">
          <div class="character-container">
            <h3>{{ character.name }}</h3>
            <img :src="character.imageUrl" alt="Character Image" />
          </div>
        </li>
      </ul>
    </section>
    <footer>
      <p class="footer-text">2024 John Michael Malbas</p>
    </footer>
  </main>
</template>

<style>
.footer-text {
  background-color: black;
  text-align: center;
  margin-top: 20px;
  color: white; 
}
.main-container {
  background-color: rgb(83, 83, 83); 
  color: white; 
  min-height: 100vh; 
}

.page-title {
  text-align: center;
  background-color: black;
  color: white;
  padding: 20px;
}

.characters-list {
  list-style: none;
  padding: 0;
  display: flex;
  flex-wrap: wrap;
  justify-content: center; 
  align-items: center; 
}

.character-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin: 0; 
  padding: 0; 
  margin-right: 20px; 
}

.character-container img {
  margin-top: 10; 
}


</style>

