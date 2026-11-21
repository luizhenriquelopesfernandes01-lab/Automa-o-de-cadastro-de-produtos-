# Automa-o-de-cadastro-de-produtos-
import time
import pandas
import pyautogui

pyautogui.PAUSE = 0.5

LINK = "https://exemplo.com/login"
EMAIL = "seu_email@exemplo.com"
SENHA = "sua_senha"


def abrir_sistema():
    pyautogui.press("win")
    pyautogui.write("chrome")
    pyautogui.press("enter")
    time.sleep(3)
    pyautogui.write(LINK)
    pyautogui.press("enter")
    time.sleep(4)


def fazer_login():
    pyautogui.click(x=700, y=400)
    pyautogui.write(EMAIL)
    pyautogui.press("tab")
    pyautogui.write(SENHA)
    pyautogui.press("tab")
    pyautogui.press("enter")
    time.sleep(4)


def cadastrar_produto(linha):
    pyautogui.click(x=700, y=300)

    campos = [
        linha["codigo"],
        linha["marca"],
        linha["tipo"],
        linha["categoria"],
        linha["preco"],
        linha["custo"],
        linha["obs"],
    ]

    for campo in campos:
        if pandas.notna(campo):
            pyautogui.write(str(campo))
        pyautogui.press("tab")

    pyautogui.press("enter")
    pyautogui.scroll(5000)


def main():
    tabela = pandas.read_csv("produtos.csv")

    abrir_sistema()
    fazer_login()

    for indice in tabela.index:
        cadastrar_produto(tabela.loc[indice])

    print("Todos os produtos foram cadastrados.")


if __name__ == "__main__":
    main()
