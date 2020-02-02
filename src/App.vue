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

          <button @click="showNews = !showNews">
            <span class="vue-green">Breaking News</span>
          </button>
            <transition
                        @before-enter="beforeEnter"
                        @enter="enter"
                        @after-enter="afterEnter"
                        @enter-cancelled="enterCancelled"

                        @before-leave="beforeLeave"
                        @leave="leave"
                        @after-leave="afterLeave"
                        @leave-cancelled="leaveCancelled"
                        :css="false">
                <div style="width: 320px; height: 100px; background-color: FloralWhite" v-if="showNews">
                        <puff>
                          <article>
                            <h3>
                              <span class="vue-green">
                              Breaking news
                              </span>
                            </h3>
                            <p>
                              <span class="vue-green">
                              BOC wishes Happy and Prosperous New Year of a Rat (Saturday, January 25th, 2020) to all its members!
                              </span>
                            </p>
                          </article>
                        </puff>
                </div>
          </transition>
        <a class="vue-green" href="img/Lunar2020.pdf" title="Happy Lunar New Year">Happy Lunar New Year</a>
        <a class="vue-green" href="img/BOC-NUMEROLOGY-FUN.pdf" title="2-2-2-2">2-2-2-2</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group0
          class="thumbnail"
          v-for="img in list0"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">
        <a class="vue-green" href="" title=""></a>
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

      <div class="subtitle">Buntzen Lake, January 26th, 2020
        <a class="vue-green" href="img/2020012BuntzenLake/20200128BuntzenLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group16
          class="thumbnail"
          v-for="img in list16"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Burnaby Mountain, December 26th, 2019
        <a class="vue-green" href="img/20191226BbyMnt/20191226BbyMntTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group15
          class="thumbnail"
          v-for="img in list15"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Cheakamus Canyon, December 08th, 2019
        <a class="vue-green" href="img/20191208CheakamusCanyon/20191208CheakamusCanyonTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group14
          class="thumbnail"
          v-for="img in list14"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Norvan Falls, December 01st, 2019
        <a class="vue-green" href="img/20191201NorvanFalls/20191201NorvanFallsTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group13
          class="thumbnail"
          v-for="img in list13"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Slhaney Peak, November 24th, 2019
        <a class="vue-green" href="img/20191124SlhaneyPeak/20191124-SlhaneyPeakTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group12
          class="thumbnail"
          v-for="img in list12"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Two Canyon Loop, November 10th, 2019
        <a class="vue-green" href="img/20191110TwoCanyonLoop/20191110TwoCanyonLoop.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group11
          class="thumbnail"
          v-for="img in list11"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Baden Powell, Trail to Quarry Rock, November 3rd, 2019
        <a class="vue-green" href="img/20191103BadenPowell/2019-11-03-Baden-Powell-Trail-to-Quarry-Rock.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group10
          class="thumbnail"
          v-for="img in list10"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Bowen Island, Dorman Point and Killarney Lake, October 27th, 2019
        <a class="vue-green" href="img/20191027BowenIsland/20191027BowenTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group9
          class="thumbnail"
          v-for="img in list9"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Brothers Creek, October 13th, 2019
        <a class="vue-green" href="img/20191013BroCreek/2019-10-13-BroCreekTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group8
          class="thumbnail"
          v-for="img in list8"
          :src="img.src"
          :key="img.src">
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

      <Snow
      :amount="50"
      :size="5"
      :active='true'
      :zIndex="null"
      :image="null"
      :resize="true"
      :wind="0"
      :opacity="0.8"
      :swing="1"
      :speed="1.5"
      color="#ffff00"/>

      <footer @click="toBocHome">
        <i class="iconfont icon-github"></i>GoTo Burnabyoutdoor.com, 2019, 2020</footer>
    </div>
  </scroller>
</template>

<script>
import Snow from '../../vue-niege';  // out of src, out boc
import Vuer from './Vuer.vue'
export default {
  components: { Snow, Vuer },
  mounted(){
    console.log(this.$imgVuer)
  },
  data() {
    return {
      showNews: false,
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
      list8: [
        { src: 'img/20191013BroCreek/01-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/02-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/03-BrothersCreek.jpg'},
        { src: 'img/20191013BroCreek/04-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/05-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/06-BrothersCreek.jpg'},
        { src: 'img/20191013BroCreek/07-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/08-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/09-BrothersCreek.jpg'},
        { src: 'img/20191013BroCreek/10-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/11-BrothersCreek.jpg'}, { src: 'img/20191013BroCreek/12-BrothersCreek.jpg'},
      ],
      list9: [
        { src: 'img/20191027BowenIsland/01-BowenIsland.jpg'}, { src: 'img/20191027BowenIsland/02-BowenIsland.jpg'}, { src: 'img/20191027BowenIsland/03-BowenIsland.jpg'},
        { src: 'img/20191027BowenIsland/04-BowenIsland.jpg'}, { src: 'img/20191027BowenIsland/05-BowenIsland.jpg'}, { src: 'img/20191027BowenIsland/06-BowenIsland.jpg'},
        { src: 'img/20191027BowenIsland/07-BowenIsland.jpg'}, { src: 'img/20191027BowenIsland/08-BowenIsland.jpg'}, { src: 'img/20191027BowenIsland/09-BowenIsland.jpg'},
        { src: 'img/20191027BowenIsland/10-BowenIsland.jpg'},
      ],
      list10: [
        { src: 'img/20191103BadenPowell/01-Quarry_Rock_Trail.jpg'}, { src: 'img/20191103BadenPowell/02-Quarry_Rock_Trail.jpg'}, { src: 'img/20191103BadenPowell/03-Quarry_Rock_Trail.jpg'},
        { src: 'img/20191103BadenPowell/04-Quarry_Rock_Trail.jpg'}, { src: 'img/20191103BadenPowell/05-Quarry_Rock_Trail.jpg'}, { src: 'img/20191103BadenPowell/06-Quarry_Rock_Trail.jpg'},
        { src: 'img/20191103BadenPowell/07-Quarry_Rock_Trail.jpg'}, { src: 'img/20191103BadenPowell/08-Quarry_Rock_Trail.jpg'}, { src: 'img/20191103BadenPowell/09-Quarry_Rock_Trail.jpg'},
        { src: 'img/20191103BadenPowell/10-Quarry_Rock_Trail.jpg'},
      ],
      list11: [
        { src: 'img/20191110TwoCanyonLoop/01-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/02-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/03-Two_Canyon_Loop.jpg'},
        { src: 'img/20191110TwoCanyonLoop/04-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/05-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/06-Two_Canyon_Loop.jpg'},
        { src: 'img/20191110TwoCanyonLoop/07-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/08-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/09-Two_Canyon_Loop.jpg'},
        { src: 'img/20191110TwoCanyonLoop/10-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/11-Two_Canyon_Loop.jpg'}, { src: 'img/20191110TwoCanyonLoop/12-Two_Canyon_Loop.jpg'},
      ],
      list12: [
        { src: 'img/20191124SlhaneyPeak/01-Slhaney-Peak.jpg'}, { src: 'img/20191124SlhaneyPeak/02-Slhaney-Peak.jpg'}, { src: 'img/20191124SlhaneyPeak/03-Slhaney-Peak.jpg'},
        { src: 'img/20191124SlhaneyPeak/04-Slhaney-Peak.jpg'}, { src: 'img/20191124SlhaneyPeak/05-Slhaney-Peak.jpg'}, { src: 'img/20191124SlhaneyPeak/06-Slhaney-Peak.jpg'},
      ],
      list13: [
        { src: 'img/20191201NorvanFalls/01-Norvan_Falls.jpg'}, { src: 'img/20191201NorvanFalls/02-Norvan_Falls.jpg'}, { src: 'img/20191201NorvanFalls/03-Norvan_Falls.jpg'},
        { src: 'img/20191201NorvanFalls/04-Norvan_Falls.jpg'}, { src: 'img/20191201NorvanFalls/05-Norvan_Falls.jpg'}, { src: 'img/20191201NorvanFalls/06-Norvan_Falls.jpg'},
        { src: 'img/20191201NorvanFalls/07-Norvan_Falls.jpg'}, { src: 'img/20191201NorvanFalls/08-Norvan_Falls.jpg'}
      ],
      list14: [
        { src: 'img/20191208CheakamusCanyon/1-P4970363.jpg'}, { src: 'img/20191208CheakamusCanyon/2-P4970364.jpg'}, { src: 'img/20191208CheakamusCanyon/3-P4970370.jpg'},
        { src: 'img/20191208CheakamusCanyon/4-P4970373.jpg'}, { src: 'img/20191208CheakamusCanyon/5-P4970375.jpg'}, { src: 'img/20191208CheakamusCanyon/6-P4970377.jpg'},
        { src: 'img/20191208CheakamusCanyon/7-P4970379.jpg'},
      ],
      list15: [
        { src: 'img/20191226BbyMnt/01-BurnabyMountain.jpg'}, { src: 'img/20191226BbyMnt/02-BurnabyMountain.jpg'}, { src: 'img/20191226BbyMnt/03-BurnabyMountain.jpg'},
        { src: 'img/20191226BbyMnt/04-BurnabyMountain.jpg'}, { src: 'img/20191226BbyMnt/05-BurnabyMountain.jpg'},
      ],
      list16: [
        { src: 'img/2020012BuntzenLake/01-Buntzen_Lake.jpg'}, { src: 'img/2020012BuntzenLake/02-Buntzen_Lake.jpg'}, { src: 'img/2020012BuntzenLake/03-Buntzen_Lake.jpg'},
        { src: 'img/2020012BuntzenLake/04-Buntzen_Lake.jpg'}, { src: 'img/2020012BuntzenLake/05-Buntzen_Lake.jpg'}, { src: 'img/2020012BuntzenLake/06-Buntzen_Lake.jpg'},
        { src: 'img/2020012BuntzenLake/07-Buntzen_Lake.jpg'}, { src: 'img/2020012BuntzenLake/08-Buntzen_Lake.jpg'}, { src: 'img/2020012BuntzenLake/09-Buntzen_Lake.jpg'},
        { src: 'img/2020012BuntzenLake/10-Buntzen_Lake.jpg'},
      ],
      list0: [
        { src: 'img/BOC-Newsletter.jpg' }, { src: 'img/TELEMMGLPICT-LUNAR2020.jpg' }, { src: 'img/2-2-2-2.jpg' }
      ]
    }
  },
  methods: {
    toBocHome() {
      location.href = 'http://www.burnabyoutdoor.com'
    },
    beforeEnter(el) {
      console.log('beforeEnter');
      this.elementWidth = 320;
      el.style.width = this.elementWidth + 'px';
    },
    enter(el, done) {
      console.log('enter');
      let round = 1;
      const interval = setInterval(() => {
          el.style.width = (this.elementWidth + round * 10) + 'px';
          round++;
          if (round > 20) {
              clearInterval(interval);
              done();
          }
      }, 20);
    },
    afterEnter(el) {
      console.log('afterEnter');
    },
    enterCancelled(el) {
      console.log('enterCancelled');
    },
    beforeLeave(el) {
      console.log('beforeLeave');
      this.elementWidth = 320;
      el.style.width = this.elementWidth + 'px';
    },
    leave(el, done) {
      console.log('leave');
      let round = 1;
      const interval = setInterval(() => {
          el.style.width = (this.elementWidth - round * 10) + 'px';
          round++;
          if (round > 20) {
              clearInterval(interval);
              done();
          }
      }, 20);
    },
    afterLeave(el) {
      console.log('afterLeave');
    },
    leaveCancelled(el) {
      console.log('leaveCancelled');
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
.card {
  position: relative;
  background-color: FloralWhite;
  //background-color: lightgreen;
  width: 26em;
  height: 9em;
  margin: 0.5em;
  padding: 0.2em;
  font-family: sans-serif;
  box-shadow: 0px 0px 10px 2px rgba(0, 0, 0, 0.3);
}
puf {
  float: left;
  padding: 5px
}
.v-enter {
  opacity: 0
}
.v-enter-active {
  transition: opacity 2s
}
</style>
