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

      <div class="subtitle">Kayaking Kits Islands, Sep 6th, 2019
        <a class="vue-green" href="img/2019-03-24-Lynn-Canyon-Report.pdf" title="Trip Report">Trip Report</a>
      </div>
      <div style="overflow:hidden">
        <img v-gallery:group1
          class="thumbnail"
          v-for="img in list1"
          :src="img.src"
          :key="img.src">
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

      <div class="subtitle">Multiple(same images)</div>
      <div style="overflow:hidden">
        <img v-gallery="'group2'"
          class="thumbnail"
          v-for="(img,index) in list2"
          :data-index="index"
          :src="img.src"
          :key="img.src + index">
      </div>

      <div class="subtitle">Single</div>
      <div style="overflow:hidden">
        <img v-gallery
          class="thumbnail"
          v-for="(img,index) in list3"
          :src="img.src"
          :key="img.src + index">
      </div>
      <div class="subtitle" style="margin-top: 0.6rem;">Small/Long</div>
      <div style="overflow:hidden">
        <img v-gallery
          class="thumbnail"
          v-for="(img,index) in list3_5"
          :src="img.src"
          :key="img.src + index">
      </div>

      <div class="subtitle">Use thumbnail</div>
      <div style="overflow:hidden">
        <img v-gallery:group3
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
      list1: [
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/1.jpg'
        },
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/2.jpg'
        },
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/3.jpg'
        }
      ],
      list2: [
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/4.jpg'
        },
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/5.jpg'
        },
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/5.jpg'
        }
      ],
      list3: [
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/6.jpg'
        },
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/7.jpg'
        },
      ],
      list3_5: [
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/8.jpg'
        },
        {
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/9.jpg'
        }
      ],
      list4: [
        {
          thumbnail:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/t1.jpg',
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/7.jpg'
        },
        {
          thumbnail:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/t2.jpg',
          src:
            'https://raw.githubusercontent.com/ssshooter/img-vuer/master/img/4.jpg'
        }
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
