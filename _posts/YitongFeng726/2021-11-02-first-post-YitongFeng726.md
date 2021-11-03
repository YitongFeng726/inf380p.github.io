---
layout: post
author: YitongFeng726
title: "YitongFeng's first post!"
--- 
  
#link
<iframe src="https://trinket.io/embed/python3/d62effbcb9" width="100%" height="356" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>

#code
from turtle import *
def curvemove():
    for i in range(200):
        right(1)
        forward(1)
color('pink')        
begin_fill()
left(140)
forward(111.65)
curvemove()
left(120)
curvemove()
forward(111.65)
end_fill()
done()

#reflection:here I want to show a pink heart graph. I was confused about how to draw curve in turtle so I googled and it suggested me to define a curvemove function. also I tried many times in define the number of range. I also have a question in trinket.  why my code doesn't work in the configuration of python3 but works for pythpn. And below I listed the reference. https://www.quora.com/How-can-I-draw-a-heart-using-Python 
