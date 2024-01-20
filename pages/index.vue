<script setup>
const { data } = await useFetch('/api/disney');
const characters = data;
</script>

<template>
  <main>
    <header>
      <h1>DISNEY CHARACTERS</h1>
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
  </main>
</template>

<style>
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
  margin-top: 10px; 
}
</style>

