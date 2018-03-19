# A Modern Approach to Responsive Images

##### The one constant is change. Is that how the saying goes? 
Well, let’s agree that it does and take a moment to consider how much has evolved in the world of responsive web design. Yesterday's idea has become today's standard and tomorrow's best practice (which will eventually be ancient history, but let’s not dwell on that just yet).

### Here’s a little history for you...

**2010:** [Responsive web design consciousness awakens](http://alistapart.com/article/responsive-web-design)

**2011:** [Debate ensues about responsive image best practices](https://css-tricks.com/which-responsive-images-solution-should-you-use/)

**2014:** [Industry standard starts to emerge for ```<srcset>```, ```<sizes>```, and ```<picture>``` attributes](https://caniuse.com/#feat=srcset)

**2018:** [Mobile page load performance gets the squeeze from Google](https://techcrunch.com/2018/01/17/google-will-make-page-speed-a-factor-in-mobile-search-ranking-starting-in-july/)

### How do these events relate?
As the concept of responsive web design gained traction, the idea of flexible and adaptive images played a central role. Responsive images came to mean the practice of serving appropriately sized images to each device, and standards began to emerge. 

### But wait! 
Just as the technology has evolved, so have industry expectations for best practices in responsive web design. It’s not enough to serve up different-sized images on mobile, tablet, or desktop. _Truly responsive image solutions require a thoroughly modern approach._

_Modern responsive images_ must…

-	Display at sizes appropriate to device
-	Convey visual meaning no matter the device size
-	Effectively balance file size with image quality
-	Support speedy page loads, especially on smaller devices

Following are three best practices for _a modern approach to responsive images._

### #1 - Make sure it scales
That 2MB hero image on your site that loads fine on desktop, will be slow to load on mobile. To minimize file size and load time on smaller devices, you can utilize HTML elements such as ```<srcset>``` and ```<size>``` to display an appropriately sized image for mobile, tablet, and desktop. 

##### Example ([code sample](https://github.com/trinasch/quilt/blob/master/index.html) | [preview](https://trinasch.github.io/quilt/index.html)):

``` 
<img srcset="quilt_1240w.jpeg 1240w,
  quilt_800w.jpeg 800w, 
  quilt_480w.jpeg 480w, 
  quilt_320w.jpeg 320w"
sizes="(max-width: 320px) 280px, 
  (max-width: 480px) 440px, 
  (max-width: 800px) 760px,
  (min-width: 2400px) 1240px"
src="quilt_1240w.jpeg" 
alt="quilted">
```

### #2 - Crop and position images appropriately per device
The screen-spanning hero image doesn’t just present file size / slow to load challenges. It also becomes harder to emphasize details in the photo as it scales down on smaller devices. Enter the HTML element of ```<picture>``` which allows you to define alternate images to be displayed. This allows you to substitute a cropped image on smaller devices and bring those otherwise lost details back into focus.

##### Example ([code sample](https://github.com/trinasch/beach/blob/master/index.html) | [preview](https://trinasch.github.io/beach/index.html)):

``` 
<picture>
  <source media="(max-width: 599px)" srcset="beach_480w_cropped.jpeg">
  <source media="(min-width: 600px)" srcset="beach_1240w.jpeg">
  <img src="beach_1240w.jpeg" alt="boy do I wish I was here right now">
</picture>
```
##### Notice how the crop on the third image is different than the first two? That's ```<picture>``` at work.

![responsive crop example](https://raw.githubusercontent.com/trinasch/technical-post/master/beach_responsive-sample.png)

### #3 - Serve just enough pixels
One step that should always be taken with your website images is to compress them.  Compression reduces the file size for faster loading, often with little visible change between the original and the compressed image. My compression tool of choice is [ImageOptim](https://imageoptim.com/) because it is so drag-n-drop easy. 

With [WebPageTest](https://www.webpagetest.org/), I evaluated the results of compressing images in the two previous projects:

##### I compressed the _beach project_ image files by 10%:

Website | Page load speed | Bytes in
--- | --- | ---
[Beach](https://trinasch.github.io/beach/index.html) | 1.340s | 74KB
[Beach (low res)](https://trinasch.github.io/beach-low-res/index.html) | 1.313s | 69KB

##### I compressed the _quilt project_ image files by 60%:

Website | Page load speed | Bytes in
--- | --- | ---
[Beach](https://trinasch.github.io/quilt/index.html) | 4.730s | 677KB

[Beach (low res)](https://trinasch.github.io/quilt-low-res/index.html) | *2.320s* | 237KB

### Wrap it up
And that’s it, my best three tips for a **thoroughly modern approach to responsive images.** Together, these best practices can help you serve up images appropriately on different device sizes and reduce files sizes to increase page load speed. Go ahead, give it a try!

_Do you have a technique that you like to use for your projects? Tell me about in the comments!_