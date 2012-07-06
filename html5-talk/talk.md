# HTML5
 
 High level overview of CSS Transitions, multi touch events specifically for mobile.
 
## CSS3 Coolbits

 Why use Transitions / Transforms
 
 * Hardware accleration
 * Mobile devices != Desktop computers
 
### Transitions

Transition from one property to another.

Syntax:

    transition:  [ <transition-property> ||
               <transition-duration> ||
               <transition-timing-function> ||
               <transition-delay> ]
               
Vendor Prefix for most browsers*

    -webkit-transition: all 500s ease-in-out;
    -moz-transition: all 1s ease-in-out;
    -o-transition: all 1s ease-in-out;
    transition: all 1s ease-in-out;
  
* Safari 3.2
* Chrome 1
* FireFox 4.0
* Opera 10.5
* IE 10
  
Short Hand Notation
  
    -webkit-transition: all 1s ease-in-out;
  
Long Hand Notation

    -webkit-transition-property: all;
    -webkit-transition-duration: 1s;
    -webkit-transition-timing-function: linear;
    -webkit-transition-delay: 0s;
	  
JavaScript Notation

    var el = document.getElementById('myDiv');
    
    el.style.transitionProperty = "top";
    el.style.transitionDuration = "1s";
    el.style.transitionTimingFunction = "linear";
    el.style.transitionDelay = '0s';
    
You can animation most properties that accept a px, % or color.

Default Timing functions

    linear
    ease
    ease-in
    ease-out
    ease-in-out
    
Or Create your own:

    cubic-bezier(n,n,n,n)
    
Using Bézier Curves control points x1,y1,x2,y2 you can even have more control over how the elements are animated.

NB: Values should be between 0 ~ 1. new WebKit allows for a values out of range in Y
BUG: https://bugs.webkit.org/show_bug.cgi?id=45761

Helpful tool for custom timing functions
http://cubic-bezier.com/

               
### Transforms

Vendor Prefix for most browsers*

2 Flavours of transforms, 2D and 3D

CSS3 Transforms support 2D

* Safari 3.2
* Chrome 1
* FireFox 3.5
* Opera 10.5
* IE 9

CSS3 Transforms support 3D

* Safari 4
* Chrome 12
* FireFox 10
* Opera 12
* IE 10

2D Syntax

    #myDiv {
    	transform:skew(35deg);
    }
    
    #myDiv {
    	transform:scale(1,0.5);
    }
    
    #myDiv {
    	transform:rotate(45deg);
    }
    
    #myDiv {
    	transform:translate(10px, 20px);
    }
    
    #myDiv {
    	transform:skew(30deg) scale(1.1,1.1) rotate(40deg) translate(10px, 20px);
    }
    
3D Syntax

    #myDiv {
    	transition:all 2s ease-in-out;
    	perspective: 800px;
    	perspective-origin: 50% 100px;
    }
    
    #myDiv:hover #rotateX {
    	transform:rotateX(180deg);
    }
    
    #myDiv:hover #rotateY {
    	transform:rotateY(180deg);
    }
    
    #myDiv:hover #rotateZ {
    	transform:rotateZ(180deg);
    }

### Animation

Taking everything we have learned.

CSS3 Transforms support 3D

* Safari 4
* Chrome 4
* FireFox 5
* Opera 12
* IE 10

Animations were first added in WebKit in 2007. In 2009, the W3C updated the working draft and other browsers later added support.

Animations add KeyFrames to tween at different times.

  @keyframes resize {
  	0% {
  		padding: 0;
  	}
  	50% {
  		padding: 0 20px;
  		background-color:rgba(255,0,0,0.2);
  	}
  	100% {
  		padding: 0 100px;
  		background-color:rgba(255,0,0,0.9);
  	}
  }

  #myDiv {
  	animation-name: resize;
  	animation-duration: 1s;
  	animation-timing-function: ease-in-out;
  	
  	animation-iteration-count: 4;   // Loop forever with `infinite` 
  	animation-direction: alternate; // `normal` or `alternate` ie: reverse on odd iterations
  	
  }

## Events
### Touch Events
### Gesture Events
## Live Demo