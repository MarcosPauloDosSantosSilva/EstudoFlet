import flet as ft
import time

def main (page:ft.Page):
    page.bgcolor=""
    page.add(ft.Text('Controle de recebimento de Veículos para descarga.', color="Green", font_family="RobotoSlab", size=50, weight=ft.FontWeight.BOLD,  ))
    page.add(ft.Text('Chegada dos veículos na portária', color="black", font_family="RobotoSlab", size=30)),
    
   
    
    def cadastrar (evento):
          
        print (ficha_Sequencia_digitado.value, nome_digitado.value, fone_digitado.value,fone_watzap.value,rg_digitado.value,cnh_digitado.value,cpf_digitado.value,placa_vaiculo.value,cg.value)
   
   


    ficha_Sequencia_digitado=ft.TextField(label="Ficha", width=75)
    nome_digitado=ft.TextField(label="Nome do Motosrista")
    fone_digitado=ft.TextField(label="Contato",width=150)
    fone_watzap=ft.TextField(label="Whatssap",width=150)
    campo_nome=ft.Row([ficha_Sequencia_digitado,nome_digitado, fone_digitado, fone_watzap])
    
    rg_digitado=ft.TextField(label="Identidade RG",width=150)
    cnh_digitado=ft.TextField(label="Carteira Habilitação CNH",width=150)
    cpf_digitado=ft.TextField(label="Cadastro pessoa Física CPF",width=150)  
    campo_documentos=ft.Row([rg_digitado,cnh_digitado,cpf_digitado])

    cg = ft.RadioGroup(content=ft.Row([
    ft.Radio(value="Carreta bau", label="Carreta bau"),
    ft.Radio(value="Carreta side", label="Carreta side"),
    ft.Radio(value="Container", label="Container"),
    ft.Radio(value="Carreta Graneleiro", label="Carreta Graneleiro"),
    ft.Radio(value="Caminhao bau", label="Caminhao bau"),
    ft.Radio(value="Caminhao", label="Caminhão")]))
    
    placa_vaiculo=ft.TextField(label="Placa", width=150)
    campo_veiculos=ft.Row([placa_vaiculo,cg])

    dia_apresentacao_nota=ft.TextField(label="Data da chegada",width=150)
    hora_apresentacao_nota=ft.TextField(label="Hora Chegada",width=150)    
    campo_dia_hora=ft.Row([dia_apresentacao_nota,hora_apresentacao_nota])

    fornecedor=ft.TextField(label="Fornecedor da Nota fiscal",width=280)
    numeros_das_notas=ft.TextField(label="Numeros das notas",width=150)

    campo_infor_nota=ft.Row([fornecedor,numeros_das_notas])

    page.add(ft.Text('Dados do motorista:', color="blue", font_family="RobotoSlab", size=15)),
    page.add(campo_nome)
    page.add(ft.Text('Tipo documento:', color="blue", font_family="RobotoSlab", size=15)),
    page.add(campo_documentos),
    #page.add(ft.Text("Selecione o tipo de veiculo:")),
    page.add(ft.Text('Dados do Veículo:                Selecione o tipo de veiculo:'  , color="blue", font_family="RobotoSlab", size=15)),
    page.add(campo_veiculos)
   
    page.add(ft.Text('Dados da nota:', color="blue", font_family="RobotoSlab", size=15)),
    page.add(campo_dia_hora)   
    page.add(campo_infor_nota)
    page.add(ft.ElevatedButton(text="Validar", on_click=cadastrar))
    

    page.update()
    
    

ft.app(target=main)
#ft.app (target=main, view=ft.AppView.WEB_BROWSER)
# (desktop)  ft.app (port=8550, target=main)