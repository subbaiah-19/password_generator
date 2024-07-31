import string
import random
from tkinter import *
def generate():
    s = ''
    l1=list(string.ascii_lowercase)
    l2=list(string.ascii_uppercase)
    l= l1+l2+[0,1,2,3,4,5,6,7,8,9]
    n = int(entry2.get())
    for i in range(n):
        s += str(random.choice(l))
    entry3.delete(0,END)
    entry3.insert(0,s)
def reset():
    entry1.delete(0,END)
    entry2.delete(0,END)
    entry3.delete(0,END)
    final1.config(text="",bg="#0af0de")
    final2.config(text="",bg="#0af0de")
window = Tk()
window.geometry("900x900")
window.config(bg="pink")
window.title("PASSWORD GENERATOR")
label1 = Label(window,
               text="Password Generator",
               font=("courier",40,"bold"),
               fg="black",
               bg="#0af0de")
label1.place(x=400,y=4)
label2 = Label(window,
               text="Enter user name: ",
               font=("courier",20,"bold"),
               fg="red",
               bg="#0af0de")
label2.place(x=250,y=150)
entry1 = Entry(window,
               font=("courier",20),
               fg = "black",
               bg = "white")
entry1.place(x=650,y=150)
label3 = Label(window,
               text="Enter password length: ",
               font=("courier",20,"bold"),
               fg="orange",
               bg="#0af0de")
label3.place(x=250,y=250)
entry2 = Entry(window,
               font=("courier",20),
               fg = "black",
               bg = "white")
entry2.place(x=650,y=250)
label4 = Label(window,
               text="Generated Password: ",
               font=("courier",20,"bold"),
               fg="yellow",
               bg="#0af0de")
label4.place(x=250,y=350)
entry3 = Entry(window,
               font=("courier",20,"bold"),
               fg = "black",
               bg = "lightyellow")
entry3.place(x=650,y=350)
button1 = Button(window,
                 text = "GENERATE PASSWORD",
                 font = ("Impact",20),
                 bg = "green",
                 fg = "white",
                 bd = 2,
                 command=generate)
button1.place(x=680,y=450)
button2 = Button(window,
                 text = "RESET",
                 font = ("Impact",17),
                 bg = "red",
                 fg = "black",
                 bd=4,
                 command=reset)
button2.place(x=780,y=550)
final1 = Label(window,bg="#0af0de")
final1.place(x=250,y=650)
final2 = Label(window,bg="#0af0de")
final2.place(x=930,y=650)
window.mainloop()
