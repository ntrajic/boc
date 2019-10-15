<template>
  <scroller>
    <div style="padding:20px;">
      <header>
        <i class="iconfont icon-image"></i>img
        <span class="vue-green">Vue</span>r of Trips with <span class="vue-green">Burnabyoutdoor.com</span>
      </header>
      <div class="descript">
        <!--An image viewer based on Vue.js for mobile-->
        Burnabyoutdoor Club for Nature Lovers, Burnaby, BC, Canada
      </div>

       <div class="subtitle"> Check the latest monthly newsletter
        <a class="vue-green" href="http://www.burnabyoutdoor.com/pdfs/BOC%20Newsletter.pdf" title="BOC Newsletter">BOC Newsletter</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group0
          class="thumbnail"
          v-for="img in list0"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">
        <a class="vue-green" href="img/20190825Galiano/20190825GalianoTripReport.pdf" title=""></a>
        <a class="vue-green"></a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery="'group0_5'"
          class="thumbnail"
          v-for="(img,index) in list0_5"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>

      <div class="subtitle">Mount Baker, Lake Ann, October 6th, 2019
        <a class="vue-green" href="img/20191006LakeAnn/20191006LakeAnnTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group3
          class="thumbnail"
          v-for="img in list3"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">High Falls Creek, September 29th, 2019
        <a class="vue-green" href="img/20190929HighFallsCreek/20190929HighFallsTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group1
          class="thumbnail"
          v-for="img in list1"
          :src="img.src"
          :key="img.src">
      </div>



      <div class="subtitle">Gold Creek Canyon, September 1st, 2019
        <a class="vue-green" href="img/20190901GoldCreekCanyon/2019-09-01-GoldCreekCanyonTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery="'group2_5'"
          class="thumbnail"
          v-for="(img,index) in list2_5"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>


      <div class="subtitle">Galiano Island, August 25th, 2019
        <a class="vue-green" href="img/20190825Galiano/20190825GalianoTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery="'group2'"
          class="thumbnail"
          v-for="(img,index) in list2"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>



      <div class="subtitle">Ptarmigan Ridge, Mount Baker, August 17th, 2019
        <a class="vue-green" href="img/20190817PtarmiganRidge/2019-08-17-PtarmiganRidgeMtBakerTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery="'group3_5'"
          class="thumbnail"
          v-for="(img,index) in list3_5"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>

       <div class="subtitle">Dog Mountain and Suicide Bluffs, July 28th, 2019
        <a class="vue-green" href="img/20190728DogMnt/2019-07-28-DogMnt-Suicide-Bluffs-TripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery="'group7'"
          class="thumbnail"
          v-for="(img,index) in list7"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>

      <div class="subtitle">Buntzen Lake Hike, March 31st, 2019
        <a class="vue-green" href="img/31-03-2019-Buntzen-Lake-Report.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group5
          class="thumbnail"
          v-for="img in list5"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Lynn Canyon Loop, March 24th, 2019
       <a class="vue-green" href="img/2019-03-24-Lynn-Canyon-Report.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group6
          class="thumbnail"
          v-for="img in list6"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle"></div>
      <div style="overflow:hidden">
        <img v-gallery
          class="thumbnail"
          v-for="(img,index) in listN"
          :src="img.src"
          :key="img.src + index">
      </div>
      <div class="subtitle" style="margin-top: 0.6rem;"></div>
      <div style="overflow:hidden">
        <img v-gallery
          class="thumbnail"
          v-for="(img,index) in listN"
          :src="img.src"
          :key="img.src + index">
      </div>

      <div class="subtitle"></div>
      <div style="overflow:hidden">
        <img v-gallery:group4
          class="thumbnail"
          v-for="(img,index) in list4"
          :src="img.thumbnail"
          :data-large="img.src"
          :key="img.src + index">
      </div>

      <footer @click="toBocHome">
        <i class="iconfont icon-github"></i>GoTo Burnabyoutdoor.com, 2019</footer>
    </div>
  </scroller>
</template>

<script>
import Vuer from './Vuer.vue'
export default {
  components: { Vuer },
  mounted(){
    console.log(this.$imgVuer)
  },
  data() {
    return {
      list0_5: [

      ],
      list1: [
        { src: 'img/20190929HighFallsCreek/01-HighFalls.jpg'}, { src: 'img/20190929HighFallsCreek/02-HighFalls.jpg'}, { src: 'img/20190929HighFallsCreek/03-HighFalls.jpg'},
        { src: 'img/20190929HighFallsCreek/04-HighFalls.jpg'}, { src: 'img/20190929HighFallsCreek/05-HighFalls.jpg'}, { src: 'img/20190929HighFallsCreek/06-HighFalls.jpg'},
        { src: 'img/20190929HighFallsCreek/07-HighFalls.jpg'},
      ],
      list2: [
        { src: 'img/20190825Galiano/01-Galiano.jpg'}, { src: 'img/20190825Galiano/02-Galiano.jpg'}, { src: 'img/20190825Galiano/03-Galiano.jpg'},
        { src: 'img/20190825Galiano/04-Galiano.jpg'}, { src: 'img/20190825Galiano/05-Galiano.jpg'}, { src: 'img/20190825Galiano/06-Galiano.jpg'},
        { src: 'img/20190825Galiano/07-Galiano.jpg'},
      ],
      list2_5: [
        { src: 'img/20190901GoldCreekCanyon/01-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/02-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/03-Gold-Creek-Canyon.jpg'},
        { src: 'img/20190901GoldCreekCanyon/04-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/05-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/06-Gold-Creek-Canyon.jpg'},
        { src: 'img/20190901GoldCreekCanyon/07-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/08-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/09-Gold-Creek-Canyon.jpg'},
        { src: 'img/20190901GoldCreekCanyon/10-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/11-Gold-Creek-Canyon.jpg'}, { src: 'img/20190901GoldCreekCanyon/12-Gold-Creek-Canyon.jpg'},
      ],
      list3: [
        { src: 'img/20191006LakeAnn/01-LakeAnn.jpg'}, { src: 'img/20191006LakeAnn/02-LakeAnn.jpg'}, { src: 'img/20191006LakeAnn/03-LakeAnn.jpg'},
        { src: 'img/20191006LakeAnn/04-LakeAnn.jpg'}, { src: 'img/20191006LakeAnn/05-LakeAnn.jpg'}, { src: 'img/20191006LakeAnn/06-LakeAnn.jpg'},
        { src: 'img/20191006LakeAnn/07-LakeAnn.jpg'},
      ],
      list3_5: [
        { src: 'img/20190817PtarmiganRidge/01-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/02-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/03-Ptarmigan-Ridge.jpg'},
        { src: 'img/20190817PtarmiganRidge/04-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/05-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/06-Ptarmigan-Ridge.jpg'},
        { src: 'img/20190817PtarmiganRidge/07-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/08-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/09-Ptarmigan-Ridge.jpg'},
        { src: 'img/20190817PtarmiganRidge/10-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/11-Ptarmigan-Ridge.jpg'}, { src: 'img/20190817PtarmiganRidge/12-Ptarmigan-Ridge.jpg'},
      ],
      list7: [
        { src: 'img/20190728DogMnt/01-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/02-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/03-Dog-Mt--Suicided-Bluffs.jpg'},
        { src: 'img/20190728DogMnt/04-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/05-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/06-Dog-Mt--Suicided-Bluffs.jpg'},
        { src: 'img/20190728DogMnt/07-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/08-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/09-Dog-Mt--Suicided-Bluffs.jpg'},
        { src: 'img/20190728DogMnt/10-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/11-Dog-Mt--Suicided-Bluffs.jpg'}, { src: 'img/20190728DogMnt/12-Dog-Mt--Suicided-Bluffs.jpg'}
      ],
      list5: [
        { src: 'img/01-Buntzen-Lake-1.jpg'}, { src: 'img/02-Buntzen-Lake-2.jpg'}, { src: 'img/03-Buntzen-Lake-3.jpg'},
        { src: 'img/04-Buntzen-Lake-4.jpg'}, { src: 'img/05-Buntzen-Lake-5.jpg'}, { src: 'img/06-Buntzen-Lake-6.jpg'},
        { src: 'img/07-Buntzen-Lake-7.jpg'}, { src: 'img/08-Buntzen-Lake-8.jpg'}, { src: 'img/09-Buntzen-Lake-9.jpg'},
        { src: 'img/10-Buntzen-Lake-10.jpg'},{ src: 'img/11-Buntzen-Lake-11.jpg'},{ src: 'img/12-Buntzen-Lake-12.jpg'}
      ],
      list6: [
        { src: 'img/1-Lower Seymour-Lynn-Canyon-Loop.jpg'}, { src: 'img/2-Lower Seymour-Lynn-Canyon-Loop.jpg'},
        { src: 'img/3-Lower Seymour-Lynn-Canyon-Loop.jpg'}, { src: 'img/4-Lower Seymour-Lynn-Canyon-Loop.jpg'},
        { src: 'img/5-Lower Seymour-Lynn-Canyon-Loop.jpg'}, { src: 'img/6-Lower Seymour-Lynn-Canyon-Loop.jpg'},
        { src: 'img/7-Lower Seymour-Lynn-Canyon-Loop.jpg'}, { src: 'img/8-Lower Seymour-Lynn-Canyon-Loop.jpg'},
      ],
      list0: [
        { src: 'img/BOC-Newsletter.jpg' }
      ]
    }
  },
  methods: {
    toBocHome() {
      location.href = 'http://www.burnabyoutdoor.com'
    }
  }
}
</script>

<style scoped>
.thumbnail {
  display: block;
  float: left;
  margin: 3px;
  height: 100px;
  width: 100px;
  object-fit: cover;
}
pre {
  font-family: Monaco;
  color: #fff;
  padding: 0.5rem;
}
p {
  background: #4d4d4d;
}
header {
  font-size: 2rem;
  color: #fff;
}
footer {
  font-size: 1rem;
  color: #fff;
}
.descript {
  font-size: 1.3rem;
  color: #9a9a9a;
  margin-bottom: 2rem;
}
.subtitle {
  font-size: 1.2rem;
  color: #a7a8aa;
  margin-bottom: 1rem;
}
.vue-green {
  color: #4fc08d;
}
.iconfont {
  font-size: 1.5rem;
  margin: 0.3rem;
}
.gray {
  color: #ccc;
}
</style>
