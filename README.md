# Calculator_GUI

DISCRIPTION : This code creates a basic calculator using Tkinter. It features buttons for digits 0-9, basic operators (+, -, *, /), a clear button, and an equals button. The display updates as digits are pressed, and the calculation results are shown after pressing '='. The `get_digit()` function updates the display with digits, `get_operator()` stores the current number and chosen operation, and `get_result()` performs the calculation and updates the display.


from tkinter import *

num1=num2=operator=None

def get_digit(digit):
    current = result_label['text']
    new = current + str(digit)
    result_label.config(text=new)

def clear(C):
    result_label.config(text=' ')


def get_operator(op):
    global num1,operator

    num1 = int(result_label['text'])
    operator = op
    result_label.config(text=' ')


def get_result():
    global num1,num2,operator

    num2 = int(result_label['text'])

    if operator == '+':
        result_label.config(text=str(num1+num2))
    elif operator == '-':
        result_label.config(text=str(num1-num2))
    elif operator == '*':
        result_label.config(text=str(num1*num2))
    else:
        if num2  == 0:
            result_label.config(text = 'error')
        else:
             result_label.config(text=(str(round(num1/num2,2))))


root = Tk()
root.title('calculator')
root.geometry('280x380')
root.configure(background='black')

result_label = Label(root,text=' ',bg='black',fg='white')
result_label.grid(row=0,column=0,columnspan = 9,pady=(50,25),sticky='w')
result_label.config(font=('verdana',30,'bold'))

btn7 = Button(root,text='7',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(7))
btn7.grid(row =1,column=0)
btn7.config(font=('verdana',14))

btn8 = Button(root,text='8',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(8))
btn8.grid(row =1,column=1)
btn8.config(font=('verdana',14))

btn9 = Button(root,text='9',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(9))
btn9.grid(row =1,column=2)
btn9.config(font=('verdana',14))

btn_add = Button(root,text='+',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda :get_operator('+'))
btn_add.grid(row =1,column=3)
btn_add.config(font=('verdana',14))


btn4 = Button(root,text='4',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(4))
btn4.grid(row =2,column=0)
btn4.config(font=('verdana',14))

btn5 = Button(root,text='5',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(5))
btn5.grid(row =2,column=1)
btn5.config(font=('verdana',14))

btn6 = Button(root,text='6',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(6))
btn6.grid(row =2,column=2)
btn6.config(font=('verdana',14))

btn_sub = Button(root,text='-',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda :get_operator('-'))
btn_sub.grid(row =2,column=3)
btn_sub.config(font=('verdana',14))

btn1 = Button(root,text='1',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(1))
btn1.grid(row =3,column=0)
btn1.config(font=('verdana',14))

btn2 = Button(root,text='2',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(2))
btn2.grid(row =3,column=1)
btn2.config(font=('verdana',14))

btn3 = Button(root,text='3',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(3))
btn3.grid(row =3,column=2)
btn3.config(font=('verdana',14))

btn_mlti = Button(root,text='*',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda :get_operator('*'))
btn_mlti.grid(row =3,column=3)
btn_mlti.config(font=('verdana',14))


btn_clr = Button(root,text='C',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda :clear('C'))
btn_clr.grid(row =4,column=0)
btn_clr.config(font=('verdana',14))

btn0 = Button(root,text='0',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda:get_digit(0))
btn0.grid(row =4,column=1)
btn0.config(font=('verdana',14))

btn_eql = Button(root,text='=',bg = '#00a65a',fg = 'white',width=5,height = 2 ,command=get_result)
btn_eql.grid(row =4,column=2)
btn_eql.config(font=('verdana',14))

btn_div = Button(root,text='/',bg = '#00a65a',fg = 'white',width=5,height = 2,command=lambda :get_operator('/'))
btn_div.grid(row =4,column=3)
btn_div.config(font=('verdana',14))


root.mainloop()
