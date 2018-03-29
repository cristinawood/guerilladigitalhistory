## Generating the *Picturing Lebreton Flats* website

Before projecting the images on the construction hoarding near Lebreton Flats, I had been considering building a site to link to for passerby to find out more. While it's tempting to want to load that up with lots of information, I wanted it to be accessible and digestible, as well as - crucial - mobile-friendly for on-the-go visits. 

Since I had gotten a taste of working with Hugo and HTML for another project (I'll link to that when it's live), I wanted to see what I could do with this generator for the Lebreton project. I had originally planned to use the HTML5Up template "TWENTY", (https://html5up.net/twenty) but felt that might be too image-heavy and didn't really suit my purposes. Instead, I chose to work with his "Story" theme, (https://html5up.net/story), which is more simple and modular. Neither of these is already loaded into Hugo, which meant tweaking the process a bit.

In the past, and according to the Hugo tutorial, the super-simple process of generating a site begins with the `hugo new site` command. From there, they suggest you install a theme from their collection using the following commands: `$ cd themes
$ git clone https://github.com/budparr/gohugo-theme-ananke.git` 

Since I was using another theme, I looked into transferring another site into Hugo, and found these directions from "Whipperstacker" (http://whipperstacker.com/2016/09/22/convert-an-existing-site-into-hugo/). I deleted the "quickstart" static folder and replaced it with the ***Story*** theme files I'd downloaded from HTML5Up's site. Then I put the index.html file into the hugo-generated "layouts" folder. When I tested the site by running `hugo server`, there it was! 

I got rid of the index-demo.html and demo.js files, since they weren't going to affect the final site, and began trying to populate the site with images. This gave me some trouble as the original code looked like this:

```
	<div class="image">
							<img src="images/banner.jpg" alt="" />
						</div>
 ```

As many times as I tried to replace the banner image with the one that I wanted instead of the sample gradient provided, the generated site would not change. I deleted the sample images from the folder completely, searched the whole "quickstart" folder for the words "image" and "banner" to see if there was a hidden path or something I wasn't getting, and nothing worked. I forced the `hugo server --disableFastRender` to see if there was something being missed in the quick generating of the site, and this didn't have any effect. So tricky when the logical path is shown, everything corresponds, and the answer is coming out wrong. Finally, I tried deleting the folder and just having the path lead to the file:

```
	<div class="image">
							<img src="/banner.jpg" alt="" />
						</div>
 ```
 ***AND IT WORKED!***
 
 Not sure why this worked the way it did, but wanted to record that process for future reference. One thing I've been trying to keep in mind is that even if I delete code and lose it, or break something, there is learning in that! There is also no irreparable damage to be done, because I'm building on the work generously shared by HTML5Up, I can always download a new version of the theme code and rework it. 
 

