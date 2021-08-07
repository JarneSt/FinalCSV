<template>
  <div id="nav" class="sticky">
    <h1 id="cvDesktop">Curriculum vitae</h1>
    <h1 id="splitline">|</h1>

    <div class="linksDropdownMobile">
      <button class="dropbtn">
        <i class="fa fa-bars"></i>
      </button>
      <div class="dropdown-content">
        <router-link to="/">Home</router-link>
        <router-link to="/projects">Projects</router-link>
        <router-link to="/contact">Contact</router-link>
      </div>
    </div>

    <div class="linksDesktop">
      <router-link to="/">Home</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/contact">Contact</router-link>
    </div>
  </div>
  <router-view/>
</template>

<style scoped>
*{
  transition: 0.3s background-color, 0.3s color;
  font-family: "Poppins Light",serif;
}

/* Dropdown Button */
.dropbtn {
  background-color: #3ab0f6;
  color: white;
  padding: 16px;
  font-size: 16px;
  border: none;
  min-width: 160px;
}

/* The container <div> - needed to position the dropdown content */
.linksDropdownMobile {
  position: relative;
  display: none;
  margin: auto 0;
  z-index: 99999;
}

/* Dropdown Content (Hidden by Default) */
.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0,0,0,0.2);
  z-index: 1;
}

/* Links inside the dropdown */
.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
}

/* Change color of dropdown links on hover */
.dropdown-content a:hover {background-color: #ddd;}

/* Show the dropdown menu on hover */
.linksDropdownMobile:hover .dropdown-content {display: block;}

/* Change the background color of the dropdown button when the dropdown content is shown */
.linksDropdownMobile:hover .dropbtn {background-color: #1797e0;}
</style>
<style>
* {
  transition: 0.3s color;
}

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: black;
  font-family: Poppins, serif;
}

#nav {
  box-shadow: 0px 0px 6px -3px black;
  display: flex;
  justify-content: space-evenly;
  padding: 10px;
  background: white;
}

#nav a {
  font-weight: bold;
  color: black;
  text-decoration: none;
  font-size: 17px;
}

#nav a.router-link-exact-active {
  color: cornflowerblue;
}

#cvDesktop {
  margin-bottom: auto;
  margin-top: auto;
  font-size: 20px;
  color: black;
}


#splitline {
  margin-top: auto;
  margin-bottom: auto;
  font-size: 30px;
}

.linksDesktop {
  display: flex;
  justify-content: space-evenly;
  width: 50%;
}

.linksDesktop a {
  margin-top: auto;
  margin-bottom: auto;
}



@media only screen and (max-width: 650px) {
  #nav {
    justify-content: space-between;
  }
  .linksDesktop {
    display: flex;
    flex-direction: column;
    width: 100%;
  }

  #splitline {
    display: none;
    font-size: 65px;
    margin-left: 2rem;
  }

  .linksDropdownMobile{
    display: block !important;
  }
  .linksDesktop {
    display: none;
  }
}

</style>
