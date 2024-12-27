<template>
    <section>
    <v-sheet
    class="aboutus"
    max-width="1000"
    >
    <h1 class="topic">Topics</h1>
    <v-slide-group
        show-arrows
        class="slide"
    >
        <v-slide-group-item
        v-for="n in 25"
        :key="n"
        v-slot="{ isSelected, toggle }"
        >
        <v-btn
            :color="isSelected ? 'primary' : 'rgb(58, 110, 165)'"
            class="ma-2"
            rounded
            @click="toggle"
        >
            Options {{ n }}
        </v-btn>
        </v-slide-group-item>
    </v-slide-group>
    <div class="chips">
        <V-chip v-for="n in 25"
        :key="n"
        style="margin-left: 5px;
        margin-top: 5px;">hello {{ n }}</V-chip>
    </div> 
    <h1 class="topic">Expertx</h1>
    <v-slide-group
        show-arrows
        class="slide"
    >
        <v-slide-group-item
        v-for="n in 25"
        :key="n"
        v-slot="{ isSelected, toggle }"
        >
        <v-btn
            :color="isSelected ? 'primary' : 'rgb(58, 110, 165)'"
            class="ma-2"
            rounded
            @click="toggle"
        >
            Options {{ n }}
        </v-btn>
        </v-slide-group-item>
    </v-slide-group>
    <div class="cards">
        <v-card
    
    max-width="400"
    v-for="n in 4"
    :key="n"
  >
    <v-img
      class="align-end text-white"
      height="200"
      :src="images[n - 1]"
      cover
    >
      
    </v-img>

    <v-card-title class="pt-4">
      Number 11
    </v-card-title>

    <v-card-text>
      <div style="color: cadetblue;">Whitehaven Beach</div>

      <div>Whitsunday Island, Whitsunday Islands</div>
    </v-card-text>

    
  </v-card>
</div>
<v-btn>
      View More
</v-btn>
    </v-sheet>
</section>
</template>
<script>
import Image2 from "@/assets/Image-2.png";
import Image3 from "@/assets/Image-3.png";
import Image4 from "@/assets/Image-4.png";
import Image5 from "@/assets/Image-5.png";

export default {
  name: 'AboutUs',
  data() {
    return {
      images: [Image2, Image3, Image4, Image5]
    };
  }
};


</script>
<style scoped>
    .aboutus{
        display: flex;
        height: auto;
        flex-direction: column;
        justify-content: flex-start;
        /* align-items: center; */
        /* background-color: brown; */
        width: 100%;
        margin: auto;
    }
    .slide{
        background-color: rgb(58, 110, 165);
        border-radius: 20px;
        z-index: 999;
    }
    .topic{
        width: 100%;
        /* background-color: aqua; */
        display: flex;
        justify-content: center;
        font-weight: lighter;
        font-size:6ch;
        margin-top: 60px;
    }

    .chips{
        width: 90%;
        /* border: 1px solid black\\\\\\\\; */
        height: 200px;
        margin: auto;
        margin-top: 20px;
        margin-bottom: 0;
        padding: 20px;
        z-index: 0;
    }
    .cards{
        width: 100%;
        /* border: 1px solid black\\\\\\\\; */
        height: 400px;
        margin: auto;
        margin-top: 20px;
        margin-bottom: 0;
        padding: 20px;
        display: flex;
        gap: 20px;
    }
</style>