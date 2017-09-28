<template>
  <div id="app">
    <header class="header">
    <svg fill="#fff" class="capitol" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" viewBox="0 0 100 110">
      <path d="M72.6,53.3c-8-1.1-15.1-1.5-22.6-1.5s-14.5,0.4-22.6,1.5c-1.5,0.3-2.5,2.1-2.5,3.4c0,1,0,11.2,0,11.2c0.7-0.1,2-0.2,3.8-0.3  v-8.7c0-1.4,1.1-2.6,2.5-2.7c1.3-0.1,2.4,0.9,2.4,2.3v8.8c2.2-0.1,4.8-0.2,7.6-0.3v-9.2c0-1.4,1.1-2.5,2.5-2.5c1.4,0,2.5,1,2.5,2.4  v9.2c2.4,0,5.2,0,7.6,0v-9.2c0-1.4,1.1-2.4,2.5-2.4c1.3,0,2.5,1.2,2.5,2.5V67c2.8,0.1,5.4,0.2,7.6,0.3v-8.8c0-1.4,1.1-2.4,2.4-2.3  c1.4,0.1,2.5,1.3,2.5,2.7v8.7c1.8,0.1,3.1,0.2,3.8,0.3c0,0,0-10.2,0-11.2C75.3,55.3,74.1,53.6,72.6,53.3z"/>
      <path d="M50,69.4c-20.5,0-34.6,2.4-34.6,2.4V95l2.6-0.1c17.7-0.6,30.1-0.7,32-0.7s14.7,0.1,32.3,0.7l2.3,0.1V71.8  C84.6,71.8,70.5,69.4,50,69.4z M27.4,87.8c0,1.3-1.1,2.5-2.5,2.7c-1.3,0.1-2.4-0.8-2.4-2.2c0-3.6,0-7.2,0-10.8  c0-1.3,1.1-2.6,2.4-2.7c1.3-0.1,2.5,0.9,2.5,2.2C27.4,80.7,27.4,84.3,27.4,87.8z M39.9,87c0,1.3-1.1,2.5-2.5,2.6  c-1.4,0.1-2.5-1-2.5-2.3c0-3.6,0-7.2,0-10.8c0-1.3,1.1-2.5,2.5-2.6c1.4-0.1,2.5,1,2.5,2.3C39.9,79.9,39.9,83.4,39.9,87z M52.5,86.8  c0,1.3-1.1,2.4-2.4,2.4c-1.4,0-2.5-1.1-2.5-2.4c0-3.6,0-7.2,0-10.8c0-1.3,1.1-2.5,2.5-2.5s2.4,1.1,2.4,2.5  C52.5,79.7,52.5,83.3,52.5,86.8z M65.1,87.3c0,1.3-1.1,2.4-2.5,2.3c-1.4-0.1-2.5-1.2-2.5-2.6c0-3.6,0-7.2,0-10.8  c0-1.3,1.1-2.4,2.5-2.3c1.4,0.1,2.5,1.2,2.5,2.6C65.1,80.1,65.1,83.7,65.1,87.3z M77.5,88.3c0,1.3-1.1,2.3-2.4,2.2  c-1.3-0.1-2.4-1.3-2.4-2.7c0-3.6,0-7.2,0-10.8c0-1.3,1.1-2.4,2.4-2.2c1.3,0.1,2.4,1.4,2.4,2.7C77.5,81.2,77.5,84.8,77.5,88.3z"/>
      <path d="M72.4,50.5c-0.3-12-8.6-23.2-22.4-23.2S27.9,38.3,27.6,50.5C31.8,49.8,52.5,47.4,72.4,50.5z"/>
      <path d="M57.2,23.3c0-2.6-1.7-4.7-3.7-5.7V8.5C53.5,6.6,51.9,5,50,5s-3.5,1.6-3.5,3.5v9.3c-1.9,1-3.4,3-3.4,5.5  c0,0.7-0.2,1.6-0.4,2.5c2.7-0.8,5.2-1,7.4-1c2.2,0,4.7,0.3,7.4,1C57.3,24.9,57.2,24,57.2,23.3z"/>
    </svg>      
      <h1>Find a Committee</h1>
    </header>
    <chamberdropdown></chamberdropdown>
    <footer class="footer"><p>Data via <a href="https://www.propublica.org/datastore/api/propublica-congress-api" target="_blank">ProPublica</a></p></footer>
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
  background: #eee;
  flex-direction: column;
  justify-content: center;
  font-family: 'Open Sans', sans-serif;
  margin: 2em 5em;  
  text-align: left;
  word-break: break-word;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
#app {
  background: #fff;
  color: #000;
  box-shadow: 0 2px 2px 0 rgba(0,0,0,.14), 0 3px 1px -2px rgba(0,0,0,.2), 0 1px 5px 0 rgba(0,0,0,.12);
  padding: 1em 5em;
  width: 40%;
}
a {
  color: #345f96;
  font-weight: 600;
  border-bottom: 2px dotted;
  text-decoration: none;
  &:hover {
    color: #3e71b3;
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
    background-color: #000;
    border-radius: 8px;
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
.committee-facts {
  border: 1px solid #ccc;
  border-radius: 4px;
  padding: 1em 1.5em;
  margin: 1.5em 0; 
  h2 {
    margin: 0 0 1rem;
    text-align: center;
  }
  p {
    margin: 0 0 0.4em;
  }
  .bold {
    font-weight: bold;
  }
}
.committee-members {
  border-collapse: collapse;
  border-spacing: 1em;
  width: 100%;

  .member-info{
    td {
      padding: 4px;
    }
    &:nth-child(even) {
      background: rgba(221, 221, 221, 0.4);
    }
  }
}

</style>