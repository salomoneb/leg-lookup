<template>
  <div id="app">
    <header class="header">
    <svg class="capitol" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" version="1.1" viewBox="0 0 100 100">
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
  flex-direction: column;
  justify-content: center;
  font-family: 'Open Sans', sans-serif;
  margin: 1em 5em;  
  text-align: left;
  word-break: break-word;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  @media screen and (max-width: 928px) {
    margin: 1em;
  }
}
a {
  border-bottom: 2px dotted;
  color: #2980b9;
  font-weight: 600;
  transition-duration: 0.1s;
  text-decoration: none;
}
select {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;  
  background: url(./assets/images/arrow.svg) no-repeat right 10px center;
  background-size: auto 60%;
  border: 1px solid #a7a8ab;
  border-radius: 5px;
  box-shadow: 0 2px 5px 1px #F4F5F7;
  display: block;
  font-size: 1em;
  padding: 5px 10px;
  margin-bottom: 1em;
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
    border-radius: 8px;
    fill: #444;
    margin-bottom: 1em;
    width: 4em; 
  }

}
.error-status {
  background: #ffe7e8;
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
  background: rgba(255, 251, 0, 0.22);
  border: 1px solid;
  border-radius: 4px;
  margin: 1.5em 0;
  padding: 1em 1.5em;
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
  margin-bottom: 2em;
  width: 100%;
  .member-headers th {
    padding: 6px 4px;
  }
  .member-info{
    td {
      padding: 4px;
    }
    &:nth-child(even) {
      background: rgba(221, 221, 221, 0.4);
    }
  }
}
#app {
  color: #444;
  width: 40%;
  @media screen and (max-width: 928px) {
    width: 100%;
  }
}
#copy-button-container {
  text-align: center;
  & .copy-button {
    background: linear-gradient(#ea4335, #ea4d4d);
    border: none;
    border-radius: 3px;
    border-style: none;
    color: #fff;
    cursor: pointer;
    font-family: inherit;
    font-size: 1em;
    font-weight: 600;
    padding: 0.5em 1em;

    &:focus {
      outline: 0;
    }
    &:active, &:hover {
      background: #e24242;
    }
  }
}

</style>