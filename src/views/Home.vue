<template>
  <!-- <Navbar /> -->
  <section class="hero">
    <div class="heroContainer">
      <button class="toggle" @click="flipLightMode">darkmode</button>
      <h1>CoutureFest'21</h1>
      <div class="data">
        <hr />
        <p>6 a 12 de Dezembro</p>
        <hr />
      </div>
      <p>
        A MELHOR feira de custura e moda da peninsula Ibérica, realizada em
        Portugal, reunindo centenas de custoreiros nacionais.
      </p>
      <div class="heroButtons">
        <button>Ver mais</button>
        <button>Participa!</button>
      </div>
      <div class="heroFeatures">
        <div class="featuresContainer">
          <i class="fas fa-cut"></i>
          <h2>Workshops</h2>
          <p>Workshops para consolidar o seu conhecimento</p>
        </div>
        <div class="featuresContainer">
          <i class="fab fa-artstation"></i>
          <h2>Exposições</h2>
          <p>Exposição das melhores peças da época</p>
        </div>
        <div class="featuresContainer">
          <i class="fas fa-medal"></i>
          <h2>Concurso</h2>
          <p>5000€ em prémios para os melhores designs</p>
        </div>
        <div class="featuresContainer">
          <i class="fas fa-network-wired"></i>
          <h2>Networking</h2>
          <p>Conheça com os melhores da indústria!</p>
        </div>
      </div>
      <!--  <div class="datasAndSocials">
        <hr />
        <p>6 a 12 de Dezembro</p>
        <i class="fab fa-instagram-square"></i>
        <i class="fab fa-facebook-square"></i>
        <hr />
      </div> -->
    </div>
    <img src="@/assets/modelo5.jpg" alt="" />
  </section>
  <section class="workshops">
    <h1>⚆ WORKSHOPS</h1>
    <div class="workshopsContainer">
      <WorkshopCard v-for="index in 10" :key="index" />
    </div>
  </section>
</template>

<script>
import WorkshopCard from "@/components/WorkshopCard.vue";
export default {
  name: "Home",
  data() {
    return {
      currentTheme: "light",
      lightModeTextColor: "#2c3e50",
      lightModeBackgroundColor: "#ffeff1",
    };
  },
  components: {
    WorkshopCard,
  },
  methods: {
    flipLightMode() {
      const body = document.querySelector("body");
      if (this.currentTheme === "light") {
        this.lightModeTextColor = "#ffeff1";
        this.lightModeBackgroundColor = "#2c3e50";
        this.currentTheme = "dark";
      } else {
        this.lightModeBackgroundColor = "#ffeff1";
        this.lightModeTextColor = "#2c3e50";
        this.currentTheme = "light";
      }

      body.style.background = this.lightModeBackgroundColor;
      body.style.color = this.lightModeTextColor;
    },
  },
};
</script>

<style scoped lang="scss">
$rosaFixe: #ffeff1;

.hero {
  height: 100vh;
  display: flex;
  padding: 100px 100px 0 100px;

  .heroContainer {
    padding-top: 50px;

    .toggle {
      position: absolute;
      top: 50px;
      left: 50px;
    }
    h1 {
      font-size: 100px;
      margin-top: 0;
      margin-bottom: 10px;
      text-transform: uppercase;
    }

    p {
      font-size: 20px;
      max-width: 800px;
    }

    .heroButtons {
      margin-top: 30px;
      button {
        border: 0;
        outline: 1px solid v-bind(lightModeTextColor);
        color: v-bind(lightModeTextColor);
        background-color: transparent;
        padding: 20px 30px;
        text-transform: uppercase;
        font-weight: bold;
        font-family: "Poppins", sans-serif;
        transition: all 0.5s cubic-bezier(0.075, 0.82, 0.165, 1);

        &:hover {
          cursor: pointer;
          background-color: v-bind(lightModeTextColor);
          color: v-bind(lightModeBackgroundColor);
        }
      }

      & > :first-child {
        margin-right: 10px;
      }
    }

    .data {
      display: flex;
      align-items: center;
      margin-top: -25px;
      margin-bottom: 20px;
      hr {
        width: 100px;
        height: 2px;
        border: none;
        outline: none;
        margin: 0px 10px;
        background-color: v-bind(lightModeTextColor);
      }

      p {
        margin: 0;
      }

      i {
        font-size: 30px;
        margin: 0 20px;
      }
    }

    .heroFeatures {
      display: flex;
      margin-top: 100px;
      .featuresContainer {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        max-width: 150px;
        text-align: center;
        padding: 20px;
        border: 1px solid v-bind(lightModeTextColor);
        margin-right: 25px;

        i {
          font-size: 30px;
        }

        h2 {
          margin: 10px 0;
        }

        p {
          font-size: 16px;
        }
      }
    }
  }

  img {
    position: absolute;
    top: 0;
    height: 784px;
    right: 200px;
    border-radius: 0 0;
  }
}

.workshops {
  height: 100vh;
  padding: 0px 100px;

  h1 {
    font-size: 60px;
  }

  .workshopsContainer {
    display: flex;
    flex-wrap: wrap;
  }
}
</style>
