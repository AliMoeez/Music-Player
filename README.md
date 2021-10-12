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
