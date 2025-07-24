# Digital-clock
from tkinter import Label, Tk
import time

# Create window
root = Tk()
root.title("Digital Clock")
root.geometry("350x100")
root.resizable(False, False)
root.configure(bg="black")

# Create time label
clock_label = Label(root, bg="black", fg="cyan", font=("Arial", 40, 'bold'))
clock_label.place(x=20, y=20)

# Update time every second
def update_time():
    current_time = time.strftime('%H:%M:%S')
    clock_label.config(text=current_time)
    clock_label.after(1000, update_time)

update_time()
root.mainloop()
