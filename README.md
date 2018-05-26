# wx-basix
A One Day Entry-Level Course to wxml and wxss

## Welcome!
This page is a reference for an introduction to programming Tencent’s WeChat mini-programs. You’ll be learning WeChat’s proprietary mark-up and styling languages, WXML and WXSS. If you’re familiar with HTML and CSS, lots of this will look familiar :bowtie: 

If you’re not familiar with HTML and CSS, what you learn today can help you learn those in the future :muscle:

## Goals
* Start a new project using WeChat’s IDE (integrated development environment)
* Get familiar with basic syntax/vocabulary
* Write some WXML, write some WXSS
* Make a pretty home page
* Get comfortable breaking things

## 1. Download!
WeChat IDE download [here](http://open.wechat.com/cgi-bin/newreadtemplate?t=overseas_open/docs/mini-programs/development/devtools/download).

You’ll want to code in WeChat’s special code editor, which will help you autocomplete and preview your work.

## 2. Start a New Project

Starting a new project takes a couple of clicks but is quite simple. Follow the steps below :point_down:

### Step 1 
> ![Step 1](https://github.com/dengel29/wx-basix/blob/master/New%20Project%201:5.png)

### Step 2
> ![Step 2](https://github.com/dengel29/wx-basix/blob/master/New%20Project%202:5.png)

### Step 3
> ![Step 3](https://github.com/dengel29/wx-basix/blob/master/New%20Project%203:5.png)

### Step 4
>![Step 4](https://github.com/dengel29/wx-basix/blob/master/New%20Project%204:5.png)

### Step 5
>![Step 5](https://github.com/dengel29/wx-basix/blob/master/New%20Project%205:5.png)


Voila! You’re in.

## 3. WXML: your content and structure. 
You can start with this WXML code in index.html and replace the content.

index.wxml
```
<text>Le Wagon</text>
<text>Learn to Code</text>
<image src="https://iphonewallpaperss.us/wp-content/uploads/2017/08/79-best-iphone-6-wallpapers-images-on-pinterest-with-iphone-6-funny-animal-wallpaper.jpg"></image>
<button type="default">Start now</button>
```

Find an image online, preferably phone-sized, like the one I’m using. You can just use this one :point_down: for now, and swap it out later. 

![Panda](https://iphonewallpaperss.us/wp-content/uploads/2017/08/79-best-iphone-6-wallpapers-images-on-pinterest-with-iphone-6-funny-animal-wallpaper.jpg)

You can use include this URL as the source for your background image :point_right: https://tinyurl.com/yda6swmk :clipboard:

## 4. WXSS
WXSS selects elements in your WXML page and applies the style that you define. 

_Use WXSS to:_
	 * make the font stylish
	 * style the title and subtitle differently, using different classes
	 * make the button cool

_Looking for colors:_
	* For colors use [Colorzilla Chrome](http://www.colorzilla.com/chrome/) plugin to pick colors from other websites
	* You can also find beautiful colors on [Coolors](https://coolors.co/) or [Color Hunt](http://colorhunt.co/)

If you broke your WXSS, don't panic: copy paste :clipboard: the CSS code below :point_down: in `index.wxss ` and tweak the style
```
.title {
  font-family: avenir;
  font-size: 48px;
  font-weight: 4px;
  display: block; 
  padding-bottom: 15px;
}

.content {
  font-family: avenir;
  font-size: 24px;
  font-weight: 2px;
}

.btn {
  font-family: 'Trebuchet MS';
  font-size: 20px;
  font-weight: bold;
  color: black;
  background-color: rgba(215, 49, 55, 0.9);
}
```

If your WXSS isn’t working, it’s probably because you haven’t added the corresponding class names to the WXML like below :point_down:
```
<text class="title">Le Wagon</text>
<text class="content">Learn to Code</text>
<image src="https://tinyurl.com/yda6swmk"></image>
<button type="default">Start now</button>
<button class="btn"> Start</button>
```
### Styling the Image: In-line style vs. code splitting
Some people say more is better. Some don't. We have more than one way to add style, we can add style. You can do largely the same things, but there are a few differences. One difference that you might notice is that local images (images saved on your computer) *can* be used in **inline style** like this. 

```
<image class="banner" style="background-image: url('../../images/panda.jpeg')"> 
```

However, we must use an **external image** (image on the internet, with a URL source) if we want to put all of our style in the `.wxss` file:

```
.banner {
  background-image: url('https://tinyurl.com/yda6swmk');
}
```

The efect is the same, but the way we write the code is different. No worries. Read more about the `<image>` element [here](http://open.wechat.com/cgi-bin/newreadtemplate?t=overseas_open/docs/mini-programs/development/component/image#component_image)

## 5. `<view>` to straighten things out
* A `view` will create a rectangle around one or many elements in you WXML. 
* You can also apply classes to views to adjust their height, width, background, position, the positioning of the element(s) inside, and more.  

Wrap the following elements in `<view>` tags:
* The entire page
* The title and content elements
* The button
* Give each view a class, so we can style them in the WXSS

```
<!--the banner contains all content, image, title, content, and button.  -->
<view class="banner"> 
 
 <!-- the banner content, which is composed of title and content. We want to move these independently of the button-->
  <view class="content-container" > 
    
    <!-- the title -->
    <text class="title">Le Wagon</text>
	
    <!-- the content -->
    <text class="content">Change Your Life 
    Learn to Code</text>   

  </view>  

  <!-- the button -->
  <view class="btn-div">
  	<button class="btn"> Start</button>
  </view>  
</view> 
```

## 6. Make it perfect
Final WXSS for your fully-marked-up WXML file:
```
/* the banner, which contains both the content and the button */
.banner {
  background-image: linear-gradient(-125deg, rgba(0,101,168,0.5) 0%, rgba(215, 49, 55, 0.2) 50%), url('https://iphonewallpaperss.us/wp-content/uploads/2017/08/79-best-iphone-6-wallpapers-images-on-pinterest-with-iphone-6-funny-animal-wallpaper.jpg');
  height: 100vh;
  align-items: center;  
  background-size: fit;
  background-position: center;
  display:flex;   
  flex-direction: column;
}

/* the banner content, which is composed of title and content. We want to move these independently of the button */

.content-container {
  font-family: avenir;
  color: rgb(215, 49, 55);
  padding-top: 10px;
  text-align: center; 
}

/* the title */

.title {
  font-size: 48px;
  font-weight: 4px;
  display: block; 
  padding-bottom: 15px;
}

.content {
  font-size: 24px;
  font-weight: 2px;
}

.btn-div {
  padding-top: 45px;
  width: 80px;
  opacity: 0%;
  background-image: none;
  justify-content: center;
}

.btn {
  font-family: 'Trebuchet MS';
  font-size: 20px;
  font-weight: bold;
  color: black;
  background-color: rgba(215, 49, 55, 0.9);
  box-shadow: 0.4px 0.3px 0.2px 0.2px;
}
```

## 7. Moving forward
* Make a new page.
    1. Go to `app.json`
    2. Add “pages/locate/locate” like this:
```
{
  "pages":[
    "pages/index/index",
    "pages/logs/logs",
    "pages/locate/locate" 
  ],
 }
```
:warning: don’t forget the comma after "pages/logs/logs” :warning:

This will generate a new page with a set of four files, just like your `index` page does

* Next, paste this JS into locate.js :clipboard:
```
Page({
  data: {
    long: 0,
    lat: 0
  },
  
  onReady: function(e){
    console.log(e)
    // Use wx.createMapContext to get map context 
    this.mapCtx = wx.createMapContext('myMap')
  },

  getCenterLocation: function() {
    this.mapCtx.getCenterLocation({
      success: (res) => {
        console.log(res.longitude)
        console.log(res.latitude)
        this.setData({
          long: res.longitude,
          lat: res.latitude
        })
      }
    })
  },

  moveToLocation: function () {
    this.mapCtx.moveToLocation()
  }
})
```

* Paste this WXML into locate.wxml :clipboard:
```
<map id="myMap" show-location />

<button type="primary" bindtap="getCenterLocation">Get location</button>
<button type="primary" bindtap="moveToLocation">Recenter on Current Location</button>

<view class="coordinates">
  <text class="title">  Your coordinates are: </text> 
  <view class="coord">
    Latitude = {{lat}}
  </view>
  <view class="coord">
    Longitude = {{long}}
  </view>
</view>
```

* Paste this into locate.wxss :clipboard:
```
#myMap {
  height: 70vh;
  width: 100vh;
}

.title {
  font-family: "Avenir";
  color: chocolate;
}

.coordinates {
  width: 100vw;
  border-bottom: 25rpx chocolate solid;
  text-align: center;
  font-family: "Avenir";
  color: darkgoldenrod;
}
```

Want a different way to navigate between pages? Add tabs in your `app.json` file 
```
"tabBar": {
    "list": [{
      "pagePath": "pages/index/index",
      "text": "Homepage"
    }, {
      "pagePath": "pages/logs/logs",
      "text": "Log"
    }]
  },
```

Wrap your button in `navigator` tags, to link to your new page:
```
<navigator url="../locate/locate" class="btn-div">
   <button class="btn"> Start</button>
</navigator>
```
## Interested in going even further?

* [The official WeChat documentation](http://open.wechat.com/cgi-bin/newreadtemplate?t=overseas_open/docs/mini-programs/development/brief-tutorial#development_brief-tutorial)
* Follow our official account for info on future workshops
  <img src="https://github.com/dengel29/wx-basix/blob/master/ChengduOA-QR.jpg?raw=true" width="200">
* [Apply to Le Wagon's next batch, starting June 25!! :confetti_ball:](http://lewagon.com/chengdu)
