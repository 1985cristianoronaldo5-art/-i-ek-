import turtle
import math
import time

turtle.bgcolor("black")
turtle.tracer(0, 0)

pen = turtle.Turtle()
pen.hideturtle()
pen.speed(0)

def draw_flower(bloom):
    pen.clear()
    pen.up()
    pen.goto(0, -20)
    pen.down()

    # Merkez (çiçeğin ortası)
    pen.color("yellow")
    pen.begin_fill()
    pen.circle(20)
    pen.end_fill()

    # Yapraklar
    petals = 8
    for i in range(petals):
        pen.up()
        pen.goto(0,0)
        pen.setheading(360/petals * i)
        pen.forward(10)

        pen.color("pink")
        pen.begin_fill()
        pen.down()

        length = 40 + bloom * 60  # açılma efekti
        width = 10 + bloom * 25

        pen.left(45)
        pen.forward(length)
        pen.circle(width, 90)
        pen.left(90)
        pen.circle(width, 90)
        pen.forward(length)
        pen.left(45)

        pen.end_fill()

while True:
    for i in range(0, 100):
        draw_flower(i/100)
        turtle.update()
        time.sleep(0.02)

    for i in range(100, 0, -1):
        draw_flower(i/100)
        turtle.update()
        time.sleep(0.02)

        
