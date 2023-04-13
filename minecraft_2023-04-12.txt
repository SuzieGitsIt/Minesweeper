# File:     minecraft_2023-04-12
# Version:  0.0.01
# Author:   Susan Haynes
# Comments/Notes:
#   (0,0) coordinates are the top left corner of the screen for 1920x1080
#   (0,0) coordinates are the bottom right corner of the screen for 1919x1079
# Online References:
#       https://stackoverflow.com/questions/65325062/change-colour-of-tkinter-button-created-in-a-loop
import tkinter as tk                            # Tkinter's Tk class
import tkinter.ttk as ttk                       # Tkinter's Tkk class
from functools import partial
import math
import sys
import array
import numpy as np

#####################################          START NEW POP UP WINDOW             #####################################
GUI = tk.Tk()
GUI.title("Sample Numbers")
GUI.geometry('380x750')
GUI.configure(background='white')  # Set background color
GUI.option_add('*Font', 'Helvetica 11')  # set the font and size for entire GUI
GUI.option_add('*foreground', 'black')  # set the text color, hex works too '#FFFFFF'
GUI.option_add('*background', 'white')  # set the background to white

###########################################          BODY OF CODE             ##########################################
lbl_dis_s1 = tk.Label(GUI, text="Sample Set #1: ").place(x=20, y=350)
lbl_dis_s2 = tk.Label(GUI, text="Sample Set #2: ").place(x=20, y=390)
lbl_dis_s3 = tk.Label(GUI, text="Sample Set #3: ").place(x=20, y=430)
lbl_dis_s4 = tk.Label(GUI, text="Sample Set #4: ").place(x=20, y=470)
lbl_dis_s5 = tk.Label(GUI, text="Sample Set #5: ").place(x=20, y=510)
lbl_dis_s6 = tk.Label(GUI, text="Sample Set #6: ").place(x=20, y=550)
lbl_dis_s7 = tk.Label(GUI, text="Sample Set #7: ").place(x=20, y=590)
lbl_dis_s8 = tk.Label(GUI, text="Sample Set #8: ").place(x=20, y=630)
lbl_dis_s9 = tk.Label(GUI, text="Sample Set #9: ").place(x=20, y=670)
lbl_dis_s10 = tk.Label(GUI, text="Sample Set #10: ").place(x=20, y=710)

lbl_out_s1 = tk.Label(GUI, text="minecraft Output").place(x=145, y=360,anchor='w')
lbl_out_s2 = tk.Label(GUI, text="Test").place(x=145, y=400,anchor='w')
lbl_out_s3 = tk.Label(GUI, text="Test").place(x=145, y=440,anchor='w')
lbl_out_s4 = tk.Label(GUI, text="Test").place(x=145, y=480,anchor='w')
lbl_out_s5 = tk.Label(GUI, text="Test").place(x=145, y=520,anchor='w')
lbl_out_s6 = tk.Label(GUI, text="Test").place(x=145, y=560,anchor='w')
lbl_out_s7 = tk.Label(GUI, text="Test").place(x=145, y=600,anchor='w')
lbl_out_s8 = tk.Label(GUI, text="Test").place(x=145, y=640,anchor='w')
lbl_out_s9 = tk.Label(GUI, text="Test").place(x=145, y=680,anchor='w')
lbl_out_s10 = tk.Label(GUI, text="Align West").place(x=145, y=720,anchor='w')
#####################################           BUTTON PRESS STYLE         #############################################
# style = ttk.Style()
# style.theme_use('default')  # alt, default, clam and classic
#
# style.map('T.TButton', background=[('active', 'pressed', 'white'), ('!active', 'white'), ('active', '!pressed', 'grey')])   # active, not active, not pressed
# style.map('T.TButton', relief=[('pressed', 'sunken'), ('!pressed', 'raised')])  # pressed, not pressed
# style.configure('T.TButton', font=('Helvetica', '10'))
#
# style.map('P.TButton', background=[('active', 'pressed', '#FF69B4'), ('!active', 'white'), ('active', '!pressed', 'grey')])  # Press me Button always hot pink when pressed
# style.map('P.TButton', relief=[('pressed', 'sunken'), ('!pressed', 'raised')])  # pressed, not pressed
# style.configure('P.TButton', font=('helvetica', '12', 'bold'))
#
# style.configure('W.TLabel', font=('helvetica', '12', 'bold'), foreground='black', background='white')       # Label

#############################################           MAIN        ####################################################

# btn_pres_cnt = 1  # initializing global variable to be able to call in and outside the function
# def pink(btn):
#     global btn_pres_cnt  # initializing btn_pres_cnt as a global varaible so that it adds through every iteration
#     if (
#         btn_pres_cnt == 5 or btn_pres_cnt == 10 or btn_pres_cnt == 15 or btn_pres_cnt == 20 or btn_pres_cnt == 25):  # button turns pink when btn_pres_cnt=100, and =200 and = 300.
#         style.map('P.TButton', background=[('active', 'pressed', '#FF69B4'), ('!active', 'white'), ('active', '!pressed', 'grey')])  # only the button being pressed turns hot pink
#         style.configure('P.TButton', font=('Helvetica', '12', 'bold'))
#         print("PINK!!!!!")
#     else:  # else is the normal style
#         style.map('T.TButton', background=[('active', 'pressed', 'white'), ('!active', 'white'), ('active', '!pressed', 'grey')])
#         style.configure('T.TButton', font=('Helvetica', '12', 'bold'))
#     print('btn_pres_cnt = ', btn_pres_cnt)
#     btn_pres_cnt += 1                                       # This is always executed at the end of the if else

arr_sz= int(0)                               # start array size at 0, so we initially have 0 integers in the array
arr = np.array([])                      # initialize array as integer and empty, default 1-dimension
arr.shape
arr.ndim
np.concatenate((arr, arr, arr, arr)).shape
np.concatenate((arr, np.zeros(3)))
arr_list= []
my_str_x = tk.StringVar()
my_str_y = tk.StringVar()

# def func_xy():
#     fun_x()
#     fun_y()
#    # z = i+jw

def fun_x(*i):
    my_str_x.set("Btn No is : "+ str(i))

def fun_y(*j):
    my_str_y.set("Btn No is : "+ str(j))

def button_click(btn):
    global arr_sz
    arr_sz += int(1)                                      # add +1 for each loop to the array size
    btn.configure(background='#FF69B4')
    arr_list.append([i])                                   # lst[n] needs to be equal to the button #
    print("btn: ", btn)
    print ("Button x # just clicked: ", i)
    print ("Button y # just clicked: ", j)
    print("Array list: ", arr_list)                            # Print what is in the array list
    print("Number of items in the array: ", arr_sz)
    fun_x()
    fun_y()
    # z = i+jw

np.array(arr_list)

frame = ttk.Frame(GUI)
frame.pack()

#z = x + y

for x in range(10):
    for y in range(1,11):
        btn = tk.Button(frame)
        btn.configure(text=f'{x*10+y}', width=3,command=lambda button=btn: button_click(button))
        btn.grid(column=y, row=x, sticky='nsew')

def fun_save():            # initially this will the kill the GUI. Later will close GUI, but save values for other GUI
    GUI.destroy()
    # GUI.quit()

btn_sav_minecraft = tk.Button(text='Save', width= 5, command=fun_save)
#btn_sav_minecraft.bind('<Button-1>', pink)
btn_sav_minecraft.place(x=230, y=310)

btn_exit_minecraft = tk.Button(text='Exit', width= 5, command=fun_save)
#btn_exit_minecraft.bind('<Button-1>', pink)
btn_exit_minecraft.place(x=310, y=310)

GUI.mainloop()
################# END POP UP WINDOW #############################
