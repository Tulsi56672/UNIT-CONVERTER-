from tkinter import*
from tkinter import ttk
from unitconvert import lengthunits

root =Tk()
#root.geometry("300x350")

userin=IntVar()
resultin = IntVar()
uf=StringVar()
us=StringVar()

def conv():
	a = lengthunits.LengthUnit(userin.get(),f'{uf.get()}',f'{us.get()}').doconvert()
	resultin.set(a)

head= Label(root,text="unit convert",font=('comic sans',20))
head.grid(row=0,column=0,columnspan=2)


userinput = Entry(root,textvariable=userin,font=('comic sans',20),width=10)
userinput.grid(row=1,column=0,padx=10,pady=10)

unitfirst = ttk.Combobox(root,textvariable=uf,font=('comic sans',20),width=5)
unitfirst['value'] = ('mm','cm','m','km','in','ft','yd','mi')
unitfirst.grid(row=1,column=1,padx=10,pady=10)

result = Label(root,textvariable=resultin,font=('comic sans',20))
result.grid(row=2,column=0,padx=10,pady=10)

unitsecond = ttk.Combobox(root,textvariable=us,font=('comic sans',20),width=5)
unitsecond['value'] = ('mm','cm','m','km','in','ft','yd','mi')
unitsecond.grid(row=2,column=1,padx=10,pady=10)

submit=Button(root,text="SUBMIT",font=('comic sans',15),command=conv)
submit.grid(row=3,columnspan=2,padx=10,pady=10)

reset=Button(root,text="RESET",font=('comic sans',15))
reset.grid(row=4,columnspan=2,padx=10,pady=10)


root.mainloop()
