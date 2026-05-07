# Cada vez que presiones ESPACIO se revelan más dígitos de Pi

import tkinter as tk

pi = (
    "3.14159265358979323846264338327950288419716939937510"
    "58209749445923078164062862089986280348253421170679"
    "82148086513282306647093844609550582231725359408128"
    "48111745028410270193852110555964462294895493038196"
)

cantidad = 1

def revelar(event):
    global cantidad
    cantidad += 5  # muestra 5 números más cada vez
    texto.config(text=pi[:cantidad])

ventana = tk.Tk()
ventana.title("Muro de Pi")
ventana.geometry("800x300")
ventana.configure(bg="black")

titulo = tk.Label(
    ventana,
    text="Presiona ESPACIO para revelar Pi",
    fg="lime",
    bg="black",
    font=("Consolas", 18)
)
titulo.pack(pady=20)

texto = tk.Label(
    ventana,
    text=pi[:cantidad],
    fg="white",
    bg="black",
    wraplength=760,
    font=("Consolas", 16)
)
texto.pack(pady=20)

ventana.bind("<space>", revelar)

ventana.mainloop()
