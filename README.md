CSS Animated Hamburger Icon
========================

Today is raining in Italy so I thought it would be fun to build an animated hamburger icon and to teach you how to do it.

## Build the hamburger icon using CSS

I know, many of you use a font or an image to represent the hamburger icon but we can create it only using HTML and CSS. Yeyyy! 
Firstly we need to write down our markup:

``` 
<a class=”menu” href=”javascript:;”> 
    <span class=”bar1"></span> 
    <span class=”bar2"></span> 
    <span class=”bar3"></span> 
</a> 
```

and now it’s time to write the CSS (I’m a little bit obsessed with alphabetical order):

```
 .menu { 
    cursor: pointer; 
}

.menu > span { 
    background: #000; 
    border-radius: 3px; 
    display: block; 
    height: 5px; 
    margin-bottom: 5px; 
    width: 35px; 
}

.menu:hover span { 
    background: #556272 !important; 
}
```

And that’s it… now you have your CSS hamburger icon (write this little tutorial makes me hungry ;) ).
 
## Add animations to our Hamburger icon

It is veeery simple, trust me!Firstly we have to write some javascript:

```
 document.querySelector( “.menu” ).addEventListener( “click”, function() { 
    this.classList.toggle( “active” ); 
}); 
```

When an user click on our hamburger icon, our little script will add or remove the class *.active* (depends if it is present or not) from our menu div. This is possible thanks to the toggle method.

And now we have to update our style:

``` 
.menu { 
    cursor: pointer;
    transition: all 275ms ease;
}

.menu > span {
    background: #000; 
    border-radius: 3px; 
    display: block; 
    height: 5px; 
    margin-bottom: 5px; 
    transition: all 275ms ease; 
    -webkit-transition: all 275ms ease; 
    width: 35px; 
}

.menu:hover span { 
    background: #556272 !important; 
}

.menu.active { 
    transform: rotate(-45deg); 
    -webkit-transform: rotate(-45deg); 
}

.menu.active span.bar1 { 
    transform: rotate(0deg) translateY(10px); 
    -webkit-transform: rotate(0deg) translateY(10px); 
}

.menu.active span.bar2 {  
    opacity: 0; 
}

.menu.active span.bar3 {  
    transform: rotate(-90deg) translateX(10px);  
    -webkit-transform: rotate(-90deg) translateX(10px); 
} 
```

