<script setup>
import timeline from '/src/timeline.json';

</script>


<template>
  <main id="main">
    <h1 id="title">Shin-chan</h1>
    <figure id="img-div">
      <img id="image" :src="imageUrl" />
      <figcaption id="img-caption">Shin-chan un Super-Heroe incomprendido</figcaption>
    </figure>
    <div id="tribute-info">
      <h2>Shinnosuke Nohara aka Shin-chan</h2>
      <ul>
        <li v-for="item in timeline" :key="item.id" class="item-year">{{ item.year }} <span v-html="item.text"></span></li>
      </ul>
      <p>Más información sobre Crayon Shin-chan aquí:
      <a target="_blank" href="https://es.wikipedia.org/wiki/Crayon_Shin-chan">Wikipedia</a>
      </p>
    </div>
  </main>
</template>

<style>
@import './assets/base.css';

#app {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;

  font-weight: normal;
}

header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

a,
.green {
  text-decoration: none;
  color: hsla(160, 100%, 37%, 1);
  transition: 0.4s;
}

#image {
  width: 100px;
}

@media (hover: hover) {
  a:hover {
    background-color: hsla(160, 100%, 37%, 0.2);
  }
}

@media (min-width: 1024px) {
  body {
    display: flex;
    place-items: center;
  }

  #app {
    display: grid;
    grid-template-columns: 1fr 1fr;
    padding: 0 2rem;
  }

  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  .logo {
    margin: 0 2rem 0 0;
  }
}
</style>
