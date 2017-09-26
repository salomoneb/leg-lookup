<template>
  <div id="app">
    <header class="header">
      <img src="./assets/images/capitol.svg" class="capitol">
    </header>
    <h1>Lookup A Committee</h1>
    <chamberdropdown></chamberdropdown>
    <footer class="footer"><p>Data via <a href="https://www.propublica.org/datastore/api/propublica-congress-api">ProPublica</a></p></footer>
  </div>
</template>

<script>
import chamberdropdown from './components/ChamberDropdown'

export default {
  name: "app",
  components: {
    chamberdropdown
  }
}
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Open+Sans:400,500,600,700,800");
body, .header {
  display: flex;
}
body {
  align-items: center;
  align-content: center;
/*  background-image: url(https://subtlepatterns.toptal.io/designers/subtlepatterns/wp-content/themes/tweaker7/images/transp_bg.png);*/
  background: #eee;
  flex-direction: column;
  justify-content: flex-start;
  font-family: 'Open Sans', sans-serif;
  margin: 2em 5em;
  min-height: 100vh;
  text-align: left;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
h1 {
  font-size: 2.1em;
  font-weight: 700;
  margin-top: 0;
}
a {
  color: inherit;
  text-decoration: none;
  border-bottom: 2px dotted;
  &:hover {
    opacity: 0.8;
  }
}
select {
  background: transparent;
  border: 1px solid;
  font-size: 14px;
  display: block;
  height: 2em;
  margin-bottom: 1em;
  padding: 1em;
  width: 100%;
}
.header {
  flex-direction: row;
  justify-content: center;
  align-items: center;
}
.capitol {
  width: 4em;
}
.footer {
  margin-top: 3em;
}
#app {
  background: #fff;
  color: #000;
  box-shadow: 0 2px 2px 0 rgba(0,0,0,.14), 0 3px 1px -2px rgba(0,0,0,.2), 0 1px 5px 0 rgba(0,0,0,.12);
  padding: 2em 10em;
}
</style>
