<template>
  <div class="websitesdiv">
    <div v-for="(link, index) in links" :key="index" class="card">
      <!--<img  class="card-img-top" :src="link.previewImg" :alt="`${link.websitename} logo`"> Maybe a picture of the site itself?-->
      <div class="card-body">
        <i v-html="link.icon"></i>
        <h5 class="card-title">{{ link.websitename }}</h5>
        <p class="card-text">{{ link.description }}</p>
        <div class="row">
          <div class="col">
            <a :href="`//${link.url}`" class="btn btn-primary" target="_blank">Visit {{ link.websitename }}</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "OtherWebsites",
  data() {
    return {
      links: [
        {
          websitename: "CSVEditor",
          url: "bit.ly/36pfXbv",
          description: "Efficiently add/remove rows from your CSV files and export with either comma, semicolumn, piping or double piping.",
          icon: "<i class=\"fas fa-file-csv csvstyling\"></i>",
          previewImg: "https://media.discordapp.net/attachments/852262452291960842/862684240096919572/Schermafbeelding_2021-07-08_151823.png?width=837&height=676"
        },
        {
          websitename: "Dogs",
          url: "bit.ly/3jPtCRf",
          description: "Checkout most common dog breeds and compare their personality to see which one is right for you",
          icon: "<i id=\"dogIcon\" class=\"fas fa-dog\"></i>",
          previewImg: "https://media.discordapp.net/attachments/852262452291960842/862682744650727464/Schermafbeelding_2021-07-08_151249.png?width=688&height=676"
        },
      ]
    }
  },
}
</script>

<style scoped>
html {
  height: 100%;
}

#mainTitle {
  padding-top: 2em;
}

i {
  font-size: 200px;
  color: #3d3d3d
}

.card {
  width: 100%;
  border: none;
}

.card-text {
  width: 50%;
  margin: auto;
  padding-bottom: 20px;
}

.fulldiv {
  display: flex;
  flex-direction: column;
  font-size: 20px;
}

.card-title {
  font-weight: bold;
}


.websitesdiv {
  display: flex;
  justify-content: center;
  width: 75%;
  margin: auto;
  margin-top: 4%;
}

@media only screen and (max-width: 900px) {
  .websitesdiv {
    display: block;
    width: 100%;
  }

  i {
    font-size: 170px;
  }

  .card {
    margin-bottom: 20px;
  }
}
</style>