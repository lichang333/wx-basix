# wx-basix
A One Day Entry-Level Course to wxml and wxss

## Welcome!
This site is a reference for an introduction to programming Tencent’s WeChat mini-programs. You’ll be learning WeChat’s proprietary mark-up and styling languages, WXML and WXSS. If you’re familiar with HTML and CSS, lots of this will look familiar. 

If you’re not familiar with HTML and CSS, what you learn today can help you learn those in the future.

## Goals
* Start a new project using WeChat’s IDE (integrated development environment)
* Get familiar with basic syntax/vocabulary
* Write some WXML
* Get comfortable breaking things

## 1. Download!
WeChat IDE download [here](http://open.wechat.com/cgi-bin/newreadtemplate?t=overseas_open/docs/mini-programs/development/devtools/download)
You’ll want to code in WeChat’s special code editor.

## 2. Start a New Project
[image:3507C0E2-DDE0-4031-9F3D-B56CFA07440F-321-000061390ACFD4DC/Screen Shot 2018-05-15 at 3.56.18 PM.png]
[image:799B7A70-3F35-4109-A647-BC4C16CCCF13-321-00006139180ED844/Screen Shot 2018-05-15 at 3.56.33 PM.png]
[image:08CF1FB9-388C-4CCA-871D-3C67E6A7F5B0-321-00006139186C6069/Screen Shot 2018-05-15 at 3.56.47 PM.png]
[image:DC6891E7-07CD-4C0C-86C1-0E1AF4FCC8AB-321-0000613918B45B77/Screen Shot 2018-05-15 at 3.58.01 PM.png]
[image:F2A8CBF0-103A-4822-A9D3-9316E74F1DB7-321-000061391AD85288/Screen Shot 2018-05-15 at 3.58.28 PM.png]

Voila! You’re in.

## 3. WXML: your content and structure. 
You can start with this WXML code in index.html and replace the content.

/index.wxml/
```
<text>Le Wagon</text>
<text>Learn to Code</text>
<image src="https://iphonewallpaperss.us/wp-content/uploads/2017/08/79-best-iphone-6-wallpapers-images-on-pinterest-with-iphone-6-funny-animal-wallpaper.jpg"></image>
<button type="default">Start now</button>
```

Find an image online, preferably phone-sized, like the one I’m using. You can just use this one for now, and swap it out later. 

[image:DA6DE76B-1914-454E-9EBC-F67456D34447-321-000061705EEEDF9A/D920CBB7-90AF-4495-9313-10BC9E5EB706.png]

## 4. WXSS
WXSS selects elements in your WXML page and applies the style that you define. 

_Use WXSS to:_
	 * make the font stylish
	 * style the title and subtitle differently, using different classes
	 * make the button cool

_Looking for colors:_
	* For colors use [Colorzilla Chrome](http://www.colorzilla.com/chrome/) plugin to pick colors from other websites
	* You can also find beautiful colors on [Coolors](https://coolors.co/) or [Color Hunt](http://colorhunt.co/)

If you’re having trouble, copy paste the CSS code below in `index.wxss ` and make it your own
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

If you’re WXSS isn’t working, it’s probably because you haven’t added the corresponding class names to the WXML.
```
<text class="title">Le Wagon</text>
<text class="content">Learn to Code</text>
<image src="https://iphonewallpaperss.us/wp-content/uploads/2017/08/79-best-iphone-6-wallpapers-images-on-pinterest-with-iphone-6-funny-animal-wallpaper.jpg"></image>
<button type="default">Start now</button>
<button class="btn"> Start</button>
```

## 5. `<view>` to straighten things out
A view will create a rectangle around one or many elements in you WXML. You can also apply classes to views to adjust their height, width, background, position,  the positioning of the element inside, and more.  

Wrap the following elements in `<view>` tags:
* The entire page
* The title and content elements
* The button
* Give each view a class, so we can style them in the WXSS

```
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

/* the banner, which contains both the content and the button --> */
.banner {
  background-image: linear-gradient(-125deg, rgba(0,101,168,0.5) 0%, rgba(215, 49, 55, 0.2) 50%), url('https://iphonewallpaperss.us/wp-content/uploads/2017/08/79-best-iphone-6-wallpapers-images-on-pinterest-with-iphone-6-funny-animal-wallpaper.jpg');
  height: 100vh;
  align-items: center;  
  background-size: fit;
  background-position: center;
  display:flex;   
  flex-direction: column;
}

/* the banner content, which is composed of title and content. We want to move these independently of the button --> */

.content-container {
  font-family: avenir;
  color: rgb(215, 49, 55);
  padding-top: 10px;
  text-align: center; 
}

/* the title --> */

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
don’t forget the comma after "pages/logs/logs”

This will generate a new page with a set of four files, like this

* Paste this JS into locate.js
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

* Paste this WXML into locate.wxml
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

* Paste this into locate.wxss
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

Add tabs:
```
json
//inside app.json
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

Add navigator to your button:
```
<navigator url="../slider/slider" class="btn-div">
   <button class="btn"> Start</button>
</navigator>
```
