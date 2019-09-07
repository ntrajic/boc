<em> Quick customisation for the BOC non-profit organisation (Burnabyoutdoor.com) </em>>
========================================================================================

# Image Viewer of BOC trips, with addition of editing trip reports.

Currently boc/img/ directory will contain images of 2 trips - to Buntzen Lake ndn Lyn Canyon Loop.

<em>In the future - for production, there will be directory structure:</em>
===========================================================================
boc/img/<06Sep2019_tripName> directory with all its images
boc/img/<tripReports> single directory for *.pdf trip reports

<em>NOTE: boc/src/App.vue HTML template file needs to be updated with trip pictures </em>
==========================================================================================
ddTripPicture.jpg, dd = n, d is a digit for picutures ordering purposes
Pictures need to be placed in the aabove directory, following the directory structure.
Trip report needs to be converted from MS Word docx format to PDF (to be read-only), and placed into the single tripReports directory.

<em>Prototype will place all images and reports to boc/img directory - the reason why this is "quick and dirty" prototype, and customisation.</em>



# img-vuer

> An Mobile-First image viewer for Vue2

[中文 README](https://github.com/ssshooter/img-vuer/blob/master/README.cn.md)

---

:ok_woman: Easy to use

:point_right: Swipe gesture

:mag: Zoom gesture

V0.11.0 Now you can use thumbnail~

V0.13.0 Gallery hide when the physical back button is pressed (android device only)

V0.15.0 Fix blurry after using scale()

:computer: v0.17.1 compatible with PC

**Now you can use both Mobile and PC Browser** :satisfied:

**[live demo](https://ssshooter.github.io/img-vuer/index.html)**

or scan the QRcode

<img width="150px" src="./QRcode.png">

## Install

```bash
npm i img-vuer --save
```

## Usage

```javascript
// import img-vuer and install
import gallery from 'img-vuer'
Vue.use(gallery, {
  swipeThreshold: 150, // default 100
  isIndexShow: true, // show image index, default true
  useCloseButton: true, // trigger gallery close with close button, default true
  preload: true, // preload images in the same group, default true
})
```

```html
<!-- add direact to <img> -->
<img v-gallery :src="..." />

<!-- group images -->
<img v-gallery:groupName :src="..." />
<img v-gallery:groupName :src="..." />
<img v-gallery:groupName :src="..." />

<!-- OR (dynamic bind) -->
<img v-gallery="'groupName'" :src="..." />

<!-- use thumbnail, new in 0.11.0 -->
<img v-gallery :src="thumbnailSrc" data-large="originSrc" />

<!-- trigger close gallery, new in 0.14.0 -->
<button @click="$imgVuer.close()">close</button>
```

## API

| api               | arg   | description                                                           |
| ----------------- | ----- | --------------------------------------------------------------------- |
| close()           | /     | close the viwer                                                       |
| onIndexChange()   | cb    | `$imgVuer.onIndexChange((newVal, oldVal)=>{...})`                     |
| onToggle()        | cb    | on close or on open `$imgVuer.onToggle((newVal, oldVal)=>{...})`      |
| changeBGColor()   | color | change the background color of viwer `$imgVuer.changeBGColor('#fff')` |
| next()            | /     | switch to next image `$imgVuer.next()`                                |
| prev()            | /     | switch to previous image `$imgVuer.prev()`                            |
| getCurrentIndex() | /     | /                                                                     |

## Development

```bash
# development environment node v6.15.1

# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

## Troubleshooting

### Abnormal with page scale

Add meta

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1,user-scalable=0, maximum-scale=1"
/>
```

### for a large number of large images

If you group a large number of large images, img-vuer will load all image in the same group, so it will cause unnecessary mobile data traffic and slow the page down.

You can use `preload` option in this situation and img-vuer will only load the image you watched.

### key

Should not use index as key for the component which is added `v-gallery`.

## License

MIT
