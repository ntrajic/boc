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
                              Take a leap of faith and begin this wondrous New year 2023 by believing!
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

      <div class="subtitle">Aldergrove Regional Park & Serpentine Fen, April 23, 2023
        <a class="vue-green" href="img/20230423Ald/20230423AldTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group124
          class="thumbnail"
          v-for="img in list124"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Buntzen Lake to Sasamat Lake, April 15th, 2023
        <a class="vue-green" href="img/20230415Buntzen/20230415BunTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group123
          class="thumbnail"
          v-for="img in list123"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Coquitlam Crunch and Shoreline Trail, April 7th, 2023
        <a class="vue-green" href="img/20230407Coq/20230407CoqTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group122
          class="thumbnail"
          v-for="img in list122"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Indian Arm Parks, North Van., March 26, 2023
        <a class="vue-green" href="img/20230326IndArm/20230326indarmTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group121
          class="thumbnail"
          v-for="img in list121"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Reifel Bird Sanctuary, Delta, and West Dyke Trail, Richmond, March 18, 2023
        <a class="vue-green" href="img/20230318Reifel/20230318ReifelTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group120
          class="thumbnail"
          v-for="img in list120"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Burnaby Mountain area to Port Moody, March 12, 2023
        <a class="vue-green" href="img/20230312BbyMnt/20230312BbyMntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group119
          class="thumbnail"
          v-for="img in list119"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Black Mnt Snowshoe Hike, March 04, 2023
        <a class="vue-green" href="img/20230304Black/20230304BlackTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group118
          class="thumbnail"
          v-for="img in list118"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Seymour River & Lynn Creek Hike, February 18, 2023
        <a class="vue-green" href="img/20230218Lynn/20230218LynnTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group117
          class="thumbnail"
          v-for="img in list117"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Mt Seymour-Dinkey Peak an First Lake Snowshoe Hike, February 12, 2023
        <a class="vue-green" href="img/20230212Dinkey/20230212DinkeyTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group116
          class="thumbnail"
          v-for="img in list116"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Mosquito & Mahon Creeks, February 5, 2023
        <a class="vue-green" href="img/20230205Mosquito/20230205MosquitoTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group115
          class="thumbnail"
          v-for="img in list115"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Vancouver’s Seawall & Seaside (English Bay, Science World), January 29, 2023
        <a class="vue-green" href="img/20230129Seawall/20230129SeawallTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group114
          class="thumbnail"
          v-for="img in list114"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Campbell Valley Regional Park, January 22nd, 2023
        <a class="vue-green" href="img/20230122Campbell/20230122CampbellTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group113
          class="thumbnail"
          v-for="img in list113"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Buntzen Lakeview Trail Hike, January 21st, 2023
        <a class="vue-green" href="img/20230121Buntzen/20230121BuntzenTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group112
          class="thumbnail"
          v-for="img in list112"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Bowen Lookout, January 15th, 2023
        <a class="vue-green" href="img/20230115Bowen/20230115BowenTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group111
          class="thumbnail"
          v-for="img in list111"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Poco Trail, January 7th, 2023
        <a class="vue-green" href="img/20230107Poco/20230107PocoTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group110
          class="thumbnail"
          v-for="img in list110"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Barnet Marine Park, Polar Bear Walk & Swim, January 1st, 2023
        <a class="vue-green" href="img/20230101Barnet/20230101BarnetTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group109
          class="thumbnail"
          v-for="img in list109"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Burnaby Mountain Walk, December 26th, 2022
        <a class="vue-green" href="img/20221226bbymnt/20221226bbymntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group108
          class="thumbnail"
          v-for="img in list108"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Burnaby Lake Walk, December 3rd, 2022
        <a class="vue-green" href="img/202212033BbyLake/20221203BbyLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group107
          class="thumbnail"
          v-for="img in list107"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Lynn Creek and Seymour River, November 27th, 2022
        <a class="vue-green" href="img/20221127Lynn/20221127LynnTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group106
          class="thumbnail"
          v-for="img in list106"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Knoll, Nicomekl and Redwood Parks, November 20th, 2022
        <a class="vue-green" href="img/20221120Knoll/20221120KnollTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group105
          class="thumbnail"
          v-for="img in list105"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Woodhaven Swamp to Sasamat Lake, November 13th, 2022
        <a class="vue-green" href="img/20221113Wood/20221113WoodTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group104
          class="thumbnail"
          v-for="img in list104"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Burnaby Mountain Loop, Friday, November 11th, 2022
        <a class="vue-green" href="img/20221111BbyMnt/20221111BbyMntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group103
          class="thumbnail"
          v-for="img in list103"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Norvan Falls, Lynn Headwaters & Cedars Mill, November 05, 2022
        <a class="vue-green" href="img/20221105Norvan/20221105NorvanTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group102
          class="thumbnail"
          v-for="img in list102"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Killarney Lake and Dorman Point, Bowen Island, October 22, 2022
        <a class="vue-green" href="img/20221022Dorman/20221022DormanTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group101
          class="thumbnail"
          v-for="img in list101"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Caulfeild Trail & Lighthouse Park, October 15, 2022
        <a class="vue-green" href="img/20221015Caul/20221015CaulTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group100
          class="thumbnail"
          v-for="img in list100"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Belcarra Park - Jug Island, October 10, 2022
        <a class="vue-green" href="img/20221010Jug/20221010jugTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group99
          class="thumbnail"
          v-for="img in list99"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Hollyburn Peak Hike,October 1, 2022
        <a class="vue-green" href="img/20221001Holly/20221001HollyTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group98
          class="thumbnail"
          v-for="img in list98"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Mount Seymour, Peaks 1 and 2, September 25, 2022
        <a class="vue-green" href="img/20220925Peaks/20220925PeaksTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group97
          class="thumbnail"
          v-for="img in list97"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">BOC 30th Anniversary BBQ, Buntzen Lake, Sep 17, 2022
        <a class="vue-green" href="img/20220917BOC30thAnniversary/20220917BOC30thAnniversaryTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group96
          class="thumbnail"
          v-for="img in list96"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Mystery Falls and Historic Mushroom, Sep 04, 2022
        <a class="vue-green" href="img/20220904Mistery/20220904MisteryTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group95
          class="thumbnail"
          v-for="img in list95"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">St. Mark's Summit hike, Aug 27, 2022
        <a class="vue-green" href="img/20220827StMark/20220827StMarkTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group94
          class="thumbnail"
          v-for="img in list94"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Dog Mountain & Suicide Bluffs hike, Aug 21, 2022
        <a class="vue-green" href="img/20220822Dog/20220821DogTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group93
          class="thumbnail"
          v-for="img in list93"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Tynehead Regional Park, Surrey Lake & Fleetwood Park -- August 14, 2022
        <a class="vue-green" href="img/20220814Tynehead/20220814TyneheadTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group92
          class="thumbnail"
          v-for="img in list92"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Elfin Lakes, August 9, 2022
        <a class="vue-green" href="img/20220809Elfin/20220809ElfinTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group91
          class="thumbnail"
          v-for="img in list91"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Mt Gardner Bowen Island - July 31, 2022
        <a class="vue-green" href="img/20220731MntGardner/20220731MntGardnerTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group90
          class="thumbnail"
          v-for="img in list90"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Black Mountain & Eagle Bluffs, July 17, 2022
        <a class="vue-green" href="img/20220717EagleBluffs/20220717EagleTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group89
          class="thumbnail"
          v-for="img in list89"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Hollyburn Four Lakes Hike, July 10, 2022
        <a class="vue-green" href="img/20220710FourLakes/20220710FourLakesTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group88
          class="thumbnail"
          v-for="img in list88"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Elk Mountain, July 01, 2022
        <a class="vue-green" href="img/20220701ElkMnt/2020701ElkMntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group87
          class="thumbnail"
          v-for="img in list87"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Brohm Lake Hike, June 26, 2022
        <a class="vue-green" href="img/20220626Brohm/20220626BrohmTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group86
          class="thumbnail"
          v-for="img in list86"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Boundary Bay Regional Park & Dyke, June 19, 2022
        <a class="vue-green" href="img/20220619Dyke/20220619DykeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group85
          class="thumbnail"
          v-for="img in list85"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Golden Ears, East and West Canyon Trails - loop hike, June 12, 2022
        <a class="vue-green" href="img/20220612GoldenEars/20220612GoldenEarsTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group84
          class="thumbnail"
          v-for="img in list84"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">The Seymour River Lynn Canyon Loop, June 04, 2022
        <a class="vue-green" href="img/20220604Lynn/20220604LynnTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group83
          class="thumbnail"
          v-for="img in list83"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Whistler Train Wreck and Cheakamus River hike, May 29, 2022
        <a class="vue-green" href="img/20220529Whistler/20220529WhistlerTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group82
          class="thumbnail"
          v-for="img in list82"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Norvan Falls, May 22, 2022
        <a class="vue-green" href="img/20220522NorVan/20220522NorVanTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group81
          class="thumbnail"
          v-for="img in list81"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Soames Hill and Gibsons, May 8, 2022
        <a class="vue-green" href="img/20220508Hill/20220508HillTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group80
          class="thumbnail"
          v-for="img in list80"
          :src="img.src"
          :key="img.src">
      </div>
      <!-- <div> 79 is already used </div> -->
      <div class="subtitle">Crescent Beach Walk, May 1, 2022
        <a class="vue-green" href="img/20220501CrescentBeach/20220501CrescentBeachTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group78
          class="thumbnail"
          v-for="img in list78"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Cypress Falls and Whyte Lake, April 24, 2022
        <a class="vue-green" href="img/20220422CypressFallWhyteLake/20220424CypressFallWhyteLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group77
          class="thumbnail"
          v-for="img in list77"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Butnzen and Sasamat Lake, April 15, 2022
        <a class="vue-green" href="img/20220415BuntzenSasamat/20220415BuntzenTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group79
          class="thumbnail"
          v-for="img in list79"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Hayward Lake, April 10, 2022
        <a class="vue-green" href="img/20220410HywardLake/20220410HywardLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group76
          class="thumbnail"
          v-for="img in list76"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Coquitlam Crunch, April 03, 2022
        <a class="vue-green" href="img/20020403Coquitlam/CoquitlamCrunchTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group75
          class="thumbnail"
          v-for="img in list75"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Woodhaven Swamp and Sasamat Lake, March 20, 2022
        <a class="vue-green" href="img/20220320Woodhaven/20220320WoodhavenTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group74
          class="thumbnail"
          v-for="img in list74"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Burnaby Mountain, March 13, 2022
        <a class="vue-green" href="img/20220313BbyMnt/20220313BbyMntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group73
          class="thumbnail"
          v-for="img in list73"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Mount Seymour, Brockton Point, March 6, 2022
        <a class="vue-green" href="img/20220306MntSeymour/20220306MntSeymourTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group72
          class="thumbnail"
          v-for="img in list72"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Indian Arm Parks, North Van, February 21, 2022
        <a class="vue-green" href="img/20220221IndianArm/20220222IndianArmTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group71
          class="thumbnail"
          v-for="img in list71"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">New Westiminster Quay, Edmonds, February 12, 2022
        <a class="vue-green" href="img/20220212NewWest/20220212NewWestTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group70
          class="thumbnail"
          v-for="img in list70"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Black Mountain, Cypress, February 06, 2022
        <a class="vue-green" href="img/20220206BlackMnt/20220206BlackMntTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group69
          class="thumbnail"
          v-for="img in list69"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Polar Bear Lunar New Year Event, February 01, 2022
        <a class="vue-green" href="img/20220201PolarBearLunar/20220201PolarTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group68
          class="thumbnail"
          v-for="img in list68"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Lynn Loop and Headwaters/Rice Lake, January 29th, 2022
        <a class="vue-green" href="img/20220129LynnLoop/20220129LynnLoopTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group67
          class="thumbnail"
          v-for="img in list67"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Bowen Lookout, January 16th, 2022
        <a class="vue-green" href="img/20220116Bowen/20220116BowenTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group66
          class="thumbnail"
          v-for="img in list66"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Vancouver Downtown's Seawall Walk, II, January 9th, 2022
        <a class="vue-green" href="img/20220109SeaWall/20220109SeaWallTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group65
          class="thumbnail"
          v-for="img in list65"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Vancouver Downtown's Seawall Walk, December 19th, 2021
        <a class="vue-green" href="img/20211219SeaWall/20211213SeaWallWalkTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group64
          class="thumbnail"
          v-for="img in list64"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Lynn Canyon and Seymour River Trails, December 05th, 2021
        <a class="vue-green" href="img/20211205LynnSeymour/20211205LynnSeymourTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group63
          class="thumbnail"
          v-for="img in list63"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Sasamat Lake to Diez Vistas, November 21st, 2021
        <a class="vue-green" href="img/20211121SasamtDiezVista/20211121SasamatDiezVistaTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group62
          class="thumbnail"
          v-for="img in list62"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Killarney Lake and Dorman Point, Bowen Island, October 31st, 2021
        <a class="vue-green" href="img/20211031KLDPBowen/20211031KLDPBowenTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group61
          class="thumbnail"
          v-for="img in list61"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Historic Mushroom Hike, October 26th, 2021
        <a class="vue-green" href="img/20211026HistoricMushroom/20211026HistoricMushroomTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group60
          class="thumbnail"
          v-for="img in list60"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Elgin Heritage Park and SunnySide Acres Urban Forest, October 11th, 2021
        <a class="vue-green" href="img/20211011ElginHeritage/20211011ElginHeritageTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group59
          class="thumbnail"
          v-for="img in list59"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Hollyburn Peak, October 03rd, 2021
        <a class="vue-green" href="img/20211003HollyburnPeak/20211003HollyburnTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group58
          class="thumbnail"
          v-for="img in list58"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Buntzen to Sasamat Lakes, September 12th, 2021
        <a class="vue-green" href="img/20210912BuntzenToSasamat/20210912BuntzenToSasamatTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group57
          class="thumbnail"
          v-for="img in list57"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Elfin Lakes, August 31st, 2021
        <a class="vue-green" href="img/20210831ElfinLakes/20210831ElfinLakesTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group56
          class="thumbnail"
          v-for="img in list56"
          :src="img.src"
          :key="img.src">
      </div>

      <div class="subtitle">Cypress Falls To Whyte Lake Trail, August 22nd, 2021
        <a class="vue-green" href="img/20210822CypressFallToWhyteLake/20210822CypressFallsToWhyteLakeTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group55
          class="thumbnail"
          v-for="img in list55"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">St Mark's Summit Hike, August 8th, 2021
        <a class="vue-green" href="img/20210808StMarksSummit/20210808StMarksSummitTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group54
          class="thumbnail"
          v-for="img in list54"
          :src="img.src"
          :key="img.src">
      </div>
      <div class="subtitle">Seymour River and Lynn Canyon Loop, August 2th, 2021
        <a class="vue-green" href="img/20210802SeymourRiverLynnCanyonLoop/20210802SeymourLynnTR.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group53
          class="thumbnail"
          v-for="img in list53"
          :src="img.src"
          :key="img.src">
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
        <i class="iconfont icon-github"></i>GoTo Burnabyoutdoor.com, 2019, 2020, 2021, 2022, 2023</footer>
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
      list53: [
        { src: 'img/20210802SeymourRiverLynnCanyonLoop/1-SeymourLynn.jpg' }, { src: 'img/20210802SeymourRiverLynnCanyonLoop/2-SeymourLynn.jpg' }, { src: 'img/20210802SeymourRiverLynnCanyonLoop/3-SeymourLynn.jpg' },
        { src: 'img/20210802SeymourRiverLynnCanyonLoop/4-SeymourLynn.jpg' }, { src: 'img/20210802SeymourRiverLynnCanyonLoop/5-SeymourLynn.jpg' }, { src: 'img/20210802SeymourRiverLynnCanyonLoop/6-SeymourLynn.jpg' },
      ],
      list54: [
        { src: 'img/20210808StMarksSummit/1-St_Marks_hike.jpg' }, { src: 'img/20210808StMarksSummit/2-St_Marks_hike.jpg' }, { src: 'img/20210808StMarksSummit/3-St_Marks_hike.jpg' },
        { src: 'img/20210808StMarksSummit/4-St_Marks_hike.jpg' }, { src: 'img/20210808StMarksSummit/5-St_Marks_hike.jpg' }, { src: 'img/20210808StMarksSummit/6-St_Marks_hike.jpg' },
        { src: 'img/20210808StMarksSummit/7-St_Marks_hike.jpg' }, { src: 'img/20210808StMarksSummit/8-St_Marks_hike.jpg' },
      ],
      list55: [
        { src: 'img/20210822CypressFallToWhyteLake/01-Cypress_Falls_To_Whyte_Lake.jpg' }, { src: 'img/20210822CypressFallToWhyteLake/02-Cypress_Falls_To_Whyte_Lake.jpg' }, { src: 'img/20210822CypressFallToWhyteLake/03-Cypress_Falls_To_Whyte_Lake.jpg' },
        { src: 'img/20210822CypressFallToWhyteLake/04-Cypress_Falls_To_Whyte_Lake.jpg' }, { src: 'img/20210822CypressFallToWhyteLake/05-Cypress_Falls_To_Whyte_Lake.jpg' }, { src: 'img/20210822CypressFallToWhyteLake/06-Cypress_Falls_To_Whyte_Lake.jpg' },
        { src: 'img/20210822CypressFallToWhyteLake/07-Cypress_Falls_To_Whyte_Lake.jpg' }, { src: 'img/20210822CypressFallToWhyteLake/08-Cypress_Falls_To_Whyte_Lake.jpg' }, { src: 'img/20210822CypressFallToWhyteLake/09-Cypress_Falls_To_Whyte_Lake.jpg' },
        { src: 'img/20210822CypressFallToWhyteLake/10-Cypress_Falls_To_Whyte_Lake.jpg' },
      ],
      list56: [
        { src: 'img/20210831ElfinLakes/01-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/02-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/03-Elfin_Lake.jpg' },
        { src: 'img/20210831ElfinLakes/04-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/05-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/06-Elfin_Lake.jpg' },
        { src: 'img/20210831ElfinLakes/07-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/08-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/09-Elfin_Lake.jpg' },
        { src: 'img/20210831ElfinLakes/10-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/11-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/12-Elfin_Lake.jpg' },
        { src: 'img/20210831ElfinLakes/13-Elfin_Lake.jpg' }, { src: 'img/20210831ElfinLakes/14-Elfin_Lake.jpg' },
      ],
      list57: [
        { src: 'img/20210912BuntzenToSasamat/01-Buntzen_to_Sasamat_Lakes.jpg' }, { src: 'img/20210912BuntzenToSasamat/02-Buntzen_to_Sasamat_Lakes.jpg' }, { src: 'img/20210912BuntzenToSasamat/03-Buntzen_to_Sasamat_Lakes.jpg' },
        { src: 'img/20210912BuntzenToSasamat/04-Buntzen_to_Sasamat_Lakes.jpg' }, { src: 'img/20210912BuntzenToSasamat/05-Buntzen_to_Sasamat_Lakes.jpg' }, { src: 'img/20210912BuntzenToSasamat/06-Buntzen_to_Sasamat_Lakes.jpg' },
        { src: 'img/20210912BuntzenToSasamat/07-Buntzen_to_Sasamat_Lakes.jpg' }, { src: 'img/20210912BuntzenToSasamat/08-Buntzen_to_Sasamat_Lakes.jpg' }, { src: 'img/20210912BuntzenToSasamat/09-Buntzen_to_Sasamat_Lakes.jpg' },
        { src: 'img/20210912BuntzenToSasamat/10-Buntzen_to_Sasamat_Lakes.jpg' },
      ],
      list58: [
        { src: 'img/20211003HollyburnPeak/01-Hollyburn_Peak.jpg' }, { src: 'img/20211003HollyburnPeak/02-Hollyburn_Peak.jpg' }, { src: 'img/20211003HollyburnPeak/03-Hollyburn_Peak.jpg' },
        { src: 'img/20211003HollyburnPeak/04-Hollyburn_Peak.jpg' }, { src: 'img/20211003HollyburnPeak/05-Hollyburn_Peak.jpg' }, { src: 'img/20211003HollyburnPeak/06-Hollyburn_Peak.jpg' },
        { src: 'img/20211003HollyburnPeak/07-Hollyburn_Peak.jpg' }, { src: 'img/20211003HollyburnPeak/08-Hollyburn_Peak.jpg' }, { src: 'img/20211003HollyburnPeak/09-Hollyburn_Peak.jpg' },
        { src: 'img/20211003HollyburnPeak/10-Hollyburn_Peak.jpg' },
      ],
      list59: [
        { src: 'img/20211011ElginHeritage/01-ElginHeritage.jpg' }, { src: 'img/20211011ElginHeritage/02-ElginHeritage.jpg' }, { src: 'img/20211011ElginHeritage/03-ElginHeritage.jpg' },
        { src: 'img/20211011ElginHeritage/04-ElginHeritage.jpg' }, { src: 'img/20211011ElginHeritage/05-ElginHeritage.jpg' }, { src: 'img/20211011ElginHeritage/06-ElginHeritage.jpg' },
        { src: 'img/20211011ElginHeritage/07-ElginHeritage.jpg' }, { src: 'img/20211011ElginHeritage/08-ElginHeritage.jpg' },
      ],
      list60: [
        { src: 'img/20211026HistoricMushroom/1-Historic_Mushroom.jpg' }, { src: 'img/20211026HistoricMushroom/2-Historic_Mushroom.jpg' }, { src: 'img/20211026HistoricMushroom/3-Historic_Mushroom.jpg' },
        { src: 'img/20211026HistoricMushroom/4-Historic_Mushroom.jpg' }, { src: 'img/20211026HistoricMushroom/5-Historic_Mushroom.jpg' }, { src: 'img/20211026HistoricMushroom/6-Historic_Mushroom.jpg' },
        { src: 'img/20211026HistoricMushroom/7-Historic_Mushroom.jpg' }, { src: 'img/20211026HistoricMushroom/8-Historic_Mushroom.jpg' },
      ],
      list61: [
        { src: 'img/20211031KLDPBowen/1-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/2-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/3-KLDPBowen.jpg' },
        { src: 'img/20211031KLDPBowen/4-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/5-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/6-KLDPBowen.jpg' },
        { src: 'img/20211031KLDPBowen/7-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/8-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/9-KLDPBowen.jpg' },
        { src: 'img/20211031KLDPBowen/10-KLDPBowen.jpg' }, { src: 'img/20211031KLDPBowen/11-KLDPBowen.jpg' },
      ],
      list62: [
        { src: 'img/20211121SasamtDiezVista/01-SasamatToDV.jpg' }, { src: 'img/20211121SasamtDiezVista/02-SasamatToDV.jpg' }, { src: 'img/20211121SasamtDiezVista/03-SasamatToDV.jpg' },
        { src: 'img/20211121SasamtDiezVista/04-SasamatToDV.jpg' }, { src: 'img/20211121SasamtDiezVista/05-SasamatToDV.jpg' }, { src: 'img/20211121SasamtDiezVista/06-SasamatToDV.jpg' },
        { src: 'img/20211121SasamtDiezVista/07-SasamatToDV.jpg' }, { src: 'img/20211121SasamtDiezVista/08-SasamatToDV.jpg' },
      ],
      list63: [
        { src: 'img/20211205LynnSeymour/01-Two_Canyon_Loop-Lynn_Creek.jpg' }, { src: 'img/20211205LynnSeymour/02-Two_Canyon_Loop-Lynn_Cteek.jpg' }, { src: 'img/20211205LynnSeymour/03-Two_Canyon_Loop-Lynn_Creek.jpg' },
        { src: 'img/20211205LynnSeymour/04-Two_Canyon_Loop-Lynn_Creek.jpg' }, { src: 'img/20211205LynnSeymour/05-Two_Canyon_Loop-Lynn_Creek.jpg' }, { src: 'img/20211205LynnSeymour/06-Two_Canyon_Loop-Lynn_Creek.jpg' },
        { src: 'img/20211205LynnSeymour/07-Two_Canyon_Loop-Lynn_Creek.jpg' }, { src: 'img/20211205LynnSeymour/08-Two_Canyon_Loop-Lynn_Creek.jpg' }, { src: 'img/20211205LynnSeymour/09-Two_Canyon_Loop-Lynn_Creek.jpg' },
        { src: 'img/20211205LynnSeymour/10-Two_Canyon_Loop-Lynn_Creek.jpg' },
      ],
      list64: [
        { src: 'img/20211219SeaWall/01-SeaWall.jpg' }, { src: 'img/20211219SeaWall/02-SeaWall.jpg' }, { src: 'img/20211219SeaWall/03-SeaWall.jpg' },
        { src: 'img/20211219SeaWall/04-SeaWall.jpg' }, { src: 'img/20211219SeaWall/05-SeaWall.jpg' }, { src: 'img/20211219SeaWall/06-SeaWall.jpg' },
        { src: 'img/20211219SeaWall/07-SeaWall.jpg' }, { src: 'img/20211219SeaWall/08-SeaWall.jpg' }, { src: 'img/20211219SeaWall/09-SeaWall.jpg' },
        { src: 'img/20211219SeaWall/10-SeaWall.jpg' }, { src: 'img/20211219SeaWall/11-SeaWall.jpg' }, { src: 'img/20211219SeaWall/12-SeaWall.jpg' },
      ],
      list65: [
        { src: 'img/20220109SeaWall/01-SeaWall.jpg' }, { src: 'img/20220109SeaWall/02-SeaWall.jpg' }, { src: 'img/20220109SeaWall/03-SeaWall.jpg' },
        { src: 'img/20220109SeaWall/04-SeaWall.jpg' }, { src: 'img/20220109SeaWall/05-SeaWall.jpg' }, { src: 'img/20220109SeaWall/06-SeaWall.jpg' },
        { src: 'img/20220109SeaWall/07-SeaWall.jpg' }, { src: 'img/20220109SeaWall/08-SeaWall.jpg' }, { src: 'img/20220109SeaWall/09-SeaWall.jpg' },
        { src: 'img/20220109SeaWall/10-SeaWall.jpg' }, { src: 'img/20220109SeaWall/11-SeaWall.jpg' }, { src: 'img/20220109SeaWall/12-SeaWall.jpg' },
        { src: 'img/20220109SeaWall/13-SeaWall.jpg' },
      ],
      list66: [
        { src: 'img/20220116Bowen/01-Bowen_Lookout.jpg' }, { src: 'img/20220116Bowen/02-Bowen_Lookout.jpg' }, { src: 'img/20220116Bowen/03-Bowen_Lookout.jpg' },
        { src: 'img/20220116Bowen/04-Bowen_Lookout.jpg' }, { src: 'img/20220116Bowen/05-Bowen_Lookout.jpg' }, { src: 'img/20220116Bowen/06-Bowen_Lookout.jpg' },
        { src: 'img/20220116Bowen/07-Bowen_Lookout.jpg' }, { src: 'img/20220116Bowen/08-Bowen_Lookout.jpg' },
      ],
      list67: [
        { src: 'img/20220129LynnLoop/01-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/02-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/03-LynnLoop.jpg' },
        { src: 'img/20220129LynnLoop/04-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/05-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/06-LynnLoop.jpg' },
        { src: 'img/20220129LynnLoop/07-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/08-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/09-LynnLoop.jpg' },
        { src: 'img/20220129LynnLoop/10-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/11-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/12-LynnLoop.jpg' },
        { src: 'img/20220129LynnLoop/13-LynnLoop.jpg' }, { src: 'img/20220129LynnLoop/14-LynnLoop.jpg' },
      ],
      list68: [
        { src: 'img/20220201PolarBearLunar/01-Polar.jpg' }, { src: 'img/20220201PolarBearLunar/02-Polar.jpg' }, { src: 'img/20220201PolarBearLunar/03-Polar.jpg' },
        { src: 'img/20220201PolarBearLunar/04-Polar.jpg' }, { src: 'img/20220201PolarBearLunar/05-Polar.jpg' },
      ],
      list69: [
        { src: 'img/20220206BlackMnt/01-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/02-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/03-Black_Mountain.jpg' },
        { src: 'img/20220206BlackMnt/04-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/05-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/06-Black_Mountain.jpg' },
        { src: 'img/20220206BlackMnt/07-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/08-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/09-Black_Mountain.jpg' },
        { src: 'img/20220206BlackMnt/10-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/11-Black_Mountain.jpg' }, { src: 'img/20220206BlackMnt/12-Black_Mountain.jpg' },
      ],
      list70: [
        { src: 'img/20220212NewWest/01-NewWest.jpg' }, { src: 'img/20220212NewWest/02-NewWest.jpg' }, { src: 'img/20220212NewWest/03-NewWest.jpg' },
        { src: 'img/20220212NewWest/04-NewWest.jpg' }, { src: 'img/20220212NewWest/05-NewWest.jpg' }, { src: 'img/20220212NewWest/06-NewWest.jpg' },
        { src: 'img/20220212NewWest/07-NewWest.jpg' }, { src: 'img/20220212NewWest/08-NewWest.jpg' }, { src: 'img/20220212NewWest/09-NewWest.jpg' },
        { src: 'img/20220212NewWest/10-NewWest.jpg' },
      ],
      list71: [
        { src: 'img/20220221IndianArm/01-IndianArm.jpg' }, { src: 'img/20220221IndianArm/02-IndianArm.jpg' }, { src: 'img/20220221IndianArm/03-IndianArm.jpg' },
        { src: 'img/20220221IndianArm/04-IndianArm.jpg' }, { src: 'img/20220221IndianArm/05-IndianArm.jpg' }, { src: 'img/20220221IndianArm/06-IndianArm.jpg' },
        { src: 'img/20220221IndianArm/07-IndianArm.jpg' }, { src: 'img/20220221IndianArm/08-IndianArm.jpg' }, { src: 'img/20220221IndianArm/09-IndianArm.jpg' },
        { src: 'img/20220221IndianArm/10-IndianArm.jpg' },
      ],
      list72: [
        { src: 'img/20220306MntSeymour/01-Mount_Seymour.jpg' }, { src: 'img/20220306MntSeymour/02-Mount_Seymour.jpg' }, { src: 'img/20220306MntSeymour/03-Mount_Seymour.jpg' },
        { src: 'img/20220306MntSeymour/04-Mount_Seymour.jpg' }, { src: 'img/20220306MntSeymour/05-Mount_Seymour.jpg' }, { src: 'img/20220306MntSeymour/06-Mount_Seymour.jpg' },
        { src: 'img/20220306MntSeymour/07-Mount_Seymour.jpg' }, { src: 'img/20220306MntSeymour/08-Mount_Seymour.jpg' }, { src: 'img/20220306MntSeymour/09-Mount_Seymour.jpg' },
        { src: 'img/20220306MntSeymour/10-Mount_Seymour.jpg' },
      ],
      list73: [
        { src: 'img/20220313BbyMnt/01-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/02-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/03-BbyMnt.jpg' },
        { src: 'img/20220313BbyMnt/04-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/05-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/06-BbyMnt.jpg' },
        { src: 'img/20220313BbyMnt/07-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/08-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/09-BbyMnt.jpg' },
        { src: 'img/20220313BbyMnt/10-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/11-BbyMnt.jpg' }, { src: 'img/20220313BbyMnt/12-BbyMnt.jpg' },
        { src: 'img/20220313BbyMnt/13-BbyMnt.jpg' },
      ],
      list74: [
        { src: 'img/20220320Woodhaven/01-Woodhaven_Swamp-Sasamt_Lake.jpg' }, { src: 'img/20220320Woodhaven/02-Woodhaven_Swamp-Sasamt_Lake.jpg' }, { src: 'img/20220320Woodhaven/03-Woodhaven_Swamp-Sasamt_Lake.jpg' },
        { src: 'img/20220320Woodhaven/04-Woodhaven_Swamp-Sasamt_Lake.jpg' }, { src: 'img/20220320Woodhaven/05-Woodhaven_Swamp-Sasamt_Lake.jpg' }, { src: 'img/20220320Woodhaven/06-Woodhaven_Swamp-Sasamt_Lake.jpg' },
        { src: 'img/20220320Woodhaven/07-Woodhaven_Swamp-Sasamt_Lake.jpg' }, { src: 'img/20220320Woodhaven/08-Woodhaven_Swamp-Sasamt_Lake.jpg' },
      ],
      list75: [
        { src: 'img/20020403Coquitlam/01-Crunch.jpg' }, { src: 'img/20020403Coquitlam/02-Crunch.jpg' }, { src: 'img/20020403Coquitlam/03-Crunch.jpg' },
        { src: 'img/20020403Coquitlam/04-Crunch.jpg' }, { src: 'img/20020403Coquitlam/05-Crunch.jpg' }, { src: 'img/20020403Coquitlam/06-Crunch.jpg' },
      ],
      list76: [
        { src: 'img/20220410HywardLake/01-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/02-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/03-Hayward_Lake.jpg' },
        { src: 'img/20220410HywardLake/04-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/05-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/06-Hayward_Lake.jpg' },
        { src: 'img/20220410HywardLake/07-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/08-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/09-Hayward_Lake.jpg' },
        { src: 'img/20220410HywardLake/10-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/11-Hayward_Lake.jpg' }, { src: 'img/20220410HywardLake/12-Hayward_Lake.jpg' },
      ],
      list77: [
        { src: 'img/20220422CypressFallWhyteLake/01-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/02-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/03-Cypress_Falls-Whyte_Lake.jpg' },
        { src: 'img/20220422CypressFallWhyteLake/04-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/05-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/06-Cypress_Falls-Whyte_Lake.jpg' },
        { src: 'img/20220422CypressFallWhyteLake/07-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/08-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/09-Cypress_Falls-Whyte_Lake.jpg' },
        { src: 'img/20220422CypressFallWhyteLake/10-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/11-Cypress_Falls-Whyte_Lake.jpg' }, { src: 'img/20220422CypressFallWhyteLake/12-Cypress_Falls-Whyte_Lake.jpg' },
      ],
      list78: [
        { src: 'img/20220501CrescentBeach/01-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/02-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/03-Crescent.jpg' },
        { src: 'img/20220501CrescentBeach/04-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/05-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/06-Crescent.jpg' },
        { src: 'img/20220501CrescentBeach/07-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/08-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/09-Crescent.jpg' },
        { src: 'img/20220501CrescentBeach/10-Crescent.jpg' }, { src: 'img/20220501CrescentBeach/11-Crescent.jpg' },
      ],
      list79: [
        { src: 'img/20220415BuntzenSasamat/01-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/02-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/03-Buntzen.jpg' },
        { src: 'img/20220415BuntzenSasamat/04-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/05-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/06-Buntzen.jpg' },
        { src: 'img/20220415BuntzenSasamat/07-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/08-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/09-Buntzen.jpg' },
        { src: 'img/20220415BuntzenSasamat/10-Buntzen.jpg' }, { src: 'img/20220415BuntzenSasamat/11-Buntzen.jpg' },
      ],
      list80: [
        { src: 'img/20220508Hill/01-Hill.jpg' }, { src: 'img/20220508Hill/02-Hill.jpg' }, { src: 'img/20220508Hill/03-Hill.jpg' },
        { src: 'img/20220508Hill/04-Hill.jpg' }, { src: 'img/20220508Hill/05-Hill.jpg' }, { src: 'img/20220508Hill/06-Hill.jpg' },
        { src: 'img/20220508Hill/07-Hill.jpg' }, { src: 'img/20220508Hill/08-Hill.jpg' }, { src: 'img/20220508Hill/09-Hill.jpg' },
        { src: 'img/20220508Hill/10-Hill.jpg' }, { src: 'img/20220508Hill/11-Hill.jpg' }, { src: 'img/20220508Hill/12-Hill.jpg' },
        { src: 'img/20220508Hill/13-Hill.jpg' }, { src: 'img/20220508Hill/14-Hill.jpg' }, { src: 'img/20220508Hill/15-Hill.jpg' },
        { src: 'img/20220508Hill/16-Hill.jpg' }, { src: 'img/20220508Hill/17-Hill.jpg' }, { src: 'img/20220508Hill/18-Hill.jpg' },
        { src: 'img/20220508Hill/19-Hill.jpg' }, { src: 'img/20220508Hill/20-Hill.jpg' }, { src: 'img/20220508Hill/21-Hill.jpg' },
        { src: 'img/20220508Hill/22-Hill.jpg' }, { src: 'img/20220508Hill/23-Hill.jpg' }, { src: 'img/20220508Hill/24-Hill.jpg' },
      ],
      list81: [
        { src: 'img/20220522NorVan/01-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/02-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/03-Norvan_Falls.jpg' },
        { src: 'img/20220522NorVan/04-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/05-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/06-Norvan_Falls.jpg' },
        { src: 'img/20220522NorVan/07-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/08-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/09-Norvan_Falls.jpg' },
        { src: 'img/20220522NorVan/10-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/11-Norvan_Falls.jpg' }, { src: 'img/20220522NorVan/12-Norvan_Falls.jpg' },
      ],
      list82: [
        { src: 'img/20220529Whistler/01-Whistler.jpg' }, { src: 'img/20220529Whistler/02-Whistler.jpg' }, { src: 'img/20220529Whistler/03-Whistler.jpg' },
        { src: 'img/20220529Whistler/04-Whistler.jpg' }, { src: 'img/20220529Whistler/05-Whistler.jpg' }, { src: 'img/20220529Whistler/06-Whistler.jpg' },
        { src: 'img/20220529Whistler/07-Whistler.jpg' }, { src: 'img/20220529Whistler/08-Whistler.jpg' }, { src: 'img/20220529Whistler/09-Whistler.jpg' },
        { src: 'img/20220529Whistler/10-Whistler.jpg' }, { src: 'img/20220529Whistler/11-Whistler.jpg' }, { src: 'img/20220529Whistler/12-Whistler.jpg' },
        { src: 'img/20220529Whistler/13-Whistler.jpg' }, { src: 'img/20220529Whistler/14-Whistler.jpg' },
      ],
      list83: [
        { src: 'img/20220604Lynn/01-Lynn.jpg' }, { src: 'img/20220604Lynn/02-Lynn.jpg' }, { src: 'img/20220604Lynn/03-Lynn.jpg' },
        { src: 'img/20220604Lynn/04-Lynn.jpg' }, { src: 'img/20220604Lynn/05-Lynn.jpg' }, { src: 'img/20220604Lynn/06-Lynn.jpg' },
        { src: 'img/20220604Lynn/07-Lynn.jpg' }, { src: 'img/20220604Lynn/08-Lynn.jpg' }, { src: 'img/20220604Lynn/09-Lynn.jpg' },
        { src: 'img/20220604Lynn/10-Lynn.jpg' }, { src: 'img/20220604Lynn/11-Lynn.jpg' }, { src: 'img/20220604Lynn/12-Lynn.jpg' },
        { src: 'img/20220604Lynn/13-Lynn.jpg' }, { src: 'img/20220604Lynn/14-Lynn.jpg' },
      ],
      list84: [
        { src: 'img/20220612GoldenEars/01-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/02-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/03-Golden_Ears_Gold_Creek.jpg' },
        { src: 'img/20220612GoldenEars/04-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/05-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/06-Golden_Ears_Gold_Creek.jpg' },
        { src: 'img/20220612GoldenEars/07-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/08-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/09-Golden_Ears_Gold_Creek.jpg' },
        { src: 'img/20220612GoldenEars/10-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/11-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/12-Golden_Ears_Gold_Creek.jpg' },
        { src: 'img/20220612GoldenEars/13-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/14-Golden_Ears_Gold_Creek.jpg' }, { src: 'img/20220612GoldenEars/15-Golden_Ears_Gold_Creek.jpg' },
        { src: 'img/20220612GoldenEars/16-Golden_Ears_Gold_Creek.jpg' },
      ],
      list85: [
        { src: 'img/20220619Dyke/01-Dyke.jpg' }, { src: 'img/20220619Dyke/02-Dyke.jpg' }, { src: 'img/20220619Dyke/03-Dyke.jpg' },
        { src: 'img/20220619Dyke/04-Dyke.jpg' }, { src: 'img/20220619Dyke/05-Dyke.jpg' }, { src: 'img/20220619Dyke/06-Dyke.jpg' },
        { src: 'img/20220619Dyke/07-Dyke.jpg' }, { src: 'img/20220619Dyke/08-Dyke.jpg' }, { src: 'img/20220619Dyke/09-Dyke.jpg' },
        { src: 'img/20220619Dyke/10-Dyke.jpg' }, { src: 'img/20220619Dyke/11-Dyke.jpg' },
      ],
      list86: [
        { src: 'img/20220626Brohm/01-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/02-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/03-Brohm_Lake.jpg' },
        { src: 'img/20220626Brohm/04-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/05-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/06-Brohm_Lake.jpg' },
        { src: 'img/20220626Brohm/07-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/08-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/09-Brohm_Lake.jpg' },
        { src: 'img/20220626Brohm/10-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/11-Brohm_Lake.jpg' }, { src: 'img/20220626Brohm/12-Brohm_Lake.jpg' },
      ],
      list87: [
        { src: 'img/20220701ElkMnt/01-ElkMnt.jpeg' }, { src: 'img/20220701ElkMnt/02-ElkMnt.jpeg' }, { src: 'img/20220701ElkMnt/03-ElkMnt.jpeg' },
        { src: 'img/20220701ElkMnt/04-ElkMnt.jpeg' }, { src: 'img/20220701ElkMnt/05-ElkMnt.jpeg' }, { src: 'img/20220701ElkMnt/06-ElkMnt.jpeg' },
      ],
      list88: [
        { src: 'img/20220710FourLakes/01-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/02-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/03-Hollyburn_4_Lakes.jpg' },
        { src: 'img/20220710FourLakes/04-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/05-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/06-Hollyburn_4_Lakes.jpg' },
        { src: 'img/20220710FourLakes/07-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/08-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/09-Hollyburn_4_Lakes.jpg' },
        { src: 'img/20220710FourLakes/10-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/11-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/12-Hollyburn_4_Lakes.jpg' },
        { src: 'img/20220710FourLakes/13-Hollyburn_4_Lakes.jpg' }, { src: 'img/20220710FourLakes/14-Hollyburn_4_Lakes.jpg' },
      ],
      list89: [
        { src: 'img/20220717EagleBluffs/01-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/02-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/03-Eagle.jpg' },
        { src: 'img/20220717EagleBluffs/04-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/05-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/06-Eagle.jpg' },
        { src: 'img/20220717EagleBluffs/07-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/08-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/09-Eagle.jpg' },
        { src: 'img/20220717EagleBluffs/10-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/11-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/12-Eagle.jpg' },
        { src: 'img/20220717EagleBluffs/13-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/14-Eagle.jpg' }, { src: 'img/20220717EagleBluffs/15-Eagle.jpg' },
      ],
      list90: [
        { src: 'img/20220731MntGardner/01-MntGardner.jpg' }, { src: 'img/20220731MntGardner/02-MntGardner.jpg' }, { src: 'img/20220731MntGardner/03-MntGardner.jpg' },
        { src: 'img/20220731MntGardner/04-MntGardner.jpg' }, { src: 'img/20220731MntGardner/05-MntGardner.jpg' }, { src: 'img/20220731MntGardner/06-MntGardner.jpg' },
        { src: 'img/20220731MntGardner/07-MntGardner.jpg' }, { src: 'img/20220731MntGardner/08-MntGardner.jpg' }, { src: 'img/20220731MntGardner/09-MntGardner.jpg' },
        { src: 'img/20220731MntGardner/10-MntGardner.jpg' }, { src: 'img/20220731MntGardner/11-MntGardner.jpg' }, { src: 'img/20220731MntGardner/12-MntGardner.jpg' },
      ],
      list91: [
        { src: 'img/20220809Elfin/00-image.jpg' },
        { src: 'img/20220809Elfin/01-image.jpg' }, { src: 'img/20220809Elfin/02-image.jpg' }, { src: 'img/20220809Elfin/03-image.jpg' },
        { src: 'img/20220809Elfin/04-image.jpg' }, { src: 'img/20220809Elfin/05-image.jpg' }, { src: 'img/20220809Elfin/06-image.jpg' },
        { src: 'img/20220809Elfin/07-image.jpg' }, { src: 'img/20220809Elfin/08-image.jpg' }, { src: 'img/20220809Elfin/09-image.jpg' },
        { src: 'img/20220809Elfin/10-image.jpg' }, { src: 'img/20220809Elfin/11-image.jpg' }, { src: 'img/20220809Elfin/12-image.jpg' },
      ],
      list92: [
        { src: 'img/20220814Tynehead/01-Tynehead.jpg' }, { src: 'img/20220814Tynehead/02-Tynehead.jpg' }, { src: 'img/20220814Tynehead/03-Tynehead.jpg' },
        { src: 'img/20220814Tynehead/04-Tynehead.jpg' }, { src: 'img/20220814Tynehead/05-Tynehead.jpg' }, { src: 'img/20220814Tynehead/06-Tynehead.jpg' },
        { src: 'img/20220814Tynehead/07-Tynehead.jpg' }, { src: 'img/20220814Tynehead/08-Tynehead.jpg' },
      ],
      list93: [
        { src: 'img/20220822Dog/01-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/02-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/03-Dog_Mt_and_Suicide_Bluffs.jpg' },
        { src: 'img/20220822Dog/04-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/05-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/06-Dog_Mt_and_Suicide_Bluffs.jpg' },
        { src: 'img/20220822Dog/07-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/08-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/09-Dog_Mt_and_Suicide_Bluffs.jpg' },
        { src: 'img/20220822Dog/10-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/11-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/12-Dog_Mt_and_Suicide_Bluffs.jpg' },
        { src: 'img/20220822Dog/13-Dog_Mt_and_Suicide_Bluffs.jpg' }, { src: 'img/20220822Dog/14-Dog_Mt_and_Suicide_Bluffs.jpg' },
      ],
      list94: [
        { src: 'img/20220827StMark/01-StMark.jpg' }, { src: 'img/20220827StMark/02-StMark.jpg' }, { src: 'img/20220827StMark/03-StMark.jpg' },
        { src: 'img/20220827StMark/04-StMark.jpg' }, { src: 'img/20220827StMark/05-StMark.jpg' }, { src: 'img/20220827StMark/06-StMark.jpg' },
        { src: 'img/20220827StMark/07-StMark.jpg' }, { src: 'img/20220827StMark/08-StMark.jpg' }, { src: 'img/20220827StMark/09-StMark.jpg' },
      ],
      list95: [
        { src: 'img/20220904Mistery/01-Mystery.jpg' }, { src: 'img/20220904Mistery/02-Mystery.jpg' }, { src: 'img/20220904Mistery/03-Mystery.jpg' },
        { src: 'img/20220904Mistery/04-Mystery.jpg' }, { src: 'img/20220904Mistery/05-Mystery.jpg' }, { src: 'img/20220904Mistery/06-Mystery.jpg' },
        { src: 'img/20220904Mistery/07-Mystery.jpg' }, { src: 'img/20220904Mistery/08-Mystery.jpg' }, { src: 'img/20220904Mistery/09-Mystery.jpg' },
        { src: 'img/20220904Mistery/10-Mystery.jpg' }, { src: 'img/20220904Mistery/11-Mystery.jpg' }, { src: 'img/20220904Mistery/12-Mystery.jpg' },
      ],
      list96: [
        { src: 'img/20220917BOC30thAnniversary/01-BOC30thAnniversary.jpg' }, { src: 'img/20220917BOC30thAnniversary/02-BOC30thAnniversary.jpg' }, { src: 'img/20220917BOC30thAnniversary/03-BOC30thAnniversary.jpg' },
        { src: 'img/20220917BOC30thAnniversary/04-BOC30thAnniversary.jpg' }, { src: 'img/20220917BOC30thAnniversary/05-BOC30thAnniversary.jpg' }, { src: 'img/20220917BOC30thAnniversary/06-BOC30thAnniversary.jpg' },
      ],
      list97: [
        { src: 'img/20220925Peaks/01-Peaks.jpg' }, { src: 'img/20220925Peaks/02-Peaks.jpg' }, { src: 'img/20220925Peaks/03-Peaks.jpg' },
        { src: 'img/20220925Peaks/04-Peaks.jpg' }, { src: 'img/20220925Peaks/05-Peaks.jpg' }, { src: 'img/20220925Peaks/06-Peaks.jpg' },
        { src: 'img/20220925Peaks/07-Peaks.jpg' }, { src: 'img/20220925Peaks/08-Peaks.jpg' }, { src: 'img/20220925Peaks/09-Peaks.jpg' },
        { src: 'img/20220925Peaks/10-Peaks.jpg' }, { src: 'img/20220925Peaks/11-Peaks.jpg' }, { src: 'img/20220925Peaks/12-Peaks.jpg' },
      ],
      list98: [
        { src: 'img/20221001Holly/01-Holly.jpg' }, { src: 'img/20221001Holly/02-Holly.jpg' }, { src: 'img/20221001Holly/03-Holly.jpg' },
        { src: 'img/20221001Holly/04-Holly.jpg' }, { src: 'img/20221001Holly/05-Holly.jpg' }, { src: 'img/20221001Holly/06-Holly.jpg' },
      ],
      list99: [
        { src: 'img/20221010Jug/01-jug.jpg' }, { src: 'img/20221010Jug/02-jug.jpg' }, { src: 'img/20221010Jug/03-jug.jpg' },
        { src: 'img/20221010Jug/04-jug.jpg' }, { src: 'img/20221010Jug/05-jug.jpg' }, { src: 'img/20221010Jug/06-jug.jpg' },
        { src: 'img/20221010Jug/07-jug.jpg' }, { src: 'img/20221010Jug/08-jug.jpg' }, { src: 'img/20221010Jug/09-jug.jpg' },
        { src: 'img/20221010Jug/10-jug.jpg' }, { src: 'img/20221010Jug/11-jug.jpg' },
      ],
      list100: [
        { src: 'img/20221015Caul/01-Caul.jpg' }, { src: 'img/20221015Caul/02-Caul.jpg' }, { src: 'img/20221015Caul/03-Caul.jpg' },
        { src: 'img/20221015Caul/04-Caul.jpg' }, { src: 'img/20221015Caul/05-Caul.jpg' }, { src: 'img/20221015Caul/06-Caul.jpg' },
        { src: 'img/20221015Caul/07-Caul.jpg' }, { src: 'img/20221015Caul/08-Caul.jpg' }, { src: 'img/20221015Caul/09-Caul.jpg' },
        { src: 'img/20221015Caul/10-Caul.jpg' },
      ],
      list101: [
        { src: 'img/20221022Dorman/01-Dorman.jpg' }, { src: 'img/20221022Dorman/02-Dorman.jpg' }, { src: 'img/20221022Dorman/03-Dorman.jpg' },
        { src: 'img/20221022Dorman/04-Dorman.jpg' }, { src: 'img/20221022Dorman/05-Dorman.jpg' }, { src: 'img/20221022Dorman/06-Dorman.jpg' },
        { src: 'img/20221022Dorman/07-Dorman.jpg' }, { src: 'img/20221022Dorman/08-Dorman.jpg' }, { src: 'img/20221022Dorman/09-Dorman.jpg' },
        { src: 'img/20221022Dorman/10-Dorman.jpg' }, { src: 'img/20221022Dorman/11-Dorman.jpg' }, { src: 'img/20221022Dorman/12-Dorman.jpg' },
        { src: 'img/20221022Dorman/13-Dorman.jpg' }, { src: 'img/20221022Dorman/14-Dorman.jpg' }, { src: 'img/20221022Dorman/15-Dorman.jpg' },
      ],
      list102: [
        { src: 'img/20221105Norvan/01-Lynn.jpg' }, { src: 'img/20221105Norvan/02-Lynn.jpg' }, { src: 'img/20221105Norvan/03-Lynn.jpg' },
        { src: 'img/20221105Norvan/04-Lynn.jpg' }, { src: 'img/20221105Norvan/05-Lynn.jpg' }, { src: 'img/20221105Norvan/06-Lynn.jpg' },
        { src: 'img/20221105Norvan/07-Lynn.jpg' }, { src: 'img/20221105Norvan/08-Lynn.jpg' }, { src: 'img/20221105Norvan/09-Lynn.jpg' },
        { src: 'img/20221105Norvan/10-Lynn.jpg' }, { src: 'img/20221105Norvan/11-Lynn.jpg' }, { src: 'img/20221105Norvan/12-Lynn.jpg' },
      ],
      list103: [
        { src: 'img/20221111BbyMnt/01-BbyMnt.jpg' }, { src: 'img/20221111BbyMnt/02-BbyMnt.jpg' }, { src: 'img/20221111BbyMnt/03-BbyMnt.jpg' },
        { src: 'img/20221111BbyMnt/04-BbyMnt.jpg' }, { src: 'img/20221111BbyMnt/05-BbyMnt.jpg' }, { src: 'img/20221111BbyMnt/06-BbyMnt.jpg' },
        { src: 'img/20221111BbyMnt/07-BbyMnt.jpg' }, { src: 'img/20221111BbyMnt/08-BbyMnt.jpg' },
      ],
      list104: [
        { src: 'img/20221113Wood/01-Wood.jpg' }, { src: 'img/20221113Wood/02-Wood.jpg' }, { src: 'img/20221113Wood/03-Wood.jpg' },
        { src: 'img/20221113Wood/04-Wood.jpg' }, { src: 'img/20221113Wood/05-Wood.jpg' }, { src: 'img/20221113Wood/06-Wood.jpg' },
        { src: 'img/20221113Wood/07-Wood.jpg' }, { src: 'img/20221113Wood/08-Wood.jpg' }, { src: 'img/20221113Wood/09-Wood.jpg' },
        { src: 'img/20221113Wood/10-Wood.jpg' }, { src: 'img/20221113Wood/11-Wood.jpg' }, { src: 'img/20221113Wood/12-Wood.jpg' },
      ],
      list105: [
        { src: 'img/20221120Knoll/01-Knoll.jpg' }, { src: 'img/20221120Knoll/02-Knoll.jpg' }, { src: 'img/20221120Knoll/03-Knoll.jpg' },
        { src: 'img/20221120Knoll/04-Knoll.jpg' }, { src: 'img/20221120Knoll/05-Knoll.jpg' }, { src: 'img/20221120Knoll/06-Knoll.jpg' },
        { src: 'img/20221120Knoll/07-Knoll.jpg' },
      ],
      list106: [
        { src: 'img/20221127Lynn/01-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/02-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/03-Lynn_Creek-and-Seymour_River.jpg' },
        { src: 'img/20221127Lynn/04-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/05-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/06-Lynn_Creek-and-Seymour_River.jpg' },
        { src: 'img/20221127Lynn/07-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/08-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/09-Lynn_Creek-and-Seymour_River.jpg' },
        { src: 'img/20221127Lynn/10-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/11-Lynn_Creek-and-Seymour_River.jpg' }, { src: 'img/20221127Lynn/12-Lynn_Creek-and-Seymour_River.jpg' },
      ],
      list107: [
        { src: 'img/202212033BbyLake/01-IMG.jpg' }, { src: 'img/202212033BbyLake/02-IMG.jpg' }, { src: 'img/202212033BbyLake/03-IMG.jpg' },
        { src: 'img/202212033BbyLake/04-IMG.jpg' }, { src: 'img/202212033BbyLake/05-IMG.jpg' }, { src: 'img/202212033BbyLake/06-IMG.jpg' },
        { src: 'img/202212033BbyLake/07-IMG.jpg' }, { src: 'img/202212033BbyLake/08-IMG.jpg' }, { src: 'img/202212033BbyLake/09-IMG.jpg' },
      ],
      list108: [
        { src: 'img/20221226bbymnt/01-bbymnt.jpg' }, { src: 'img/20221226bbymnt/02-bbymnt.jpg' }, { src: 'img/20221226bbymnt/03-bbymnt.jpg' },
        { src: 'img/20221226bbymnt/04-bbymnt.jpg' },
      ],
      list109: [
        { src: 'img/20230101Barnet/01-Barnet.jpg' }, { src: 'img/20230101Barnet/02-Barnet.jpg' }, { src: 'img/20230101Barnet/03-Barnet.jpg' },
        { src: 'img/20230101Barnet/04-Barnet.jpg' }, { src: 'img/20230101Barnet/05-Barnet.jpg' }, { src: 'img/20230101Barnet/06-Barnet.jpg' },
        { src: 'img/20230101Barnet/07-Barnet.jpg' }, { src: 'img/20230101Barnet/08-Barnet.jpg' }, { src: 'img/20230101Barnet/09-Barnet.jpg' },
      ],
      list110: [
        { src: 'img/20230107Poco/01-Poco.jpg' }, { src: 'img/20230107Poco/02-Poco.jpg' }, { src: 'img/20230107Poco/03-Poco.jpg' },
        { src: 'img/20230107Poco/04-Poco.jpg' }, { src: 'img/20230107Poco/05-Poco.jpg' }, { src: 'img/20230107Poco/06-Poco.jpg' },
      ],
      list111: [
        { src: 'img/20230115Bowen/01-Bowen_Lookout.jpg' }, { src: 'img/20230115Bowen/02-Bowen_Lookout.jpg' }, { src: 'img/20230115Bowen/03-Bowen_Lookout.jpg' },
        { src: 'img/20230115Bowen/04-Bowen_Lookout.jpg' }, { src: 'img/20230115Bowen/05-Bowen_Lookout.jpg' }, { src: 'img/20230115Bowen/06-Bowen_Lookout.jpg' },
        { src: 'img/20230115Bowen/07-Bowen_Lookout.jpg' }, { src: 'img/20230115Bowen/08-Bowen_Lookout.jpg' },
      ],
      list112: [
        { src: 'img/20230121Buntzen/21-Buntzen_Lake.jpg' }, { src: 'img/20230121Buntzen/22-Buntzen_Lake.jpg' }, { src: 'img/20230121Buntzen/23-Buntzen_Lake.jpg' },
        { src: 'img/20230121Buntzen/24-Buntzen_Lake.jpg' }, { src: 'img/20230121Buntzen/25-Buntzen_Lake.jpg' }, { src: 'img/20230121Buntzen/26-Buntzen_Lake.jpg' },
        { src: 'img/20230121Buntzen/27-Buntzen_Lake.jpg' }, { src: 'img/20230121Buntzen/28-Buntzen_Lake.jpg' }, { src: 'img/20230121Buntzen/29-Buntzen_Lake.jpg' },
        { src: 'img/20230121Buntzen/30-Buntzen_Lake.jpg' },
      ],
      list113: [
        { src: 'img/20230122Campbell/01-Campbell.jpg' }, { src: 'img/20230122Campbell/02-Campbell.jpg' }, { src: 'img/20230122Campbell/03-Campbell.jpg' },
      ],
      list114: [
        { src: 'img/20230129Seawall/00-image.jpeg' },
        { src: 'img/20230129Seawall/01-image.jpeg' }, { src: 'img/20230129Seawall/02-image.jpeg' }, { src: 'img/20230129Seawall/03-image.jpeg' },
        { src: 'img/20230129Seawall/04-image.jpeg' }, { src: 'img/20230129Seawall/05-image.jpeg' }, { src: 'img/20230129Seawall/06-image.jpeg' },
        { src: 'img/20230129Seawall/07-image.jpeg' }, { src: 'img/20230129Seawall/08-image.jpeg' }, { src: 'img/20230129Seawall/09-image.jpeg' },
        { src: 'img/20230129Seawall/10-image.jpeg' },
      ],
      list115: [
        { src: 'img/20230205Mosquito/1-Mosquito_Creek.jpg' }, { src: 'img/20230205Mosquito/2-Mosquito_Creek.jpg' }, { src: 'img/20230205Mosquito/3-Mosquito_Creek.jpg' },
        { src: 'img/20230205Mosquito/4-Mosquito_Creek.jpg' }, { src: 'img/20230205Mosquito/5-Mosquito_Creek.jpg' }, { src: 'img/20230205Mosquito/6-Mosquito_Creek.jpg' },
        { src: 'img/20230205Mosquito/7-Mosquito_Creek.jpg' }, { src: 'img/20230205Mosquito/8-Mosquito_Creek.jpg' }, { src: 'img/20230205Mosquito/9-Mosquito_Creek.jpg' },
      ],
      list116: [
        { src: 'img/20230212Dinkey/01-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/02-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/03-Dinkey_Peak_First_Lake.jpg' },
        { src: 'img/20230212Dinkey/04-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/05-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/06-Dinkey_Peak_First_Lake.jpg' },
        { src: 'img/20230212Dinkey/07-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/08-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/09-Dinkey_Peak_First_Lake.jpg' },
        { src: 'img/20230212Dinkey/10-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/11-Dinkey_Peak_First_Lake.jpg' }, { src: 'img/20230212Dinkey/12-Dinkey_Peak_First_Lake.jpg' },
        { src: 'img/20230212Dinkey/13-Dinkey_Peak_First_Lake.jpg' },
      ],
      list117: [
        { src: 'img/20230218Lynn/01-Lynn.jpg' }, { src: 'img/20230218Lynn/02-Lynn.jpg' }, { src: 'img/20230218Lynn/03-Lynn.jpg' },
        { src: 'img/20230218Lynn/04-Lynn.jpg' }, { src: 'img/20230218Lynn/05-Lynn.jpg' }, { src: 'img/20230218Lynn/06-Lynn.jpg' },
        { src: 'img/20230218Lynn/07-Lynn.jpg' }, { src: 'img/20230218Lynn/08-Lynn.jpg' }, { src: 'img/20230218Lynn/09-Lynn.jpg' },
        { src: 'img/20230218Lynn/10-Lynn.jpg' }, { src: 'img/20230218Lynn/11-Lynn.jpg' }, { src: 'img/20230218Lynn/12-Lynn.jpg' },
      ],
      list118: [
        { src: 'img/20230304Black/1-Black_Mountain-Cypress.jpg' }, { src: 'img/20230304Black/2-Black_Mountain-Cypress.jpg' }, { src: 'img/20230304Black/3-Black_Mountain-Cypress.jpg' },
        { src: 'img/20230304Black/4-Black_Mountain-Cypress.jpg' }, { src: 'img/20230304Black/5-Black_Mountain-Cypress.jpg' }, { src: 'img/20230304Black/6-Black_Mountain-Cypress.jpg' },
        { src: 'img/20230304Black/7-Black_Mountain-Cypress.jpg' }, { src: 'img/20230304Black/8-Black_Mountain-Cypress.jpg' },
      ],
      list119: [
        { src: 'img/20230312BbyMnt/01-IMG.jpg' }, { src: 'img/20230312BbyMnt/02-IMG.jpg' }, { src: 'img/20230312BbyMnt/03-IMG.jpg' },
        { src: 'img/20230312BbyMnt/04-IMG.jpg' }, { src: 'img/20230312BbyMnt/05-IMG.jpg' }, { src: 'img/20230312BbyMnt/06-IMG.jpg' },
      ],
      list120: [
        { src: 'img/20230318Reifel/01-Reifel.jpg' }, { src: 'img/20230318Reifel/02-Reifel.jpg' }, { src: 'img/20230318Reifel/03-Reifel.jpg' },
        { src: 'img/20230318Reifel/04-Reifel.jpg' }, { src: 'img/20230318Reifel/05-Reifel.jpg' }, { src: 'img/20230318Reifel/06-Reifel.jpg' },
        { src: 'img/20230318Reifel/07-Reifel.jpg' }, { src: 'img/20230318Reifel/08-Reifel.jpg' },
      ],
      list121: [
        { src: 'img/20230326IndArm/01-indarm.jpg' }, { src: 'img/20230326IndArm/02-indarm.jpg' }, { src: 'img/20230326IndArm/03-indarm.jpg' },
        { src: 'img/20230326IndArm/04-indarm.jpg' }, { src: 'img/20230326IndArm/05-indarm.jpg' }, { src: 'img/20230326IndArm/06-indarm.jpg' },
        { src: 'img/20230326IndArm/07-indarm.jpg' }, { src: 'img/20230326IndArm/08-indarm.jpg' }, { src: 'img/20230326IndArm/09-indarm.jpg' },
      ],
      list122: [
        { src: 'img/20230407Coq/01.jpg' }, { src: 'img/20230407Coq/02.jpg' }, { src: 'img/20230407Coq/03.jpg' },
        { src: 'img/20230407Coq/04.jpg' }, { src: 'img/20230407Coq/05.jpg' }, { src: 'img/20230407Coq/06.jpg' },
        { src: 'img/20230407Coq/07.jpg' }, { src: 'img/20230407Coq/08.jpg' }, { src: 'img/20230407Coq/09.jpg' },
        { src: 'img/20230407Coq/10.jpg' }, { src: 'img/20230407Coq/11.jpg' }, { src: 'img/20230407Coq/12.jpg' },
        { src: 'img/20230407Coq/13.jpg' }, { src: 'img/20230407Coq/14.jpg' },
      ],
      list123: [
        { src: 'img/20230415Buntzen/01-Bun.jpg' }, { src: 'img/20230415Buntzen/02-Bun.jpg' }, { src: 'img/20230415Buntzen/03-Bun.jpg' },
        { src: 'img/20230415Buntzen/04-Bun.jpg' }, { src: 'img/20230415Buntzen/05-Bun.jpg' }, { src: 'img/20230415Buntzen/06-Bun.jpg' },
        { src: 'img/20230415Buntzen/07-Bun.jpg' }, { src: 'img/20230415Buntzen/08-Bun.jpg' }, { src: 'img/20230415Buntzen/09-Bun.jpg' },
        { src: 'img/20230415Buntzen/10-Bun.jpg' }, { src: 'img/20230415Buntzen/11-Bun.jpg' },
      ],
      list124: [
        { src: 'img/20230423Ald/01-Ald.jpg' }, { src: 'img/20230423Ald/02-Ald.jpg' }, { src: 'img/20230423Ald/03-Ald.jpg' },
        { src: 'img/20230423Ald/04-Ald.jpg' }, { src: 'img/20230423Ald/05-Ald.jpg' }, { src: 'img/20230423Ald/06-Ald.jpg' },
        { src: 'img/20230423Ald/07-Ald.jpg' }, { src: 'img/20230423Ald/08-Ald.jpg' }, { src: 'img/20230423Ald/09-Ald.jpg' },
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
