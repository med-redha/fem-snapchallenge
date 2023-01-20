<template>
  <div class="landingPage">
    <v-row class=" hidden-sm-and-down">
      <v-col cols="12" md="6">
        <div class="content_sections">
          <div
            class="main_section"
            v-for="(cont, index) in mainSec"
            :key="index"
          >
            <div class="header">{{ cont.header }}</div>
            <p class="description_txt">{{ cont.description }}</p>
            <v-hover v-slot="{hover}">
            <v-btn class="mainSec_btn" :class="hover ? 'main_hover' : ''">{{ cont.mbtn }}</v-btn>
          </v-hover>
          </div>
          <div class="buttom_section">
            <v-btn plain height="68"  class="icon_holder" icon v-for="(icon , index) in icons" :key="index">
              <img class="b_icon" :src="icon.img" alt=""
            />
            </v-btn>
          </div>
        </div>
      </v-col>
      <v-col cols="12" md="6" >
        <div class="hero_section">
          <img
            class="hero_img"
            src="../assets/images/image-hero-desktop.png"
            alt=""
          />
        </div>
      </v-col>
    </v-row>
    <v-row class=" hidden-md-and-up">
      <v-col cols="12" md="6" >
        <div class="hero_section">
          <img
            class="hero_img"
            src="../assets/images/image-hero-mobile.png"
            alt=""
          />
        </div>
      </v-col>
      <v-col cols="12" md="6">
        <div class="content_sections">
          <div
            class="main_section"
            v-for="(cont, index) in mainSec"
            :key="index"
          >
            <div class="header">{{ cont.header }}</div>
            <p class="description_txt">{{ cont.description }}</p>
            <v-hover v-slot="{hover}">
            <v-btn class="mainSec_btn" :class="hover ? 'main_hover' : ''">{{ cont.mbtn }}</v-btn>
          </v-hover>
          </div>
          <div class="buttom_section my-6">
            <v-btn plain   class="icon_holder mr-1" icon v-for="(icon , index) in icons" :key="index">
              <img class="b_icon" :src="icon.img" alt=""
            />
            </v-btn>
          </div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
import svOne from '../assets/images/databiz.svg';
import svTwo from '../assets/images/audiophile.svg';
import svThree from '../assets/images/maker.svg';
import svFour from '../assets/images/meet.svg';
export default {
  name: "snapChallenge",

  data() {
    return {
      mainSec: [
        {
          header: "Make remote work",
          description:
            "Get your team in sync, no matter your location. Streamline processes, create team rituals,and watch productivity soar",
          mbtn: "Learn more",
        },
      ],
      icons: [
        { img: svOne },
        { img: svTwo },
        { img: svThree },
        { img: svFour },
      ],
    };
  },
};
</script>
