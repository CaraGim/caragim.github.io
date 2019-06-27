---
layout: post
title: Shape Drawing
date: 2019-03-28
excerpt: "Create a program that calls procedures to draw a picture to a window."
tags: [code, function]
comments: true
---

### Shape drawing
#### Instruction
 For this task you will create a program that <br>
draws a scene using primitive shapes (triangles, rectangles, and circles).<br>
The goal of this exercise is to learn a little about how to create a program using either <br>
the Gosu or Texplay libraries (but note – texplay is not installed in the labs).<br>
Gosu is a development environment that makes it easy to create programs that <br>
use graphics, sounds, animations, networking, and other aspects relevant <br>
to creating small interactive games.
<br>
■ Use the following site to select colours for the circle (which uses RGB values):<br>
https://www.rapidtables.com/web/color/RGB_Color.html<br>
Or<br>
Use the Gosu colour constants:<br>
https://www.rubydoc.info/github/gosu/gosu/master/Gosu/Color<br>
eg: a Red circle with a radius of 50 pixels would be produced by the two statements:<br>
img = Gosu::Image.new(Circle.new(50)) img.draw(200, 200, ZOrder::TOP, 0.5, 1.0, Gosu::Color::RED)<br>
Or you could use the HEX values: img.draw(300, 50, ZOrder::TOP, 1.0, 1.0, 0xff_ff0000)<br>
See here to work out HEX values:<br>
https://www.binaryhexconverter.com/decimal-to-hex-converter<br>
The co-ordinate system works as follows:<br>

#### Reference
![](assets/img/3_3 instruction.PNG)

{% highlight ruby %}
require 'rubygems'
require 'gosu'
require './circle'

#The screen has layers: Background, middle, top
module ZOrder
  BACKGROUND, MIDDLE, TOP = *0..2
end

class DemoWindow < Gosu::Window
  def initialize
    super(640, 400, false)
  end

  def draw
    #see www.rubydoc.info/github/gosu/gosu/Gosu/Color for colours
    draw_quad(0, 0, 0xff_ffffff, 800, 0, 0xff_ffffff, 0, 600, 0xff_ffffff, 800, 600, 0xff_ffffff, ZOrder::BACKGROUND)
    draw_quad(250, 180, Gosu::Color.argb(0xff_808080), 400, 180, Gosu::Color.argb(0xff_808080), 250, 350, Gosu::Color.argb(0xff_808080), 400, 350, Gosu::Color.argb(0xff_808080), ZOrder::TOP)
    draw_triangle(200, 200, Gosu::Color::RED, 450, 200, Gosu::Color::RED, 325, 90, Gosu::Color::RED, ZOrder::TOP, mode=:default)
    #draw_rect works a bit differently:
    #Gosu.draw_rect(300, 200, 100, 50, Gosu::Color::BLACK, ZOrder::TOP, mode=:default)
   
    #Circle parameter - Radius
    img2 = Gosu::Image.new(Circle.new(50))
    #Image draw parameters - x, y, z, horizontal scale (use for ovals), vertical scale (use for ovals), colour
    #Colour - use Gosu::Image::{Colour name} or .rgb({red},{green},{blue}) or .rgba({alpha}{red},{green},{blue},)
    #Note - alpha is used for transparency.
    #drawn as an elipse (0.5 width:)
    img2.draw(0, 270, ZOrder::MIDDLE, 6.4, 2.5, Gosu::Color::GREEN)
    #drawn as a red circle:
    ##img2.draw(300, 50, ZOrder::TOP, 1.0, 1.0, 0xff_ff0000)
    #drawn as a red circle with transparency:
    ##img2.draw(300, 250, ZOrder::TOP, 1.0, 1.0, 0x64_ff0000)
    
  end
end

DemoWindow.new.show
{% endhighlight %}

Result : <br>
![](assets/img/t3_3screenshot.JPG)

