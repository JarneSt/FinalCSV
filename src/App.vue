<template>
  <div class="nav sticky">
    <h1 id="cvDesktop">Curriculum vitae</h1>
    <h1 id="splitline">|</h1>

    <div class="linksDropdownMobile">
      <button aria-label="Main Menu"
              class="menu"
              onclick="this.classList.toggle('opened');this.setAttribute('aria-expanded', this.classList.contains('opened'))"
              @click="displayNavbarMobile()">
        <svg height="100" viewBox="0 0 100 100" width="100">
          <path class="line line1"
                d="M 20,29.000046 H 80.000231 C 80.000231,29.000046 94.498839,28.817352 94.532987,66.711331 94.543142,77.980673 90.966081,81.670246 85.259173,81.668997 79.552261,81.667751 75.000211,74.999942 75.000211,74.999942 L 25.000021,25.000058"/>
          <path class="line line2" d="M 20,50 H 80"/>
          <path class="line line3"
                d="M 20,70.999954 H 80.000231 C 80.000231,70.999954 94.498839,71.182648 94.532987,33.288669 94.543142,22.019327 90.966081,18.329754 85.259173,18.331003 79.552261,18.332249 75.000211,25.000058 75.000211,25.000058 L 25.000021,74.999942"/>
        </svg>
      </button>
    </div>
    <div class="linksDesktop">
      <router-link to="/">Home</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/contact">Contact</router-link>
    </div>
  </div>

  <div class="linksMob">
    <div class="flex-column d-flex">
      <router-link to="/">Home</router-link>
      <router-link to="/projects">Projects</router-link>
      <router-link to="/contact">Contact</router-link>
    </div>
  </div>
  <router-view/>
</template>


<script>
export default {
  methods: {
    displayNavbarMobile() {
      if (this.navOpened === true) {
        document.querySelector('.linksMob').style.display = "none";
        document.querySelector('.linksMob').style.opacity = "0";

        this.navOpened = false;
      } else {
        document.querySelector('.linksMob').style.display = "block";
        document.querySelector('.linksMob').style.opacity = "100";
        this.navOpened = true;
      }
    }
  },
  data() {
    return {
      navOpened: false
    }
  },
  mounted() {

  }
}
</script>


<style scoped>
* {
  transition: 0.3s background-color, 0.3s color, 4s opacity;
  font-family: "Poppins Light", serif;
}

/* Dropdown Button */
.dropbtn {
  background-color: #3ab0f6;
  color: white;
  border: none;
  min-width: 160px;
  justify-content: flex-end;
}

svg {
  width: 35px;
}

.linksMob {
  font-weight: bold;
  color: black;
  text-decoration: none;
  font-size: 17px;
  display: none;
  opacity: 0;
  box-shadow: black 0px 0px 4px -2px;
}

.linksMob a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
}

.router-link-active, .router-link-exact-active {
  color: cornflowerblue !important;
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
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
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
.dropdown-content a:hover {
  background-color: #ddd;
}

/* Show the dropdown menu on hover */
.linksDropdownMobile:hover .dropdown-content {
  display: block;
}

/* Change the background color of the dropdown button when the dropdown content is shown */
/*
.linksDropdownMobile:hover .dropbtn {
  background-color: #1797e0;
}

 */
.menu {
  background-color: transparent;
  border: none;
  cursor: pointer;
  display: flex;
  padding: 0;
}

.line {
  fill: none;
  stroke: black;
  stroke-width: 6;
  transition: stroke-dasharray 600ms cubic-bezier(0.4, 0, 0.2, 1),
  stroke-dashoffset 600ms cubic-bezier(0.4, 0, 0.2, 1);
}

.line1 {
  stroke-dasharray: 60 207;
  stroke-width: 6;
}

.line2 {
  stroke-dasharray: 60 60;
  stroke-width: 6;
}

.line3 {
  stroke-dasharray: 60 207;
  stroke-width: 6;
}

.opened .line1 {
  stroke-dasharray: 90 207;
  stroke-dashoffset: -134;
  stroke-width: 6;
}

.opened .line2 {
  stroke-dasharray: 1 60;
  stroke-dashoffset: -30;
  stroke-width: 6;
}

.opened .line3 {
  stroke-dasharray: 90 207;
  stroke-dashoffset: -134;
  stroke-width: 6;
}


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

.nav {
  box-shadow: 0px 0px 6px -3px black;
  display: flex;
  justify-content: space-evenly;
  padding: 10px;
  background: white;
}

.nav a {
  font-weight: bold;
  color: black;
  text-decoration: none;
  font-size: 17px;
}

.nav a.router-link-exact-active {
  color: cornflowerblue;
}

#cvDesktop {
  margin-bottom: auto;
  margin-top: auto;
  font-size: 22px;
  color: black;
  margin-left: 1rem;
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

.linksMob {
  display: none;
}

.linksDesktop a {
  margin-top: auto;
  margin-bottom: auto;
}

@media only screen and (min-width: 650px) {
  .linksMob {
    display: none !important;
  }
}

@media only screen and (max-width: 650px) {
  .nav {
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

  .linksDropdownMobile {
    display: block !important;
  }

  .linksDesktop {
    display: none;
  }

  .linksMob {
    display: block;
  }

}

</style>
