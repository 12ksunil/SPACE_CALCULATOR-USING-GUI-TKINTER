# SPACE_CALCULATOR-USING-GUI-TKINTER
from tkinter import *
import tkinter.messagebox as tmsg
root=Tk()
root.geometry("890x400")
root.title("Stage2 - Astronout Mass Calculator")
root.configure(background="grey",borderwidth=4,relief=SOLID,highlightbackground="white",highlightcolor="BLACK")


l1=Label(root,text="DESTINATIONS" , font="comicsanssm 13 bold",background="grey")
l1.grid(row=0,column=0,padx=23,pady=23)
l2=Label(root,text="Max. Tool Weights" , font="comicsanssm 13 bold",background="grey")
l2.grid(row=0,column=1,padx=43,pady=23)
l3=Label(root,text="Tool Weight" , font="comicsanssm 13 bold",background="grey")
l3.grid(row=0,column=2,padx=63,pady=23)
l4=Label(root,text="Available" , font="comicsanssm 13 bold",background="grey")
l4.grid(row=0,column=3,padx=0,pady=23)
l5=Label(root,text="Crew:100kg",font="comicsanssm 10 bold",background="grey")
l5.grid(row=1,column=1)
l6=Label(root,text="Mission Specialist:150kg",font="comicsanssm 10 bold",background="grey")
l6.grid(row=4,column=1)
fr=Frame(root)
fr.grid(row=1,column=0,padx=34)
sbr=Scrollbar(fr)
sbr.pack(side=RIGHT,fill=BOTH)
lbx=Listbox(fr,yscrollcommand=sbr.set)
itemsforlbx=['Mercury','Venus','Moon','Mars','IO','Europa','Ganymede','Callisto']
for items in itemsforlbx:
 lbx.insert(END,items)
#lbx.bind('<Double-1>',go)
#lbx.location(x=20,y=90)
lbx.pack()
lbx.configure(width=0,height=5)
sbr.config(command=lbx.yview)


def calculate():
 # global T1,T2,T3,T4,T5,T6
 try:
  float(T1.get())
 except ValueError:
  tmsg.showinfo("T1", "Please enter a number ")

 #    print(T1.get())
 #   print(T2.get())
 #  print(T3.get())
 # print(T4.get())
 # print(T5.get())
 # print(T6.get())
 r1 = int(T1.get())
 sum = 100 - r1
 a1.config(text=sum)
 r2 = int(T2.get())
 sum1 = sum - r2
 a2.config(text=sum1)
 # tmsg.showinfo("T2", "Please enter a remaining value because total wight of crew is 100kg ")
 r3 = int(T3.get())
 # if r3==sum1:
 sum2 = sum1 - r3
 a3.config(text=sum2)
 # else:
 #  tmsg.showinfo("T3", "Please enter a previous remaining value because total wight of crew is 100kg ")
 r4 = int(T4.get())
 sum3 = 150 - r4
 a4.config(text=sum3)
 r5 = int(T5.get())
 sum4 = sum3 - r5
 a5.config(text=sum4)
 r6 = int(T6.get())
 sum5 = sum4 - r6
 a6.config(text=sum5)
 sum6 = sum2 + sum5
 total.config(text=sum6)
 R1 = (sum6) / 6
 result3.config(text=R1)
 v1 = lbx.curselection()[0]
 if v1 == 0:
  R1 = R1 * 0.378
  result2.config(text=R1)
 elif v1 == 1:
  R1 = R1 * 0.907
  result2.config(text=R1)
 elif v1 == 2:
  R1 = R1 * 0.166
  result2.config(text=R1)
 elif v1 == 3:
  R1 = R1 * 0.377
  result2.config(text=R1)
 elif v1 == 4:
  R1 = R1 * 0.1835
  result2.config(text=R1)
 elif v1 == 5:
  R1 = R1 * 0.1335
  result2.config(text=R1)
 elif v1 == 6:
  R1 = R1 * 0.1448
  result2.config(text=R1)
 else:
  R1 = R1 * 0.1264
  result2.config(text=R1)
def exit():
 root.destroy()

b = Button(root, background="grey", text="Calculate", bg="light blue", borderwidth=2, relief=SUNKEN, command=calculate)
b.grid(row=7,column=0, padx=4)

def go(event):
 cs=lbx.curselection()[0]
 T['text']=lbx.get(cs)
 print(type(cs),"kkk")
 if cs == 0:
  T.config(text="Mass Multiplier for Mercury is 0.378")
 elif cs == 1:
  T.config(text="Mass Multiplier for Venus is 0.907")
 elif cs == 2:
  T.config(text="Mass Multiplier for Moon is 0.166")
 elif cs == 3:
  T.config(text="Mass Multiplier for Mars is 0.377")
 elif cs == 4:
  T.config(text="Mass Multiplier for IO is 0.1835")
 elif cs == 5:
  T.config(text="Mass Multiplier for Europa is 0.1335")
 elif cs == 6:
  T.config(text="Mass Multiplier for Ganymede is 0.1448")
 else :
  T.config(text="Mass Multiplier for Callisto is 0.1264")



b = Button(root, background="grey", text="Exit", bg="light blue", borderwidth=2, relief=SUNKEN, command=exit)
b.grid(row=7,column=1)
a1=Label(root,bg="grey",width=3,text="-")
a1.grid(row=1,column=3,pady=3)
a2=Label(root,bg="grey",width=3,text="-")
a2.grid(row=2,column=3,pady=3)
a3=Label(root,bg="grey",width=3,text="-")
a3.grid(row=3,column=3,pady=3)
a4=Label(root,bg="grey",width=3,text="-")
a4.grid(row=4,column=3,pady=3)
a5=Label(root,bg="grey",width=3,text="-")
a5.grid(row=5,column=3,pady=3)
a6=Label(root,bg="grey",width=3,text="-")
a6.grid(row=6,column=3,pady=3)
total=Label(root,bg="white",width=4,text="Total")
total.grid(row=7,column=3)
T1=StringVar()
T2=StringVar()
T3=StringVar()
T4=StringVar()
T5=StringVar()
T6=StringVar()
t1=Entry(root,width=5,textvariable=T1,validate="key")
t1.grid(row=1,column=2,pady=3)
t2=Entry(root,width=5,textvariable=T2,validate="key")
t2.grid(row=2,column=2,pady=3)
t3=Entry(root,width=5,textvariable=T3,validate="key")
t3.grid(row=3,column=2,pady=3)
t4=Entry(root,width=5,textvariable=T4,validate="key")
t4.grid(row=4,column=2,pady=3)
t5=Entry(root,width=5,textvariable=T5,validate="key")
t5.grid(row=5,column=2,pady=3)
t6=Entry(root,width=5,textvariable=T6,validate="key")
t6.grid(row=6,column=2,pady=3)

#
T=Label(root,text="Mass Multiplier for ",bg="grey",font="comicsanssm 10 bold")
T.grid(row=7,column=2)
result=Label(root,text="Average available weight is:",bg="grey",font="comicsanssm 10 bold")
result.grid(row=8,column=2)
result3=Label(root,text="",bg="grey",font="comicsanssm 10 bold")
result3.grid(row=9,column=2)
result1=Label(root,text="Equivalent Average on Destination:",bg="grey",font="comicsanssm 10 bold")
result1.grid(row=8,column=3)
result2=Label(root,text="",bg="grey",font="comicsanssm 10 bold")
result2.grid(row=9,column=3)




root.mainloop()
