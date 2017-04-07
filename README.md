# tic-tac-toe
Tic-Tac-Toe game in Python.
from tkinter import *
import tkinter.messagebox
tk=None

click=True
loop=True
button1=None
button2=None
button3=None
button4=None
button5=None
button6=None
button7=None
button8=None
button9=None

def checker(buttons):
    global click,loop,button1,button2,button3,button4,button5,button6,button7,button8,button9
    if buttons["text"]==" " and click==True:
        buttons["text"]="X"
        click=False
    elif buttons["text"]==" " and click==False:
        buttons["text"]="O"
        click=True
    if(button1["text"]=="X" and button2["text"]=="X" and button3["text"]=="X" or
        button4["text"]=="X" and button5["text"]=="X" and button6["text"]=="X" or
        button7["text"]=="X" and button8["text"]=="X" and button9["text"]=="X" or
        button1["text"]=="X" and button5["text"]=="X" and button9["text"]=="X" or
        button3["text"]=="X" and button5["text"]=="X" and button7["text"]=="X" or
        button1["text"]=="X" and button4["text"]=="X" and button7["text"]=="X" or
        button2["text"]=="X" and button5["text"]=="X" and button8["text"]=="X" or
        button3["text"]=="X" and button6["text"]=="X" and button9["text"]=="X"):
        tkinter.messagebox.showinfo("Winner X:You won the game")
        loop=True
        tk.destroy()

    elif(button1["text"]=="O" and button2["text"]=="O" and button3["text"]=="O" or
        button4["text"]=="O" and button5["text"]=="O" and button6["text"]=="O" or
        button7["text"]=="O" and button8["text"]=="O" and button9["text"]=="O" or
        button1["text"]=="O" and button5["text"]=="O" and button9["text"]=="O" or
        button3["text"]=="O" and button5["text"]=="O" and button7["text"]=="O" or
        button1["text"]=="O" and button4["text"]=="O" and button7["text"]=="O" or
        button2["text"]=="O" and button5["text"]=="O" and button8["text"]=="O" or
        button3["text"]=="O" and button6["text"]=="O" and button9["text"]=="O"):
        tkinter.messagebox.showinfo("Winner O:You won the game")
        loop=True
        tk.destroy()
    elif(not(button1["text"]==" " or
        button2["text"]==" " or
        button3["text"]==" " or
        button4["text"]==" " or
        button5["text"]==" " or
        button6["text"]==" " or
        button7["text"]==" " or
        button8["text"]==" " or
        button9["text"]==" ")):
        tkinter.messagebox.showinfo("Draw")
        loop=True
        tk.destroy()

def init():
    global tk,click,button1,button2,button3,button4,button5,button6,button7,button8,button9
    #buttons=StringVar()

    button1=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button1))
    button1.grid(row=0,column=0,sticky=S+N+E+W)

    button2=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button2))
    button2.grid(row=0,column=1,sticky=S+N+E+W)

    button3=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button3))
    button3.grid(row=0,column=2,sticky=S+N+E+W)

    button4=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button4))
    button4.grid(row=1,column=0,sticky=S+N+E+W)

    button5=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button5))
    button5.grid(row=1,column=1,sticky=S+N+E+W)

    button6=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button6))
    button6.grid(row=1,column=2,sticky=S+N+E+W)

    button7=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button7))
    button7.grid(row=2,column=0,sticky=S+N+E+W)

    button8=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button8))
    button8.grid(row=2,column=1,sticky=S+N+E+W)

    button9=Button(tk,text=" ",font=('Times 26 bold'),height=4,width=8,command=lambda:checker(button9))
    button9.grid(row=2,column=2,sticky=S+N+E+W)

while loop:
    loop=False
    tk=Tk()
    tk.title("Tic Tac Toe")
    click=True
    init()
    tk.mainloop()

