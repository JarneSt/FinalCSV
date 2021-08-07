<template>
  <header>
    <div>
      <h1 id="title" class="frost-container">
        <!--
        <span>J</span>
        <span>J</span>
        <span>J</span>
        <span>J</span>
        <span>J</span>
        <span>J</span>
        <span>J</span>-->
        JarneST Development<br><small>(scroll down to get to know me)</small>
      </h1>
    </div>

    <img v-if="onMobile === false" alt="blocks background" class="banner-img"
         src="../assets/blocks.jpg">

    <img v-else alt="party background" class="banner-img"
         src="../assets/tower.jpg">
  </header>
</template>

<script>
window.addEventListener("scroll", function () {
  let title = document.getElementById("title");
  let scrollVal = localStorage.getItem('scroll');
  console.log('previous scrollVal', scrollVal);

  let isMobile = () => {
    if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
      console.log(this.onMobile);
      this.onMobile = true;
      return true
    } else {
      this.onMobile = false;
      return false
    }
  };

  if (isMobile() === false) {
    console.log('We are not on mobile');
    title.style.position = "fixed";
    title.classList.add("frost-container");
    localStorage.setItem('scroll', window.scrollY);
    console.log('new scrollVal', localStorage.getItem('scroll'));
    if (window.scrollY > 250) {
      title.style.opacity = "0";
    }
    if (window.scrollY <= 600) {
      title.style.opacity = "1";
    }

    if (window.scrollY <= 490) {
      title.style.display = "block";

      let scrollVal = localStorage.getItem('scroll');
      console.log('previous scrollVal', scrollVal)

      localStorage.setItem('scroll', window.scrollY);
      console.log('new scrollVal', localStorage.getItem('scroll'));
      if (scrollVal !== localStorage.getItem('scroll')) {
        let el = document.getElementById('title');
        let style = window.getComputedStyle(el, null).getPropertyValue('font-size');
        let fontSize = parseFloat(style);
        let newFontSize = fontSize + 3;

        console.log(fontSize)
        if (fontSize >= 60) {
          title.style.fontSize = 30 + 'px';
        } else if (fontSize < 60) {
          title.style.fontSize = newFontSize + 'px';
        }
      }
    }
  } else if (isMobile() === true) {
    title.style.zIndex = "1";
    title.style.position = "absolute";
    title.classList.remove("frost-container");
  }
})


export default {
  name: "Banner",
  data() {
    return {
      onMobile: false
    }
  },
  mounted() {
    localStorage.setItem('scroll', window.scrollY);

    let title = document.getElementById("title");

    let isMobile = () => {
      if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
        console.log(this.onMobile);
        this.onMobile = true;
        return true
      } else {
        this.onMobile = false;
        return false
      }
    };

    if (isMobile() === false) {
      console.log('We are not on mobile');
      title.style.position = "fixed";
      title.classList.add("frost-container");
      localStorage.setItem('scroll', window.scrollY);
      console.log('new scrollVal', localStorage.getItem('scroll'));
      if (window.scrollY > 250) {
        title.style.opacity = "0";
      }
      if (window.scrollY <= 600) {
        title.style.opacity = "1";
      }

      if (window.scrollY <= 490) {
        title.style.display = "block";

        let scrollVal = localStorage.getItem('scroll');
        console.log('previous scrollVal', scrollVal)

        localStorage.setItem('scroll', window.scrollY);
        console.log('new scrollVal', localStorage.getItem('scroll'));
        if (scrollVal !== localStorage.getItem('scroll')) {
          let el = document.getElementById('title');
          let style = window.getComputedStyle(el, null).getPropertyValue('font-size');
          let fontSize = parseFloat(style);
          let newFontSize = fontSize + 3;

          console.log(fontSize)
          if (fontSize >= 60) {
            title.style.fontSize = 30 + 'px';
          } else if (fontSize < 60) {
            title.style.fontSize = newFontSize + 'px';
          }
        }
      }
    } else if (isMobile() === true) {
      title.style.zIndex = "1";
      title.style.position = "absolute";
      title.classList.remove("frost-container");
    }
  }
}
</script>


<style scoped>
span:nth-child(even):hover {

}

* {
  transition: 1s font-size, 1s opacity;
}

h1 {
  position: fixed;
  color: white;
  font-size: 75px;
  width: 100%;
  text-align: center;
  margin-top: 18%;
  text-shadow: 0px 0px 4px black;
  padding: 50px;
}

img {
  max-width: 100%;
  filter: blur(1px);
  -webkit-filter: blur(1px);
}

.frost-container {
  box-shadow: 0 0 1rem 0 rgb(0 0 0 / 20%);
  border-radius: 5px;
  z-index: 1;
  background: inherit;
  overflow: hidden;
}

.frost-container:before {
  content: "";
  position: absolute;
  background: inherit;
  z-index: -1;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  box-shadow: inset 0 0 2000px rgba(255, 255, 255, .5);
  filter: blur(10px);
  margin: -20px;
}

small {
  font-size: 30px;
}

@media only screen and (max-width: 940px) {
  h1 {
    font-size: 28px;
    margin-top: 44%;
  }

  small {
    font-size: 15px;
  }

}

</style>