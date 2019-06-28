---
layout: post
title: Shape Moving
date: 2019-04-04
excerpt: "Modify a simple Ruby program to move a shape across the screen."
tags: [code, function]
comments: true
---

###Shape Moving
Modify the provided code in the Gosu cycle update() method.
####Instruction
Use the code provided (from this task’s resources in Doubtfire) to get started.<br>
You must enhance the code provided as follows:<br>
1. The shape also can be moved up and down<br>
2. The shape does not move out of the window area<br>
<br>
A.
Fix the following code so that:
The shape also can be moved up and down the shape does not move out of the window area.
{% highlight ruby %}
require 'gosu'

module ZOrder
  BACKGROUND, MIDDLE, TOP = *0..2
end

WIDTH = 400
HEIGHT = 500
SHAPE_DIM = 50

class GameWindow < Gosu::Window
  def initialize
  end
  
  def update
  end
  
  def draw
  end
 end
window = GameWindow.new
window.show

{% endhighlight %}
<br>
B.
Initialize creates a window with a width an a height and a caption. It also sets up any variables to be used.<br>
This is procedure i.e the return value is 'undefined'.
{% highlight ruby %}
def initialize
    super WIDTH, HEIGHT, false
    self.caption = "Shape Moving"
    @HEIGHT = 30
    @WIDTH = 80

     # Create and load a font for drawing text on the screen
    @font = Gosu::Font.new(20)
    @cycle = 0

    @shape_y = HEIGHT / 2
    @shape_x = WIDTH / 2
  end
{% endhighlight %}
<br>
C.
Put any work you want done in update.
his is a procedure i.e the return value is 'undefined'.
{% highlight ruby %}
def update
    @cycle += 1
    sleep(0.1) # give a break

    if button_down?(Gosu::KbRight)
      if @shape_x != (WIDTH - SHAPE_DIM)
        @shape_x += 10
        puts "Right button has pressed"
      end
    end
    if button_down?(Gosu::KbLeft) && (@shape_x != 0)
        @shape_x -= 10
        puts "Left button has pressed"
    end
    if button_down?(Gosu::KbUp) && (@shape_y != 0 )
        @shape_y -= 10
        puts "Up button has pressed"
    end
    if button_down?(Gosu::KbDown)
        if @shape_y != (HEIGHT - SHAPE_DIM)
        @shape_y += 10
        puts "Down button has pressed."
        end
    end

  end
{% endhighlight %}
<br>
D.
Draw (or Redraw) the window
This is procedure i.e the return value is 'undefined'
{% highlight ruby %}
  def draw
    @font.draw("Cycle count: #{@cycle}", 10, 10, z = ZOrder::TOP, 1.0, 1.0, Gosu::Color::WHITE)
    Gosu.draw_rect(@shape_x, @shape_y, SHAPE_DIM, SHAPE_DIM, Gosu::Color::RED, ZOrder::TOP, mode=:default)
  end
{% endhighlight %}
<br>

E.Entire code ::
{% highlight ruby %}
require 'gosu'

module ZOrder
  BACKGROUND, MIDDLE, TOP = *0..2
end

WIDTH = 400
HEIGHT = 500
SHAPE_DIM = 50

# Instructions:
# Fix the following code so that:
# 1. The shape also can be moved up and down
# 2. the shape does not move out of the window area

class GameWindow < Gosu::Window

  # initialize creates a window with a width an a height
  # and a caption. It also sets up any variables to be used.
  # This is procedure i.e the return value is 'undefined'
  def initialize
    super WIDTH, HEIGHT, false
    self.caption = "Shape Moving"
    @HEIGHT = 30
    @WIDTH = 80

     # Create and load a font for drawing text on the screen
    @font = Gosu::Font.new(20)
    @cycle = 0

    @shape_y = HEIGHT / 2
    @shape_x = WIDTH / 2
  end

  # Put any work you want done in update
  # This is a procedure i.e the return value is 'undefined'
  def update
    @cycle += 1
    sleep(0.1) # give a break

    if button_down?(Gosu::KbRight)
      if @shape_x != (WIDTH - SHAPE_DIM)
        @shape_x += 10
        puts "Right button has pressed"
      end
    end
    if button_down?(Gosu::KbLeft) && (@shape_x != 0)
        @shape_x -= 10
        puts "Left button has pressed"
    end
    if button_down?(Gosu::KbUp) && (@shape_y != 0 )
        @shape_y -= 10
        puts "Up button has pressed"
    end
    if button_down?(Gosu::KbDown)
        if @shape_y != (HEIGHT - SHAPE_DIM)
        @shape_y += 10
        puts "Down button has pressed."
        end
    end

  end

  # Draw (or Redraw) the window
  # This is procedure i.e the return value is 'undefined'
  def draw
    @font.draw("Cycle count: #{@cycle}", 10, 10, z = ZOrder::TOP, 1.0, 1.0, Gosu::Color::WHITE)
    Gosu.draw_rect(@shape_x, @shape_y, SHAPE_DIM, SHAPE_DIM, Gosu::Color::RED, ZOrder::TOP, mode=:default)
  end
end

window = GameWindow.new
window.show

{% endhighlight %}

