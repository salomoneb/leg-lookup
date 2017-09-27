<template>
  <div id="app">
    <header class="header">
      <img :src="headerImg" class="capitol">
      <h1>Find a Committee</h1>
    </header>
    <chamberdropdown></chamberdropdown>
    <footer class="footer"><p>Data via <a href="https://www.propublica.org/datastore/api/propublica-congress-api">ProPublica</a></p></footer>
  </div>
</template>

<script>
import chamberdropdown from './components/ChamberDropdown'

export default {
  name: "app",
  data: function() {
    return {
      headerImg: require("./assets/images/capitol.svg")
    }
  },
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
  text-align: left;
  word-wrap: break-word;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
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
  border: 1px solid #a7a8ab;
  box-shadow: 0 2px 5px 1px #F4F5F7;
  font-size: 14px;
  display: block;
  height: 2em;
  margin-bottom: 1em;
  padding: 1em;
  width: 100%;
}
.header {
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin-bottom: 2em;

  h1 {
    font-size: 2.1em;
    font-weight: 700;
    margin: 0;
  }

  .capitol {
    margin-bottom: 1em;
    width: 4em; 
  }

}
.error-status {
  background: rgba(243, 212, 204, 0.6);
  border-radius: 8px;
  border: 1px solid;
  color: #da3333;
  list-style-type: none;
  margin-top: 2em;
  padding: 0.3em 1em;

  .error-message {
    font-weight: bold;
  }

}
.footer {
  margin-top: 3em;
}
#app {
  background: #fff;
  color: #000;
  box-shadow: 0 2px 2px 0 rgba(0,0,0,.14), 0 3px 1px -2px rgba(0,0,0,.2), 0 1px 5px 0 rgba(0,0,0,.12);
  padding: 1em 8em;
  width: 35%;
}
</style>