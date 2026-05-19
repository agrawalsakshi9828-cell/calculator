from sys import exception
from tkinter import *
def click(event):
    text=event.widget.cget("text")
    global scvalue
    print(text)
    if text == "=":
        if scvalue.get().isdigit():
            value=int(scvalue.get())
        else:
            try:
                value=eval(scvalue.get())
            except Exception as e:
                print(e)
                scvalue.set("error")
                screen.update()

        scvalue.set(value)
        screen.update()

    elif text == "C":
        scvalue.set("")# calculator
