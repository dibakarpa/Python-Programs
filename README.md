
import tkinter as tk  #Imports the Tkinter library and gives it a short name tk
***
Tkinter is used to create GUI applications like:
Windows
Buttons
Labels
Textboxes
***
from tkinter import messagebox #Imports the messagebox feature from Tkinter.
***
Why used from tkinter import messagebox?
To show popup messages:
Errors
Warnings
Information messages
***


# Main Window 
root = tk.Tk()    #A blank GUI window appears.
root.title("Basic Python Programs App") #Sets the title of the window.
root.geometry("500x600") #Sets the window size.
root.configure(bg="lightblue")  #Changes background color of the window.

# Title
label = tk.Label(root, text="Python Mini Projects App", font=("Arial", 20, "bold"), bg="lightblue") #Creates a text label.
label.pack(pady=10) #Displays the label on screen. Pack() Places widget automatically. Pady=10 Adds vertical spacing of 10 pixels.

# Input Field
entry = tk.Entry(root, font=("Arial", 14)) #Creates a textbox where user can type.
entry.pack(pady=10) #Displays textbox on screen.

# Result Label
result_label = tk.Label(root, text="Result will appear here", font=("Arial", 14), bg="lightblue") #Creates another label to display output.
result_label.pack(pady=10)

# Add Two Numbers

def add_numbers():
    try:
        nums = entry.get().split()  #entry.get() Gets text from textbox and Splits text using spaces.
        a = int(nums[0])
        b = int(nums[1])
        result_label.config(text=f"Sum = {a + b}")
    except:
        messagebox.showerror("Error", "Enter two numbers separated by space")

# Even or Odd

def even_odd():
    try:
        num = int(entry.get())
        if num % 2 == 0:
            result_label.config(text="Even Number")
        else:
            result_label.config(text="Odd Number")
    except:
        messagebox.showerror("Error", "Enter a valid number")

# Factorial

def factorial():
    try:
        num = int(entry.get())
        fact = 1
        for i in range(1, num + 1):
            fact *= i
        result_label.config(text=f"Factorial = {fact}")
    except:
        messagebox.showerror("Error", "Enter a valid number")

# Prime Number

def prime_check():
    try:
        num = int(entry.get())

        if num > 1:
            for i in range(2, num):
                if num % i == 0:
                    result_label.config(text="Not Prime")
                    return
            result_label.config(text="Prime Number")
        else:
            result_label.config(text="Not Prime")
    except:
        messagebox.showerror("Error", "Enter a valid number")

# Fibonacci Series

def fibonacci():
    try:
        n = int(entry.get())
        a, b = 0, 1
        series = ""

        for i in range(n):
            series += str(a) + " "
            a, b = b, a + b

        result_label.config(text=series)
    except:
        messagebox.showerror("Error", "Enter a valid number")

# Reverse String

def reverse_string():
    text = entry.get()
    result_label.config(text=text[::-1])

# Palindrome Check

def palindrome():
    text = entry.get()

    if text == text[::-1]:
        result_label.config(text="Palindrome")
    else:
        result_label.config(text="Not Palindrome")

# Buttons

btn1 = tk.Button(root, text="Add Numbers", width=20, command=add_numbers) #Creates a button.
btn1.pack(pady=5)

btn2 = tk.Button(root, text="Even / Odd", width=20, command=even_odd)
btn2.pack(pady=5)

btn3 = tk.Button(root, text="Factorial", width=20, command=factorial)
btn3.pack(pady=5)

btn4 = tk.Button(root, text="Prime Check", width=20, command=prime_check)
btn4.pack(pady=5)

btn5 = tk.Button(root, text="Fibonacci", width=20, command=fibonacci)
btn5.pack(pady=5)

btn6 = tk.Button(root, text="Reverse String", width=20, command=reverse_string)
btn6.pack(pady=5)

btn7 = tk.Button(root, text="Palindrome", width=20, command=palindrome)
btn7.pack(pady=5)

# Run App
root.mainloop()
