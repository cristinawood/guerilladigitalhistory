## What's the deal with modal windows?

![what's the deal](https://img.ziggi.org/vAagBQVV.jpg)

I had wanted to make modal windows work on my Hugo site, built on a single-page site template. I thought modals would be the perfect solution to the impulse to add more details to the site without overloading the basic template. I met with Shawn and Rob, who tried to help me come up with the code to add those into my HTML index file and make them work on the site. 

We started with code from this page: https://www.w3schools.com/howto/howto_css_modals.asp

and put this
```
<!-- Trigger/Open The Modal -->
<button id="myBtn">Open Modal</button>

<!-- The Modal -->
<div id="myModal" class="modal">

  <!-- Modal content -->
  <div class="modal-content">
    <span class="close">&times;</span>
    <p>Some text in the Modal..</p>
  </div>

</div>
```
into the index.html file, 

And then this into the main.css file:
```
/* The Modal (background) */
.modal {
    display: none; /* Hidden by default */
    position: fixed; /* Stay in place */
    z-index: 1; /* Sit on top */
    left: 0;
    top: 0;
    width: 100%; /* Full width */
    height: 100%; /* Full height */
    overflow: auto; /* Enable scroll if needed */
    background-color: rgb(0,0,0); /* Fallback color */
    background-color: rgba(0,0,0,0.4); /* Black w/ opacity */
}

/* Modal Content/Box */
.modal-content {
    background-color: #fefefe;
    margin: 15% auto; /* 15% from the top and centered */
    padding: 20px;
    border: 1px solid #888;
    width: 80%; /* Could be more or less, depending on screen size */
}

/* The Close Button */
.close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
}

.close:hover,
.close:focus {
    color: black;
    text-decoration: none;
    cursor: pointer;
}
```

And this bit of javascript at the top of the index.html file:
```
// Get the modal
var modal = document.getElementById('myModal');

// Get the button that opens the modal
var btn = document.getElementById("myBtn");

// Get the <span> element that closes the modal
var span = document.getElementsByClassName("close")[0];

// When the user clicks on the button, open the modal 
btn.onclick = function() {
    modal.style.display = "block";
}

// When the user clicks on <span> (x), close the modal
span.onclick = function() {
    modal.style.display = "none";
}

// When the user clicks anywhere outside of the modal, close it
window.onclick = function(event) {
    if (event.target == modal) {
        modal.style.display = "none";
    }
}
```

We had to render the site in Python to get that to show up, but it did! 
By the way, that command is: ```python -m SimpleHTTPServer 8000```

First, just with a header: ![just header modal window](https://img.ziggi.org/teLosqq6.png)

and then with some text demarcated as a paragraph: ![modal paragraph](https://img.ziggi.org/sIAvQ2xq.png)

Unfortunately, once we tried to get multiple modal windows going, we couldn't figure out how to differentiate the two. Even changing the "class type", the trigger would just pop up with the first modal window code it found. The few hours we spent working through these issues were certainly not wasted, but I still wanted to find a solution to the problem of a lack of space for extra information on the website. Shawn showed me how to copy the main site into the original site, basically nesting sites to create additional pages. This was as simple as working from the finder window, duplicating the "public" file generated by Hugo/Python, and copying it into itself with another name - ex. "page 1." Then, by changing the button path on the main page to ```href="/page1/index.html"```, I could make a single page site into multiple! 

Working on customizing those extra pages was the next step, and I'll have to save playing with modal windows for another day. I learned a lot through the whole process about div classes, and not being afraid to finick with the code and just see what happens. (This seems to be a frequent lesson...) I was proud to have been able to customize a Hugo site - basically creating a new template for a site. The ***Story*** theme from HTML5Up is super customizable, so it's neat to play with that as I create the individual pages. I should record that I also purchased a domain name - www.picturinglebretonflats.ca - via Reclaim Hosting under their student/personal plan, and that worked really well. Once I'm ready, I'll just unzip a copy of the Public folder on my machine into the hosting service, and hope that all goes to plan! 
