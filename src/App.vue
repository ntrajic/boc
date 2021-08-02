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
                <div style="width: 400px; height: 100px; background-color: FloralWhite" v-if="showNews">
                        <puff>
                          <article>
                            <h3>
                              <span class="vue-green">
                              Breaking news
                              </span>
                            </h3>
                            <p>
                              <span class="vue-green">
                              BOC is operating in groups of six following Health Canada restrictions. Larger number of participants are allowed. Stay tuned!
                              </span>
                            </p>
                          </article>
                        </puff>
                </div>
          </transition>
      </div>

      <div style="overflow:hidden">
        <img v-gallery:group0
          class="thumbnail"
          v-for="img in list0"
          :src="img.src"
          :key="img.src">
      </div>
      <div style="overflow:hidden">
        <img v-gallery="'group0_5'"
          class="thumbnail"
          v-for="(img,index) in list0_5"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>
      
      <div class="subtitle">Mamquam River and Smoke Bluffs Park, July 25th, 2021
        <a class="vue-green" href="img/20210725MamquamRiver/20210725MamquamTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group52
          class="thumbnail"
          v-for="img in list52"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Black Mountain - Yew Lake, July 11th, 2021
        <a class="vue-green" href="img/20210711YewBlackMnt/20210711BlackMntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group51
          class="thumbnail"
          v-for="img in list51"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Buntzen Lake Hike, July 05th, 2021
        <a class="vue-green" href="img/20210705BuntzenLake/20210705BuntzenLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group50
          class="thumbnail"
          v-for="img in list50"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Crescent Beach and Park in Surrey, July 01st, 2021
        <a class="vue-green" href="img/20210701CrescentBeach/20210701CrescentTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group49
          class="thumbnail"
          v-for="img in list49"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Poco Trail Bike Trip, June 06th, 2021
        <a class="vue-green" href="img/20210606Poco/20210606PocoTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group48
          class="thumbnail"
          v-for="img in list48"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Shoreline Trail and Coquitlam Crunch, May 30th, 2021
        <a class="vue-green" href="img/20213005Shoreline/20213005ShorelineTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group47
          class="thumbnail"
          v-for="img in list47"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Whyte Lake, May 23rd, 2021
        <a class="vue-green" href="img/20210523WhiteLake/2021-05-23-White-Lake-TR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group46
          class="thumbnail"
          v-for="img in list46"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Minnekhada Regional Park, May 8th, 2021
        <a class="vue-green" href="img/20210508Minnekhada/20210508MinnekhadaRPTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group45
          class="thumbnail"
          v-for="img in list45"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Chadsey Lake, April 18th, 2021
        <a class="vue-green" href="img/20210418ChadseyLake/20210418ChadseyLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group44
          class="thumbnail"
          v-for="img in list44"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Fisherman's Trail, April 11th, 2021
        <a class="vue-green" href="img/20210411Fisherman/20210411FishermanTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group43
          class="thumbnail"
          v-for="img in list43"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Great Trail - Trans Canada Trail, April 04th, 2021
        <a class="vue-green" href="img/20210404TransCanadaTrail/20210404TCTTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group42
          class="thumbnail"
          v-for="img in list42"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Brohm Lake, March 25th, 2021
        <a class="vue-green" href="img/20210325BrohmLake/20210325BrohmLakeTripReport.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group41
          class="thumbnail"
          v-for="img in list41"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Buntzen Lake, March 14th, 2021
        <a class="vue-green" href="img/20210314Buntzen/20210314-Buntzen-Lake-Trail.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group40
          class="thumbnail"
          v-for="img in list40"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Hayward Lake Reservoir, November 8th, 2020
        <a class="vue-green" href="img/20201108HaywardLake/HaywardLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group39
          class="thumbnail"
          v-for="img in list39"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Fisherman's Trail, November 1st, 2020
        <a class="vue-green" href="img/20201101FishermansTrail/FishermansTrailTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group38
          class="thumbnail"
          v-for="img in list38"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Gold Creek Canyon, October 25th, 2020
        <a class="vue-green" href="img/20201025GoldCreekCanyon/GoldCreekCanyonTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group37          class="thumbnail"
          v-for="img in list37"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Campbell Valley Regional Park, October 18th, 2020
        <a class="vue-green" href="img/20201018CampbellValley/20201018CampbellValleyTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group36
          class="thumbnail"
          v-for="img in list36"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">UBC Research Forest, October 4th, 2020
        <a class="vue-green" href="img/20201004UBCRForest/20201004UBCRForestTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group35
          class="thumbnail"
          v-for="img in list35"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Buntzen to Sasamat Lake, September 27th, 2020
        <a class="vue-green" href="img/20200927BuntzenToSasamatLake/20200927BuntzenToSasamatTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group34
          class="thumbnail"
          v-for="img in list34"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Sumas Bike Ride, September 20th, 2020
        <a class="vue-green" href="img/20200920Sumas/0200920SumasBikeRideTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group33
          class="thumbnail"
          v-for="img in list33"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Historic Mushroom, September 09th, 2020
        <a class="vue-green" href="img/20200906HistoricMushroom/20200906HistoricMushroom.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group31
          class="thumbnail"
          v-for="img in list31"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Greendrop and Lindeman Lakes, August 30th, 2020
        <a class="vue-green" href="img/20200830Greendrop/20200830GreendropTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group32
          class="thumbnail"
          v-for="img in list32"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Cheakmus Park, August 23rd, 2020
        <a class="vue-green" href="img/20200823CheakamusCanyon/20200823-CheakamusTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group30
          class="thumbnail"
          v-for="img in list30"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Tynehead Regional Park, August 16th, 2020
        <a class="vue-green" href="img/20200816TyneheadRP/20200816TyneheadTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group29
          class="thumbnail"
          v-for="img in list29"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Minnekhada Regional Park, Bear!, August 09th, 2020
        <a class="vue-green" href="img/20200809MinnekhadaRP/20200809MinnekhadaTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group28
          class="thumbnail"
          v-for="img in list28"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Whyte Lake, August 02nd, 2020
        <a class="vue-green" href="img/20200802WhyteLake/2020-08-02-Whyte-Lake-TR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group27
          class="thumbnail"
          v-for="img in list27"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Brothers Creek, July 12th, 2020
        <a class="vue-green" href="img/20200712BrothersCreek/20200712BrothersCreekTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group26
          class="thumbnail"
          v-for="img in list26"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Smoke Bluffs and Mamquam River, July 5th, 2020
        <a class="vue-green" href="img/20200705SmokeBluffsNMamquamRiver/SmokeBluffsTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group25
          class="thumbnail"
          v-for="img in list25"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Norvan Falls, June 28th, 2020
        <a class="vue-green" href="img/20200628NorvanFalls/NorvanFallsTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group24
          class="thumbnail"
          v-for="img in list24"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Lynn Creek and Seymour River, June 21st, 2020
        <a class="vue-green" href="img/20200621-Lynn-Creek-n-Seymour-River/2020-06-21-Lynn-Valley-Loop.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group23
          class="thumbnail"
          v-for="img in list23"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Petgill Lake, June 14th, 2020
        <a class="vue-green" href="img/20200614-Petgill-Lake/Petgill-Lake-20200614-TR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group22
          class="thumbnail"
          v-for="img in list22"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Brohm Lake, June 07th, 2020
        <a class="vue-green" href="img/20200607BrohmLake/20200607BrohmLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group21_5
          class="thumbnail"
          v-for="img in list21_5"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Black Mountain, March 8th, 2020
        <a class="vue-green" href="img/20200308BlackMnt/20200607BrohmLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group21
          class="thumbnail"
          v-for="img in list21"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Eagle Bluffs, February 22nd, 2020
        <a class="vue-green" href="img/20200222EagleBluffs/missing.pdf" title="Trip Report"></a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group20
          class="thumbnail"
          v-for="img in list20"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Caulfeild Trail and Lighthouse Park, February 16th, 2020
        <a class="vue-green" href="img/20200215CaulifieldLightHouse/20200216CaulfeildTrailnLighthouseParkTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group19
          class="thumbnail"
          v-for="img in list19"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Bowen Lookout, February 9th, 2020
        <a class="vue-green" href="img/20200209BowenLookout/202029BowenLookoutTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group18
          class="thumbnail"
          v-for="img in list18"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Hollyburn Peak, February 2nd, 2020
        <a class="vue-green" href="img/20200202HollyburnPeak/20200202HollyburnPeakTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group17
          class="thumbnail"
          v-for="img in list17"
          :src="img.src"
          :key="img.src">
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
      :active='false'
      :zIndex="null"
      :image="null"
      :resize="true"
      :wind="0"
      :opacity="0.8"
      :swing="1"
      :speed="1.5"
      color="#ffff00"/>

      <footer @click="toBocHome">
        <i class="iconfont icon-github"></i>GoTo Burnabyoutdoor.com, 2019, 2020, 2021</footer>
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
      list17: [
        { src: 'img/20200202HollyburnPeak/01-HollyburnPeak.jpg'}, { src: 'img/20200202HollyburnPeak/02-HollyburnPeak.jpg'}, { src: 'img/20200202HollyburnPeak/03-HollyburnPeak.jpg'},
      ],
      list18: [
        { src: 'img/20200209BowenLookout/01-Bowen_Lookout.jpg'}, { src: 'img/20200209BowenLookout/02-Bowen_Lookout.jpg'}, { src: 'img/20200209BowenLookout/03-Bowen_Lookout.jpg'},
        { src: 'img/20200209BowenLookout/04-Bowen_Lookout.jpg'}, { src: 'img/20200209BowenLookout/05-Bowen_Lookout.jpg'}, { src: 'img/20200209BowenLookout/06-Bowen_Lookout.jpg'},
        { src: 'img/20200209BowenLookout/07-Bowen_Lookout.jpg'}, { src: 'img/20200209BowenLookout/08-Bowen_Lookout.jpg'}, { src: 'img/20200209BowenLookout/09-Bowen_Lookout.jpg'},
        { src: 'img/20200209BowenLookout/10-Bowen_Lookout.jpg'},
      ],
      list19: [
        { src: 'img/20200215CaulifieldLightHouse/01-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/02-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/03-Caulfeild_and_Lighthouse_Park.jpg' },
        { src: 'img/20200215CaulifieldLightHouse/04-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/05-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/06-Caulfeild_and_Lighthouse_Park.jpg' },
        { src: 'img/20200215CaulifieldLightHouse/07-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/08-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/09-Caulfeild_and_Lighthouse_Park.jpg' },
        { src: 'img/20200215CaulifieldLightHouse/10-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/11-Caulfeild_and_Lighthouse_Park.jpg' }, { src: 'img/20200215CaulifieldLightHouse/12-Caulfeild_and_Lighthouse_Park.jpg' },
      ],
      list20: [
        { src: 'img/20200222EagleBluffs/01-20200222EagleBluffs.jpg' }, { src: 'img/20200222EagleBluffs/02-20200222EagleBluffs.jpg' }, { src: 'img/20200222EagleBluffs/03-20200222EagleBluffs.jpg' },
        { src: 'img/20200222EagleBluffs/04-20200222EagleBluffs.jpg' }, { src: 'img/20200222EagleBluffs/05-20200222EagleBluffs.jpg' }, { src: 'img/20200222EagleBluffs/06-20200222EagleBluffs.jpg' },
      ],
      list21: [
        { src: 'img/20200308BlackMnt/1-Black_Mountain.jpg' }, { src: 'img/20200308BlackMnt/2-Black_Mountain.jpg' }, { src: 'img/20200308BlackMnt/3-Black_Mountain.jpg' },
        { src: 'img/20200308BlackMnt/4-Black_Mountain.jpg' }, { src: 'img/20200308BlackMnt/5-Black_Mountain.jpg' }, { src: 'img/20200308BlackMnt/6-Black_Mountain.jpg' },
        { src: 'img/20200308BlackMnt/7-Black_Mountain.jpg' }, { src: 'img/20200308BlackMnt/8-Black_Mountain.jpg' },
      ],
      list21_5: [
        { src: 'img/20200607BrohmLake/01-BrohmLake.jpg' }, { src: 'img/20200607BrohmLake/02-BrohmLake.jpg' }, { src: 'img/20200607BrohmLake/03-BrohmLake.jpg' },
      ],
      list22: [
        { src: 'img/20200614-Petgill-Lake/01-Petgill-Lake.jpg' }, { src: 'img/20200614-Petgill-Lake/02-Petgill-Lake.jpg' }, { src: 'img/20200614-Petgill-Lake/03-Petgill-Lake.jpg' },
        { src: 'img/20200614-Petgill-Lake/04-Petgill-Lake.jpg' }, { src: 'img/20200614-Petgill-Lake/05-Petgill-Lake.jpg' }, { src: 'img/20200614-Petgill-Lake/06-Petgill-Lake.jpg' },
      ],
      list23: [
        { src: 'img/20200621-Lynn-Creek-n-Seymour-River/01-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/02-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/03-Lynn_n_Seymour_Canyon_Loop.jpg' },
        { src: 'img/20200621-Lynn-Creek-n-Seymour-River/04-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/05-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/06-Lynn_n_Seymour_Canyon_Loop.jpg' },
        { src: 'img/20200621-Lynn-Creek-n-Seymour-River/07-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/08-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/09-Lynn_n_Seymour_Canyon_Loop.jpg' },
        { src: 'img/20200621-Lynn-Creek-n-Seymour-River/10-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/11-Lynn_n_Seymour_Canyon_Loop.jpg' }, { src: 'img/20200621-Lynn-Creek-n-Seymour-River/12-Lynn_n_Seymour_Canyon_Loop.jpg' },
      ],
      list24: [
        { src: 'img/20200628NorvanFalls/01-NorvanFalls.jpg' }, { src: 'img/20200628NorvanFalls/02-NorvanFalls.jpg' }, { src: 'img/20200628NorvanFalls/03-NorvanFalls.jpg' },
        { src: 'img/20200628NorvanFalls/04-NorvanFalls.jpg' }, { src: 'img/20200628NorvanFalls/05-NorvanFalls.jpg' }, { src: 'img/20200628NorvanFalls/06-NorvanFalls.jpg' },
        { src: 'img/20200628NorvanFalls/07-NorvanFalls.jpg' },
      ],
      list25: [
        { src: 'img/20200705SmokeBluffsNMamquamRiver/01-Smoke.jpg' }, { src: 'img/20200705SmokeBluffsNMamquamRiver/02-Smoke.jpg' }, { src: 'img/20200705SmokeBluffsNMamquamRiver/03-Smoke.jpg' },
        { src: 'img/20200705SmokeBluffsNMamquamRiver/04-Smoke.jpg' }, { src: 'img/20200705SmokeBluffsNMamquamRiver/05-Smoke.jpg' }, { src: 'img/20200705SmokeBluffsNMamquamRiver/06-Smoke.jpg' },
        { src: 'img/20200705SmokeBluffsNMamquamRiver/07-Smoke.jpg' }, { src: 'img/20200705SmokeBluffsNMamquamRiver/08-Smoke.jpg' }, { src: 'img/20200705SmokeBluffsNMamquamRiver/09-Smoke.jpg' },
        { src: 'img/20200705SmokeBluffsNMamquamRiver/10-Smoke.jpg' },
      ],
      list26: [
        { src: 'img/20200712BrothersCreek/01-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/02-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/03-Brothers_Creek.jpg' },
        { src: 'img/20200712BrothersCreek/04-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/05-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/06-Brothers_Creek.jpg' },
        { src: 'img/20200712BrothersCreek/07-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/08-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/09-Brothers_Creek.jpg' },
        { src: 'img/20200712BrothersCreek/10-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/11-Brothers_Creek.jpg' }, { src: 'img/20200712BrothersCreek/12-Brothers_Creek.jpg' },
      ],
      list27: [
        { src: 'img/20200802WhyteLake/01-Whyte_Lake.jpg' }, { src: 'img/20200802WhyteLake/02-Whyte_Lake.jpg' }, { src: 'img/20200802WhyteLake/03-Whyte_Lake.jpg' },
        { src: 'img/20200802WhyteLake/04-Whyte_Lake.jpg' }, { src: 'img/20200802WhyteLake/05-Whyte_Lake.jpg' }, { src: 'img/20200802WhyteLake/06-Whyte_Lake.jpg' },
        { src: 'img/20200802WhyteLake/07-Whyte_Lake.jpg' }, { src: 'img/20200802WhyteLake/08-Whyte_Lake.jpg' }, { src: 'img/20200802WhyteLake/09-Whyte_Lake.jpg' },
      ],
      list28: [
        { src: 'img/20200809MinnekhadaRP/01-Minnekhada.jpg' }, { src: 'img/20200809MinnekhadaRP/02-Minnekhada.jpg' }, { src: 'img/20200809MinnekhadaRP/03-Minnekhada.jpg' },
        { src: 'img/20200809MinnekhadaRP/04-Minnekhada.jpg' }, { src: 'img/20200809MinnekhadaRP/05-Minnekhada.jpg' }, { src: 'img/20200809MinnekhadaRP/06-Minnekhada.jpg' },
        { src: 'img/20200809MinnekhadaRP/07-Minnekhada.jpg' }, { src: 'img/20200809MinnekhadaRP/08-Minnekhada.jpg' }, { src: 'img/20200809MinnekhadaRP/09-Minnekhada.jpg' },
        { src: 'img/20200809MinnekhadaRP/10-Minnekhada.jpg' },
      ],
      list29: [
        { src: 'img/20200816TyneheadRP/01-IMG_Tynehead.jpg' }, { src: 'img/20200816TyneheadRP/02-IMG_Tynehead.jpg' }, { src: 'img/20200816TyneheadRP/03-IMG_Tynehead.jpg' },
        { src: 'img/20200816TyneheadRP/04-IMG_Tynehead.jpg' }, { src: 'img/20200816TyneheadRP/05-IMG_Tynehead.jpg' }, { src: 'img/20200816TyneheadRP/06-IMG_Tynehead.jpg' },
        { src: 'img/20200816TyneheadRP/07-IMG_Tynehead.jpg' }, { src: 'img/20200816TyneheadRP/08-IMG_Tynehead.jpg' },
      ],
      list30: [
        { src: 'img/20200823CheakamusCanyon/01-Cheakamus.jpg' }, { src: 'img/20200823CheakamusCanyon/02-Cheakamus.jpg' }, { src: 'img/20200823CheakamusCanyon/03-Cheakamus.jpg' },
        { src: 'img/20200823CheakamusCanyon/04-Cheakamus.jpg' }, { src: 'img/20200823CheakamusCanyon/05-Cheakamus.jpg' }, { src: 'img/20200823CheakamusCanyon/06-Cheakamus.jpg' },
      ],
      list32: [
        { src: 'img/20200830Greendrop/01-Greendrop.jpg' }, { src: 'img/20200830Greendrop/02-Greendrop.jpg' }, { src: 'img/20200830Greendrop/03-Greendrop.jpg' },
        { src: 'img/20200830Greendrop/04-Greendrop.jpg' }, { src: 'img/20200830Greendrop/05-Greendrop.jpg' },
      ],
      list31: [
        { src: 'img/20200906HistoricMushroom/1-Historic_Mushroom.jpg' }, { src: 'img/20200906HistoricMushroom/2-Historic_Mushroom.jpg' }, { src: 'img/20200906HistoricMushroom/3-Historic_Mushroom.jpg' },
        { src: 'img/20200906HistoricMushroom/4-Historic_Mushroom.jpg' }, { src: 'img/20200906HistoricMushroom/5-Historic_Mushroom.jpg' }, { src: 'img/20200906HistoricMushroom/6-Historic_Mushroom.jpg' },
        { src: 'img/20200906HistoricMushroom/7-Historic_Mushroom.jpg' }, { src: 'img/20200906HistoricMushroom/8-Historic_Mushroom.jpg' },
      ],
      list33: [
        { src: 'img/20200920Sumas/01-Sumas-bike.jpg' }, { src: 'img/20200920Sumas/02-Sumas-bike.jpg' }, { src: 'img/20200920Sumas/03-Sumas-bike.jpg' },
        { src: 'img/20200920Sumas/04-Sumas-bike.jpg' }, { src: 'img/20200920Sumas/05-Sumas-bike.jpg' }, { src: 'img/20200920Sumas/06-Sumas-bike.jpg' },
        { src: 'img/20200920Sumas/07-Sumas-bike.jpg' },
      ],
      list34: [
        { src: 'img/20200927BuntzenToSasamatLake/01-Buntzen.jpg' }, { src: 'img/20200927BuntzenToSasamatLake/02-Buntzen.jpg' }, { src: 'img/20200927BuntzenToSasamatLake/03-Buntzen.jpg' },
        { src: 'img/20200927BuntzenToSasamatLake/04-Buntzen.jpg' }, { src: 'img/20200927BuntzenToSasamatLake/05-Buntzen.jpg' }, { src: 'img/20200927BuntzenToSasamatLake/06-Buntzen.jpg' },
      ],
      list35: [
        { src: 'img/20201004UBCRForest/01-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/02-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/03-M_Knapp_Research_Forest.jpg' },
        { src: 'img/20201004UBCRForest/04-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/05-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/06-M_Knapp_Research_Forest.jpg' },
        { src: 'img/20201004UBCRForest/07-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/08-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/09-M_Knapp_Research_Forest.jpg' },
        { src: 'img/20201004UBCRForest/10-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/11-M_Knapp_Research_Forest.jpg' }, { src: 'img/20201004UBCRForest/12-M_Knapp_Research_Forest.jpg' },
      ],
      list36: [
        { src: 'img/20201018CampbellValley/00-CampbellValley.jpg' }, { src: 'img/20201018CampbellValley/01-CampbellValley.jpg' }, { src: 'img/20201018CampbellValley/02-CampbellValley.jpg' },
        { src: 'img/20201018CampbellValley/03-CampbellValley.jpg' },
      ],
      list37: [
        { src: 'img/20201025GoldCreekCanyon/01-GoldCreekCanyon.jpg' }, { src: 'img/20201025GoldCreekCanyon/02-GoldCreekCanyon.jpg' }, { src: 'img/20201025GoldCreekCanyon/03-GoldCreekCanyon.jpg' },
        { src: 'img/20201025GoldCreekCanyon/04-GoldCreekCanyon.jpg' }, { src: 'img/20201025GoldCreekCanyon/05-GoldCreekCanyon.jpg' }, { src: 'img/20201025GoldCreekCanyon/06-GoldCreekCanyon.jpg' },
        { src: 'img/20201025GoldCreekCanyon/07-GoldCreekCanyon.jpg' }, { src: 'img/20201025GoldCreekCanyon/08-GoldCreekCanyon.jpg' }, { src: 'img/20201025GoldCreekCanyon/09-GoldCreekCanyon.jpg' },
      ],
      list38: [
        { src: 'img/20201101FishermansTrail/01-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/02-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/03-FishermansTrail.jpg' },
        { src: 'img/20201101FishermansTrail/04-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/05-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/06-FishermansTrail.jpg' },
        { src: 'img/20201101FishermansTrail/07-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/08-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/09-FishermansTrail.jpg' },
        { src: 'img/20201101FishermansTrail/10-FishermansTrail.jpg' }, { src: 'img/20201101FishermansTrail/11-FishermansTrail.jpg' },
      ],
      list39: [
        { src: 'img/20201108HaywardLake/01-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/02-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/03-Hayward_Lake_Reservoir.jpg' },
        { src: 'img/20201108HaywardLake/04-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/05-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/06-Hayward_Lake_Reservoir.jpg' },
        { src: 'img/20201108HaywardLake/07-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/08-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/09-Hayward_Lake_Reservoir.jpg' },
        { src: 'img/20201108HaywardLake/10-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/11-Hayward_Lake_Reservoir.jpg' }, { src: 'img/20201108HaywardLake/12-Hayward_Lake_Reservoir.jpg' },
      ],
      list40: [
        { src: 'img/20210314Buntzen/1-Buntzen_Lake.jpg' }, { src: 'img/20210314Buntzen/2-Buntzen_Lake.jpg' }, { src: 'img/20210314Buntzen/3-Buntzen_Lake.jpg' },
        { src: 'img/20210314Buntzen/4-Buntzen_Lake.jpg' }, { src: 'img/20210314Buntzen/5-Buntzen_Lake.jpg' }, { src: 'img/20210314Buntzen/6-Buntzen_Lake.jpg' },
        { src: 'img/20210314Buntzen/7-Buntzen_Lake.jpg' }, { src: 'img/20210314Buntzen/8-Buntzen_Lake.jpg' }, 
      ],
      list41: [
        { src: 'img/20210325BrohmLake/01-BrohmLake.jpg' }, { src: 'img/20210325BrohmLake/02-BrohmLake.jpg' }, { src: 'img/20210325BrohmLake/03-BrohmLake.jpg' },
        { src: 'img/20210325BrohmLake/04-BrohmLake.jpg' }, 
      ],
      list42: [
        { src: 'img/20210404TransCanadaTrail/01-IMG_7648.jpg' }, { src: 'img/20210404TransCanadaTrail/02-IMG_7649.jpg' }, { src: 'img/20210404TransCanadaTrail/03-IMG_7650.jpg' },
        { src: 'img/20210404TransCanadaTrail/04-IMG_7651.jpg' }, { src: 'img/20210404TransCanadaTrail/05-IMG_7652.jpg' }, { src: 'img/20210404TransCanadaTrail/06-IMG_7654.jpg' },
        { src: 'img/20210404TransCanadaTrail/07-IMG_7655.jpg' }, { src: 'img/20210404TransCanadaTrail/08-IMG_7656.jpg' }, { src: 'img/20210404TransCanadaTrail/09-IMG_7658.jpg' },
      ],
      list43: [
        { src: 'img/20210411Fisherman/01-Fisherman.jpg' }, { src: 'img/20210411Fisherman/02-Fisherman.jpg' }, { src: 'img/20210411Fisherman/03-Fisherman.jpg' },
        { src: 'img/20210411Fisherman/04-Fisherman.jpg' }, { src: 'img/20210411Fisherman/05-Fisherman.jpg' }, { src: 'img/20210411Fisherman/06-Fisherman.jpg' },
        { src: 'img/20210411Fisherman/07-Fisherman.jpg' }, 
      ],
      list44: [
        { src: 'img/20210418ChadseyLake/01-Chadsey-Lake.jpg' }, { src: 'img/20210418ChadseyLake/02-Chadsey-Lake.jpg' }, { src: 'img/20210418ChadseyLake/03-Chadsey-Lake.jpg' },
        { src: 'img/20210418ChadseyLake/04-Chadsey-Lake.jpg' }, { src: 'img/20210418ChadseyLake/05-Chadsey-Lake.jpg' }, { src: 'img/20210418ChadseyLake/06-Chadsey-Lake.jpg' },
        { src: 'img/20210418ChadseyLake/07-Chadsey-Lake.jpg' }, 
      ],
      list45: [
        { src: 'img/20210508Minnekhada/01-Minnekhada.jpg' }, { src: 'img/20210508Minnekhada/02-Minnekhada.jpg' }, { src: 'img/20210508Minnekhada/03-Minnekhada.jpg' },
        { src: 'img/20210508Minnekhada/04-Minnekhada.jpg' }, { src: 'img/20210508Minnekhada/05-Minnekhada.jpg' }, { src: 'img/20210508Minnekhada/06-Minnekhada.jpg' },
        { src: 'img/20210508Minnekhada/07-Minnekhada.jpg' }, { src: 'img/20210508Minnekhada/08-Minnekhada.jpg' }, { src: 'img/20210508Minnekhada/09-Minnekhada.jpg' },
        { src: 'img/20210508Minnekhada/10-Minnekhada.jpg' },
      ],
      list46: [
        { src: 'img/20210523WhiteLake/1-Whyte_Lake.jpg' }, { src: 'img/20210523WhiteLake/2-Whyte_Lake.jpg' }, { src: 'img/20210523WhiteLake/3-Whyte_Lake.jpg' },
        { src: 'img/20210523WhiteLake/4-Whyte_Lake.jpg' }, { src: 'img/20210523WhiteLake/5-Whyte_Lake.jpg' }, { src: 'img/20210523WhiteLake/6-Whyte_Lake.jpg' },
        { src: 'img/20210523WhiteLake/7-Whyte_Lake.jpg' }, { src: 'img/20210523WhiteLake/8-Whyte_Lake.jpg' }, 
      ],
      list47: [
        { src: 'img/20213005Shoreline/01-Shoreline.jpg' }, { src: 'img/20213005Shoreline/02-Shoreline.jpg' }, { src: 'img/20213005Shoreline/03-Shoreline.jpg' },
        { src: 'img/20213005Shoreline/04-Shoreline.jpg' }, { src: 'img/20213005Shoreline/05-Shoreline.jpg' }, { src: 'img/20213005Shoreline/06-Shoreline.jpg' },
        { src: 'img/20213005Shoreline/07-Shoreline.jpg' }, { src: 'img/20213005Shoreline/08-Shoreline.jpg' }, 
      ],
      list48: [
        { src: 'img/20210606Poco/01-Poco.jpg' }, { src: 'img/20210606Poco/02-Poco.jpg' }, { src: 'img/20210606Poco/03-Poco.jpg' },
        { src: 'img/20210606Poco/04-Poco.jpg' }, { src: 'img/20210606Poco/05-Poco.jpg' }, { src: 'img/20210606Poco/06-Poco.jpg' },
        { src: 'img/20210606Poco/07-Poco.jpg' }, { src: 'img/20210606Poco/08-Poco.jpg' }, 
      ],
      list49: [
        { src: 'img/20210701CrescentBeach/01-Crescent.jpg' }, { src: 'img/20210701CrescentBeach/02-Crescent.jpg' }, { src: 'img/20210701CrescentBeach/03-Crescent.jpg' },
        { src: 'img/20210701CrescentBeach/04-Crescent.jpg' }, { src: 'img/20210701CrescentBeach/05-Crescent.jpg' }, { src: 'img/20210701CrescentBeach/06-Crescent.jpg' },
        { src: 'img/20210701CrescentBeach/07-Crescent.jpg' }, { src: 'img/20210701CrescentBeach/08-Crescent.jpg' }, { src: 'img/20210701CrescentBeach/09-Crescent.jpg' },
        { src: 'img/20210701CrescentBeach/10-Crescent.jpg' },
      ],
      list50: [
        { src: 'img/20210705BuntzenLake/01-Buntzen.jpg' }, { src: 'img/20210705BuntzenLake/02-Buntzen.jpg' }, { src: 'img/20210705BuntzenLake/03-Buntzen.jpg' },
        { src: 'img/20210705BuntzenLake/04-Buntzen.jpg' }, { src: 'img/20210705BuntzenLake/05-Buntzen.jpg' }, { src: 'img/20210705BuntzenLake/06-Buntzen.jpg' },
        { src: 'img/20210705BuntzenLake/07-Buntzen.jpg' }, 
      ],
      list51: [
        { src: 'img/20210711YewBlackMnt/1-Black_Mountain.jpg' }, { src: 'img/20210711YewBlackMnt/2-Black_Mountain.jpg' }, { src: 'img/20210711YewBlackMnt/3-Black_Mountain.jpg' },
        { src: 'img/20210711YewBlackMnt/4-Black_Mountain.jpg' }, { src: 'img/20210711YewBlackMnt/5-Black_Mountain.jpg' }, { src: 'img/20210711YewBlackMnt/6-Black_Mountain.jpg' },
        { src: 'img/20210711YewBlackMnt/7-Black_Mountain.jpg' }, { src: 'img/20210711YewBlackMnt/8-Black_Mountain.jpg' },
      ],
      list52: [
        { src: 'img/20210725MamquamRiver/1-Mamquam.jpg' }, { src: 'img/20210725MamquamRiver/2-Mamquam.jpg' }, { src: 'img/20210725MamquamRiver/3-Mamquam.jpg' },
        { src: 'img/20210725MamquamRiver/4-Mamquam.jpg' }, { src: 'img/20210725MamquamRiver/5-Mamquam.jpg' }, { src: 'img/20210725MamquamRiver/6-Mamquam.jpg' },
        { src: 'img/20210725MamquamRiver/7-Mamquam.jpg' }, { src: 'img/20210725MamquamRiver/8-Mamquam.jpg' },
      ],
      list0: [
        { src: 'img/BOC-Newsletter.jpg' }, 
      ]
    }
  },
  methods: {
    toBocHome() {
      location.href = 'http://www.burnabyoutdoor.com'
    },
    beforeEnter(el) {
      console.log('beforeEnter');
      this.elementWidth = 400;
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
      this.elementWidth = 400;
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
