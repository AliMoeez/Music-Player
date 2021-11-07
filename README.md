#python mp3 player made on tkinter

#contains a libaray button, where users can access and store their music
#contains a speed increase and decrease button
#contains a help guide
#contains a button that will allow user to insert link to uploard sonf with desried name
#shows the sound wave of each song played

from tkinter import *
from pygame import mixer
import wave
import numpy as np
import matplotlib.pyplot as plt
from matplotlib.backends.backend_tkagg import (FigureCanvasTkAgg ,NavigationToolbar2Tk ) 

screen=Tk()

screen.geometry("700x500")

mixer.init()

screen.config(bg="light salmon")

title=Label(screen,text="Music Player",bg="light salmon",font=("arial",36)).place(x=250,y=20)


sound1="/Users/moeezali/Desktop/Sounds.alarm1.wav"

Sounds=["--","1",'2','3','4','5','6','7','8','9','10','11','12','13','14']

Library=StringVar(screen)
Library.set(Sounds[0])

Libr=OptionMenu(screen,Library,*Sounds)
Libr.place(x=325,y=100)

from pygame import mixer

sound1='/Users/moeezali/Desktop/Sounds/alarm1.wav'

mixer.init()

 
def play():
    
    show_play=Label(screen,text="Currently Playing " +Library.get(),bg="light salmon")
    show_play.place(x=285,y=220)

    soundsz=Button(screen,text="▶",command=play,bg="light salmon")
    soundsz.place(x=315,y=150)
    
    if Library.get()==Sounds[0]:
        labelz=Label(screen,text='0')
        labelz.place(x=25,y=400)
        
    if Library.get()==Sounds[1]:
        mixer.music.load(sound1)
        mixer.music.play()
          
    if Library.get()==Sounds[2]:
        print('two')
        labelz=Label(screen,text='2')
        labelz.place(x=25,y=400)
        
    if Library.get()==Sounds[3]:
        print('three')
        labelz=Label(screen,text='3')
        labelz.place(x=25,y=400)
        
    if Library.get()==Sounds[4]:
        print('four')
        labelz=Label(screen,text='4')
        labelz.place(x=25,y=400)
        
    if Library.get()==Sounds[5]:
        print('five')
        labelz=Label(screen,text='5')
        labelz.place(x=25,y=400)
        
    
play()

def pause():
    pause_music=Button(screen,text="■",command=pause,bg="light salmon")
    pause_music.place(x=370,y=150)
    
    if Library.get() in Sounds:
        mixer.music.stop()
        
    
pause()

def graph():

    show_graph=Library.get()
    
    show_graph_al=show_graph.readframes(-1)
    show_graph_a1=np.frombuffer(show_graph_a1,dtpye="int16")
    
    frame=show_graph.getframerate()
    
    times=np.linspace(0,len(show_graph_al/frame,num=len(show_graph_a1))
    
    plot=plt.figure(1)
                      
    plot_axes=plt.axes()
                      
    plot_graph=plt.plot(times,show_graph_al)
    
    
graph()


def fast_foward():
    faster_music=Button(screen,text=">>",bg="light salmon",command=fast_foward)
    faster_music.place(x=260,y=150)
    
    if Library.get()==Sounds[0]:
        Library.set(Sounds[1]) 
   
    elif Library.get()==Sounds[1]:
        Library.set(Sounds[2])
        
    elif Library.get()==Sounds[2]:
        Library.set(Sounds[3])
        
    elif Library.get()==Sounds[3]:
        Library.set(Sounds[4])
                     
    elif Library.get()==Sounds[4]:
        Library.set(Sounds[5])
                         
    elif Library.get()==Sounds[5]:
        Library.set(Sounds[6])
                     
    elif Library.get()==Sounds[6]:
        Library.set(Sounds[7])
        
    elif Library.get()==Sounds[7]:
        Library.set(Sounds[8])
        
    elif Library.get()==Sounds[8]:
        Library.set(Sounds[9])
        
    elif Library.get()==Sounds[9]:
        Library.set(Sounds[10])
        
    elif Library.get()==Sounds[10]:
        Library.set(Sounds[11])       
         
    elif Library.get()==Sounds[11]:
        Library.set(Sounds[12])
            
    elif Library.get()==Sounds[12]:
        Library.set(Sounds[13])
        
         
    elif Library.get()==Sounds[13]:
        Library.set(Sounds[14])
        
                    
fast_foward()
    
def slow_down():
    slower_music=Button(screen,text="<<",bg="light salmon",command=slow_down)
    slower_music.place(x=420,y=150)
    
    if Library.get()==Sounds[1]:
        Library.set(Sounds[0]) 
   
    elif Library.get()==Sounds[2]:
        Library.set(Sounds[1])
        
    elif Library.get()==Sounds[3]:
        Library.set(Sounds[2])
        
    elif Library.get()==Sounds[4]:
        Library.set(Sounds[3])
                     
    elif Library.get()==Sounds[5]:
        Library.set(Sounds[4])
                         
    elif Library.get()==Sounds[6]:
        Library.set(Sounds[5])
                     
    elif Library.get()==Sounds[7]:
        Library.set(Sounds[6])
        
    elif Library.get()==Sounds[8]:
        Library.set(Sounds[7])
        
    elif Library.get()==Sounds[9]:
        Library.set(Sounds[8])
        
    elif Library.get()==Sounds[10]:
        Library.set(Sounds[9]) 
        
    elif Library.get()==Sounds[11]:
        Library.set(Sounds[10]) 
         
    elif Library.get()==Sounds[12]:
        Library.set(Sounds[11]) 
         
    elif Library.get()==Sounds[13]:
        Library.set(Sounds[12])
         
    elif Library.get()==Sounds[14]:
        Library.set(Sounds[13])
        

slow_down()

def skip():
    skip_music=Button(screen,text="(>",bg="light salmon",command=skip)
    skip_music.place(x=340,y=180)
    
    if Library.get()==Sounds[0]:
        Library.set(Sounds[1]) 
   
    elif skip:
        choice=random.choice(Sounds)
        if choice==Sounds[0]:
            choice=random.choice(Sounds)
        else:
            Library.set(choice)
    

skip()

    

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
first=(r"C:\Users\Owner\Desktop\Depths.wav")

sound_wave=wave.open(first)

sound_wave_change=sound_wave.readframes(-1)
sound_wave_change=np.frombuffer(sound_wave_change,dtype="int16")

frame=sound_wave.getframerate()

times=np.linspace(0,len(sound_wave_change)/frame,num=len(sound_wave_change))

plot=plt.figure(1)

plot_ax=plt.axes()

plotz=plt.plot(times,sound_wave_change)
