<template>
  <div id="app">
    <main>
      <div class="navigation">
        <header>
          <h1>Afzalbek Orifjonov</h1>
        </header>
        <nav>
          <a href="#">ABOUT US</a>
          <a class="a2" href="#">CONTACT</a>
          <a href="https://github.com/AOrifjonov" target="__blank">PORTFOLIO</a>
        </nav>
      </div>
      <Progressbar :progress="progress" />
      <Post @progressUpdate="setProgress" />
    </main>
  </div>
</template>

<script>
import Post from './components/Post'
import Progressbar from './components/Progressbar'
export default {
  name: 'App',
  components: {
    Post,
    Progressbar
  },
  data(){
    return {
      progress: 0,
    }
  },
  methods: {
    setProgress(progress) {
      this.progress = progress;
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'monospace', sans-serif;
}

main {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  overflow: hidden;
}

.navigation {
  width: 100%;
  height: 10vh;
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: #002337;
  padding: 30px;
}

header h1 {
  color: #fff;
  font-size: 32px;
}

nav a {
  color: #fff;
  text-decoration: none;
  padding: 7px;
}

@media (max-width: 650px) {
  header h1 {
    display: none;
  }
}

@media (max-width: 354px) {
  .a2 {
    display: none;
  }
}
</style>
