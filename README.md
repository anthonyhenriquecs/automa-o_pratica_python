# automa-o_pratica_python

import pyautogui
import time

pyautogui.PAUSE = 1

#Entrar no site
pyautogui.press("Win")
pyautogui.write("chorme")
pyautogui.press("enter")

link = "https://dlp.hashtagtreinamentos.com/python/intensivao/login"
pyautogui.write(link)
pyautogui.press("enter")
time.sleep(3)

#login
pyautogui.click(x=625, y=375)
pyautogui.write("slalsasla@gmail.com")
pyautogui.press("tab")
pyautogui.write("senha")
pyautogui.press("enter")
time.sleep(1)
#importando base de dados
import pandas

tabela = pandas.read_csv("produtos.csv")

for item in tabela.index:
    #cadastrando os produtos
    pyautogui.click(x=558, y=261)
    #codigo
    codigo = tabela.loc[item, "codigo"]
    pyautogui.write(codigo)
    pyautogui.press("tab")
    
    #marca
    pyautogui.write(tabela.loc[item, "marca"])
    pyautogui.press("tab")
    
    #tipo
    pyautogui.write(tabela.loc[item, "tipo"])
    pyautogui.press("tab")
    
    #categoria
    pyautogui.write(str(tabela.loc[item, "categoria"]))
    pyautogui.press("tab")
    
    #preço
    pyautogui.write(str(tabela.loc[item, "preco_unitario"]))
    pyautogui.press("tab")
    
    #custo
    pyautogui.write(str(tabela.loc[item, "custo"]))
    pyautogui.press("tab")
    
    #obs
    obs = tabela.loc[item, "obs"]
    if not pandas.isna(obs):
        pyautogui.write(obs)
    pyautogui.press("tab")
    #enviar
    pyautogui.press("enter")
    pyautogui.scroll(5000)
    
