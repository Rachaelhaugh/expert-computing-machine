# expert-computing-machine
#GW application

from tkinter import *

class ShoppingGW:

    def __init__(self):

        window = Tk() # Create a window

        window.title("ShoppingGw") # Set title of a window

        Label(window, text = "First name").grid(row = 1, column = 1, sticky = W)                     

        Label(window, text = "Last name").grid(row = 2, column = 1, sticky = W)                     

        Label(window, text = "Choose product").grid(row = 3, column = 1, sticky = W)

        Label(window, text = "Price").grid(row = 4, column = 1, sticky = W)

        Label(window, text = "Quantity").grid(row = 5, column = 1, sticky = W)

        Label(window, text = "Tax rate 13%").grid(row = 6, column = 1, sticky = W)
        self.cusnameVar = StringVar()
        
        Label(window, text = "Total Payment ($)").grid(row = 7, column = 1, sticky = W)
        
        self.firstnameVar = StringVar()

        Entry(window, textvariable = self.firstnameVar,justify = RIGHT).grid(row = 1, column = 2)

        self.lastnameVar = StringVar()
        Entry(window, textvariable = self.lastnameVar,justify = RIGHT).grid(row = 2, column = 2)

        self.productnameVar = StringVar()
        Entry(window, textvariable = self.productnameVar, justify = RIGHT).grid(row = 3, column = 2)

        self.productpriceVar = StringVar()

        Entry(window, textvariable = self.productpriceVar, justify = RIGHT).grid(row = 4, column = 2)

        self.productquantityVar = StringVar()

        Entry(window, textvariable = self.productquantityVar, justify = RIGHT).grid(row = 5, column = 2)

        self.totalPaymentVar = StringVar()

        Label(window, textvariable = self.totalPaymentVar).grid(row = 7, column = 2, sticky = E)

        Button(window, text = "Compute Payment", command = self.totalPayment).grid(row = 8, column = 2, sticky = E)
        window.mainloop()


    def totalPayment(self):
        totalPayment = float(self.productpriceVar.get()) * int(self.productquantityVar.get())*1.13
        self.totalPaymentVar.set(format(totalPayment, '10.2f'))
        return totalPayment

ShoppingGW()
