---
layout: post
title: Gosu Cycle
date: 2019-04-02
excerpt: "Use the Gosu cycle to manipulate moving widgets on the screen."
tags: [code, function]
comments: true
---

### Gosu Cycle
#### Overview
Modify the tasks in the Gosu cycle update() and draw() methods.
#### Instruction
■ Add a variable in the initialize() method called shape_x with the initial value of zero.<br>
■ Add code into the update() method that will add 10 to shape_x.<br>
■ Add code into the draw() method that will draw a shape (square or circle of any visible colour) at the y coordinate of 30 and x coordinate of shape_x.<br>
<br>
◈Build program structure roughly
{% highlight ruby %}
class GameWindow < Gosu::Window

  def initialize
  end
 
  def update
  end
 
  def button_down
  end
 
  def draw
  end
end
window = GameWindow.new
window.show
{% endhighlight %}
<br>
<br>
◈ Initialize the elements: window width and height size and a caption.
◈ It also possible to any variables to be used.
◈ This is procedure i.e the return value is 'undefined'.
{% highlight ruby %}
 def initialize
    super 200, 135, false
    self.caption = "Gosu Cycle Example"
    @shape_x = 0 # x coordinate

    #Create and load an image to display
    @background_image = Gosu::Image.new("media/earth.png")

    #Create and load a font for drawing text on the screen
    @font = Gosu::Font.new(20)
    @cycle = 0
    puts "0. In initialize\n"
  end
  {% endhighlight %}
  <br>
  <br>
  ◈ Put any work you want done in update.
  ◈ This is a procedure i.e the return value is 'undefined'.
  {% highlight ruby %}
   def update
  	puts "1. In update. Sleeping for one second\n"
    @cycle += 1 # add one to the current value of cycle
    sleep(1)
    @shape_x += 10 # add 10 to the current value of x coordinate
  end
  {% endhighlight %}
  <br>
  <br>
  ◈ The following method is called when you press a mouse.
  ◈ Button or key.
  {% highlight ruby %}
   def button_down(id)
    puts "In Button Down " + id.to_s
  end
  {% endhighlight %}
  <br>
  <br>
  ◈ Draw (or Redraw) the window
  ◈ This is procedure i.e the return value is 'undefined'.
  {% highlight ruby %}
  def draw
    # Draws an image with an x, y and z
    #(z determines if it sits on or under other things that are drawn)
    @background_image.draw(0, 0, z = ZOrder::BACKGROUND)
    @font.draw("Cycle count: #{@cycle}", 10, 10, z = ZOrder::TOP, 1.0, 1.0, Gosu::Color::BLACK)
    puts "2. In draw\n"

    draw_quad(@shape_x, 30, Gosu::Color::GREEN, @shape_x + 50, 30, Gosu::Color::GREEN, @shape_x+60, 100, Gosu::Color::WHITE, @shape_x+120,100, Gosu::Color::WHITE, ZOrder::TOP, mode=:default)
  end
  {% endhighlight %}
  
  

