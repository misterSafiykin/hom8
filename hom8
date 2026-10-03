import tkinter as tk

window = tk.Tk()
window.title("Калькулятор")
window.geometry("300x400")

expression = ""

display = tk.Label(window, text="", font=("Arial", 24), anchor="e")
display.pack(fill="both", padx=10, pady=10)


def add_symbol(symbol):
    global expression
    expression += symbol
    display.config(text=expression)


def calculate():
    global expression

    try:
        result = eval(expression)
        display.config(text=result)
        expression = str(result)
    except:
        display.config(text="Помилка")
        expression = ""


def clear():
    global expression
    expression = ""
    display.config(text="")


buttons = [
    ["7", "8", "9", "/"],
    ["4", "5", "6", "*"],
    ["1", "2", "3", "-"],
    ["0", ".", "+", "="]
]

for row in buttons:
    frame = tk.Frame(window)
    frame.pack(expand=True, fill="both")

    for button in row:
        if button == "=":
            command = calculate
            text = "Результат"
        else:
            command = lambda x=button: add_symbol(x)
            text = button

        tk.Button(
            frame,
            text=text,
            font=("Arial", 14),
            command=command
        ).pack(side="left", expand=True, fill="both", padx=2, pady=2)

tk.Button(
    window,
    text="Очистити",
    font=("Arial", 14),
    command=clear
).pack(fill="both", padx=5, pady=5)

window.mainloop()
