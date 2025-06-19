CAOS - Comibyte Animate On Scroll
A lightweight, performant, and dependency-free JavaScript library for animating elements on scroll. CAOS uses the modern IntersectionObserver API for optimal performance, ensuring smooth animations without bogging down your main thread.

Key Features
Performant: Uses IntersectionObserver to efficiently detect when elements enter the viewport.

Zero Dependencies: Written in pure vanilla JavaScript. No jQuery or other libraries required.

Customizable: Easily change animation duration, delay, and trigger points through HTML data attributes.

Variety of Animations: Includes fades, slides, zooms, flips, and more.

Special Effects: Built-in support for modern overlay reveals and parallax background effects.

Repeatable or Once-Off: Configure animations to run once or every time an element enters the viewport.

Table of Contents
Installation

Usage

Available Animations

Customization Attributes

Special Effects

Overlay Effect

Parallax Effect

Advanced Configuration (JavaScript)

License

Installation
Getting started with CAOS is simple. Since the library is self-contained, you just need to include its CSS and JavaScript in your HTML file.

Link the CSS : Link the CAOS CSS style within the <head> your HTML.

<link rel="stylesheet" href="path to the file/caos.css">


Link the JavaScript: Link the CAOS JavaScript file just before the closing </body> tag, with a <script> tag.

<!-- Before your closing </body> tag -->
 <script src="path to the folder/caos.js"></script>



That's it! The library is now active and will automatically detect and animate any elements with the data-caos attribute.

Usage
To animate an element, simply add the data-caos attribute to it with the desired animation type.

<!-- This div will fade in from the bottom when it scrolls into view -->
<div data-caos="fade-up">
  <h2>Hello, World!</h2>
  <p>This content is now animated.</p>
</div>



Available Animations
Here is a list of all the animation types you can use with data-caos:

| Animation Type | Description |
| fade-up | Fades and moves up from the bottom. |
| fade-down | Fades and moves down from the top. |
| fade-left | Fades and moves in from the left. |
| fade-right | Fades and moves in from the right. |
| slide-up | Slides in from completely below the element. |
| slide-down | Slides in from completely above the element. |
| slide-left | Slides in from completely to the left. |
| slide-right | Slides in from completely to the right. |
| zoom-in | Zooms in from a smaller size. |
| zoom-out | Zooms out from a larger size. |
| flip-up | Flips in over the X-axis from the bottom. |
| flip-down | Flips in over the X-axis from the top. |
| flip-left | Flips in over the Y-axis from the left. |
| flip-right | Flips in over the Y-axis from the right. |
| overlay-reveal-right | Reveals content with an overlay moving right. |
| overlay-reveal-left | Reveals content with an overlay moving left. |
| parallax | Applies a parallax effect to a background. |

Customization Attributes
You can easily customize the behavior of each animation directly from your HTML using these data attributes:

data-caos-duration: Sets the duration of the animation in milliseconds.

Example: data-caos-duration="1500" (for a 1.5-second animation).

data-caos-delay: Adds a delay before the animation starts, in milliseconds.

Example: data-caos-delay="500" (waits 0.5 seconds before starting).

data-caos-once: Overrides the global setting to make a specific animation run only once.

Example: data-caos-once="true"

data-caos-overlay-color: Sets the background color for the overlay reveal effect.

Example: data-caos-overlay-color="#ff6347"

Combined Example:

<div data-caos="fade-left" data-caos-duration="1000" data-caos-delay="300">
  This element fades in from the left over 1 second after a 300ms delay.
</div>



Special Effects
Overlay Effect
The overlay effect requires a specific HTML structure. The element with the data-caos attribute acts as a container, and it must contain a div with the class caos-overlay.

<!-- Container with the animation attribute -->
<div class="caos-overlay-container" data-caos="overlay-reveal-right" data-caos-overlay-color="var(--primary-color)">
  <!-- The actual overlay element -->
  <div class="caos-overlay"></div>
  
  <!-- Your content to be revealed -->
  <h1>Revealed Content</h1>
</div>



Parallax Effect
The parallax effect also requires a specific structure. The data-caos="parallax" container holds a background element and a content element.

<!-- Container with the parallax attribute -->
<div class="caos-parallax-container" data-caos="parallax">
  <!-- The background element that will move -->
  <div class="caos-parallax-bg" style="background-image: url('path/to/your/image.jpg');"></div>
  
  <!-- Your foreground content -->
  <div class="caos-parallax-content">
    <h2>Parallax Title</h2>
  </div>
</div>



The background image moves at a different speed than the page scroll, creating a sense of depth.

Advanced Configuration (JavaScript)
You can change the global behavior of CAOS by passing an options object to the init() function.

CAOS.init({
  // How much of the element should be visible before animating (0 to 1.0)
  // Default is 0.5 (50%)
  threshold: 0.75, 

  // Whether animations should only happen once globally.
  // Default is false. Can be overridden per-element with data-caos-once.
  once: true 
});



Options
threshold: (Number | Default: 0.5) A value between 0.0 and 1.0 that determines what percentage of the element must be visible on screen before the animation is triggered. 0.25 means 25% visible.
