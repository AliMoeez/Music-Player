# Music-Player

#python mp3 player made on tkinter

#contains a libaray button, where users can access and store their music
#contains a speed increase and decrease button
#contains a help guide
#contains a button that will allow user to insert link to uploard sonf with desried name

from tkinter import *
from playsound import playsound 

screen=Tk()

screen.geometry("700x500")

screen.config(bg="light salmon")

title=Label(screen,text="Music Player",bg="light salmon",font=("arial",36)).place(x=250,y=20)

def sound1():
    pass
    
    
def sound2():
    pass
    
def sound3():
    pass
    

Sounds=['1','2','3','4','5','6','7','8','9','10','11','12','13','14']

Library=StringVar(screen)
Library.set(Sounds[0])

Libr=OptionMenu(screen,Library,*Sounds)
Libr.place(x=325,y=100)

    
def play():
    
    text_play=Library.get()
    
    show_play=Label(screen,text="Currentely Playing " +text_play,bg="light salmon")
    show_play.place(x=285,y=190)
    
    sounds=Button(screen,text="▶",command=play,bg="light salmon")
    sounds.place(x=290,y=150)
    
play()

def pause():
    pause_music=Button(screen,text="■",bg="light salmon")
    pause_music.place(x=370,y=150)
    
pause()

screen.mainloop()





#code for the graph
import matplotlib.pyplot as plt
import wave
import numpy as np
from matplotlib.backends.backend_tkagg import (FigureCanvasTkAgg ,NavigationToolbar2Tk )                                     
from tkinter import *

screen=Tk()

screen.geometry("500x400")

screen.config(bg="salmon")



#creartion of the plot
x="/Users/moeezali/Desktop/Sounds/alarm1.wav"
sound=wave.open(x)

sound_change=sound.readframes(-1)
sound_change=np.frombuffer(sound_change,dtype="int16")

frames=sound.getframerate()

time=np.linspace(0,len(sound_change)/frames,num=len(sound_change))
                 
z=plt.figure(1)

az=plt.axes()


#color for bg
z.set_facecolor("xkcd:salmon")
z.set_facecolor((1.0,0.47,0.42))

#color for graph
az.set_facecolor("xkcd:salmon")
az.set_facecolor((1.0,0.47,0.42))
y=plt.plot(time,sound_change)




#code to put matlibplot on tkinter
show=FigureCanvasTkAgg(z,screen)
show.draw()

tool=NavigationToolbar2Tk(show,screen)

tool.update()

show.get_tk_widget().pack()



screen.mainloop()
