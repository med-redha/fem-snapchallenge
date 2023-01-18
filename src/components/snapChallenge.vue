<template>
  <div class="landingPage">
    <v-row>
      <v-col cols="6">
        <div class="content_sections">
          <div
            class="main_section"
            v-for="(cont, index) in mainSec"
            :key="index"
          >
            <div class="header">{{ cont.header }}</div>
            <p class="description_txt">{{ cont.description }}</p>
            <v-btn class="mainSec_btn">{{ cont.mbtn }}</v-btn>
          </div>
          <div class="buttom_section">
            
            <v-btn class="icon_holder" icon v-for="(icon , index) in icons" :key="index">
              <img class="b_icon" :src="icon.img" alt=""
            />
            </v-btn>
          </div>
        </div>
      </v-col>
      <v-col cols="6">
        <div class="hero_section">
          <img
            class="hero_img"
            src="../assets/images/image-hero-desktop.png"
            alt=""
          />
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
