#dicechallenge
#Analog and Digital Dice Challenge
#dice example
from adafruit_circuitplayground import cp
import time
import random

def dice():
    i = 1
    roll=(random.randint(1,6)) #create randomization here
    while i<=6:
        
        if (roll==i):       #here's a one but you need 6 combos for a dice
            cp.pixels[i+1]=(50, 0, 0) 
        time.sleep(1.0)
        cp.pixels.fill((0, 0, 0))
        i+=1

while True:

    if cp.shake(shake_threshold=12):
        print("Shake detected!")
        dice()
        cp.red_led = True
        
    else:
        cp.red_led = False
