# Calculate.
Uma calculadora 

#importando Tkinter
import tkinter as tk
from tkinter import *
from tkinter import ttk
import select as sl

# cores

cor1 = "#0e0b24" #preto
cor2 = "#404047" #cinza
cor3 = "#ffffff" #branco
cor4 = "#e66210" #laranja
cor5 = "#40438f" #azul
cor6 = "#39e02d" #verde


# tela
janela = Tk()
janela.title("Calculadora")
janela.geometry("320x450")
janela.config(bg = cor2)

frame_tela = Frame(janela, width=320, height= 100, bg = cor5 )
frame_tela.grid(row = 0, column = 0)

frame_corpo = Frame(janela, width=320, height= 450)
frame_corpo.grid(row = 1, column = 0)

# info que aprece na tela

#para armazenar todas as expressões que serão avaliadas
todos_valores = ""

# para entrada de valor único
valor_texto = StringVar()
################# Funções ####################

def entrar_valor(event):
    global todos_valores

    todos_valores = todos_valores + str(event)
    valor_texto.set(todos_valores)

def calcular():
    global todos_valores
    resultado = str(eval(todos_valores))
    valor_texto.set(resultado)
    todos_valores = ""



# criando label

valor_texto = StringVar()

app_label = Label(frame_tela, textvariable = valor_texto, width = 30, height = 5, padx = 10, relief = FLAT, anchor = "e", font = ("Ivy 12 bold"), justify=LEFT, bg = cor5)
app_label.place(x = 0, y = 0)


b_1 = Button(frame_corpo,command = lambda: limpar_tela(), text = "C", width = 15, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_1.place(x = 0, y = 0)

b_2 = Button(frame_corpo,command = lambda: entrar_valor('%'), text="%", width=8, height=3, bg= cor3, fg=cor1,font=('Ivy 13 bold'),relief=RAISED, overrelief=RIDGE)
b_2.place(x = 150, y = 0)

b_3 = Button(frame_corpo,command = lambda: entrar_valor('/'), text = "/", width = 10, height = 3, bg = cor4, fg=cor3, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_3.place(x = 240, y = 0)

b_4 = Button(frame_corpo,command = lambda: entrar_valor('7'), text = "7", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_4.place(x = 0, y = 70)

b_5 = Button(frame_corpo,command = lambda: entrar_valor('8'), text = "8", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_5.place(x = 75, y = 70)

b_6 = Button(frame_corpo,command = lambda: entrar_valor('9'), text = "9", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_6.place(x = 150, y = 70)

b_7 = Button(frame_corpo,command = lambda: entrar_valor('*'), text = "*", width = 11, height = 3, bg = cor4, fg=cor3, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_7.place(x = 240, y = 70)

b_8 = Button(frame_corpo,command = lambda: entrar_valor('4'), text = "4", width = 7, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_8.place(x = 0, y = 140)

b_9 = Button(frame_corpo,command = lambda: entrar_valor('5'), text = "5", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_9.place(x = 75, y = 140)

b_10 = Button(frame_corpo,command = lambda: entrar_valor('6'), text = "6", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_10.place(x = 150, y = 140)

b_11 = Button(frame_corpo,command = lambda: entrar_valor('-'), text = "-", width = 11, height = 3, bg = cor4, fg=cor3, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_11.place(x = 240, y = 140)

b_8 = Button(frame_corpo,command = lambda: entrar_valor('1'), text = "1", width = 7, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_8.place(x = 0, y = 210)

b_9 = Button(frame_corpo,command = lambda: entrar_valor('2'), text = "2", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_9.place(x = 75, y = 210)

b_10 = Button(frame_corpo,command = lambda: entrar_valor('3'), text = "3", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_10.place(x = 150, y = 210)

b_11 = Button(frame_corpo,command = lambda: entrar_valor('+'), text = "+", width = 11, height = 3, bg = cor4, fg=cor3, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_11.place(x = 240, y = 210)

b_12 = Button(frame_corpo,command = lambda: entrar_valor('0'), text = "0", width = 15, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_12.place(x = 0, y = 280)

b_13 = Button(frame_corpo,command = lambda: entrar_valor('-'), text = "-", width = 8, height = 3, bg = cor3, fg=cor1, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_13.place(x = 150, y = 280)

b_14 = Button(frame_corpo,command = lambda: calcular(), text = "=", width = 11, height = 3, bg = cor4, fg=cor3, font = ("Ivy 13 bold"), relief = RAISED, overrelief = RIDGE)
b_14.place(x = 240, y = 280)

def limpar_tela(): 
    global todos_valores
    todos_valores = "" 
    valor_texto.set("")

janela.mainloop()

#Fim.























