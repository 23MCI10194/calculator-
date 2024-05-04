from tkinter import *
class Calculator:
 def __init__(self, root):
 self.root = root
 self.current_expression = ""
 self.display_var = StringVar()
 self.create_widgets()
 def create_widgets(self):
 self.root.title("Calculator")
 self.root.geometry("300x400")
 # Display for showing the expression/result
 display = Label(self.root, textvariable=self.display_var, font=('consolas', 20), 
bg="white", width=15, height=2, anchor='e')
 display.pack(pady=10)
 # Frame for buttons
 frame = Frame(self.root)
 frame.pack()
 # Button layout
 buttons = [
 [("7", self.append_to_expression), ("8", self.append_to_expression), ("9", 
self.append_to_expression), ("/", self.append_to_expression)],
 [("4", self.append_to_expression), ("5", self.append_to_expression), ("6", 
self.append_to_expression), ("*", self.append_to_expression)],
 [("1", self.append_to_expression), ("2", self.append_to_expression), ("3", 
self.append_to_expression), ("-", self.append_to_expression)],
 [("0", self.append_to_expression), (".", self.append_to_expression), ("=", 
self.calculate_result), ("+", self.append_to_expression)],
 ]
 # Create buttons in the grid
 for r, row in enumerate(buttons):
 for c, (text, func) in enumerate(row):
 Button(frame, text=text, height=2, width=6, font=(35,), command=lambda t=text, 
f=func: f(t)).grid(row=r, column=c)
 # Clear button
 clear_button = Button(self.root, text="Clear", height=2, width=12, font=(35,), 
command=self.clear_expression)
 clear_button.pack(pady=10)
 def append_to_expression(self, value):
 self.current_expression += value
 self.display_var.set(self.current_expression)
 def calculate_result(self):
 try:
 if self.current_expression:
 result = eval(self.current_expression) # Caution: eval can be dangerous; use with 
care
 self.display_var.set(str(result))
 self.current_expression = str(result)
 except ZeroDivisionError:
 self.display_var.set("Cannot divide by zero")
 self.current_expression = ""
 except SyntaxError:
 self.display_var.set("Syntax Error")
 self.current_expression = ""
 except Exception:
 self.display_var.set("Error")
 self.current_expression = ""
 def clear_expression(self):
 self.display_var.set("")
 self.current_expression = ""
if __name__ == "__main__":
 root = Tk()
 calculator = Calculator(root)
 root.mainloop()
