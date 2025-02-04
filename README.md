# dados-cadastro

import tkinter as tk
# Criar janela principal
root = tk.Tk()
root.title("Interface com 5 Objetos")
root.geometry("600x200")


# Criar Rótulos e Caixas de Entrada lado a lado
tk.Label(root, text="Nome:", font=("Arial", 12)).grid(row=0, column=0, padx=10, pady=5, sticky="e")
entrada_nome = tk.Entry(root, width=70)
entrada_nome.grid(row=0, column=1, padx=10, pady=5)

tk.Label(root, text="Endereco:", font=("Arial", 12)).grid(row=1, column=0, padx=10, pady=5, sticky="e")
entrada_endereco = tk.Entry(root, width=70)
entrada_endereco.grid(row=1, column=1, padx=10, pady=5, sticky='w')

tk.Label(root, text="Bairro:", font=("Arial", 12)).grid(row=2, column=0, padx=10, pady=5, sticky="e")
entrada_bairro = tk.Entry(root, width=30)
entrada_bairro.grid(row=2, column=1, padx=10, pady=5)

tk.Label(root, text="Cep:", font=("Arial", 12)).grid(row=3, column=0, padx=10, pady=5, sticky="e")
entrada_bairro = tk.Entry(root, width=30)
entrada_bairro.grid(row=3, column=1, padx=10, pady=5)


# Criar um rótulo para exibir o resultado
label_resultado = tk.Label(root, text="Resultado:", font=("Arial", 12), fg="blue")
label_resultado.grid(row=4, column=0, columnspan=2, pady=10)

# Função para exibir os dados digitados
def exibir_dados():
 nome = entrada_nome.get()
 endereco = entrada_endereco.get()
 bairro = entrada_bairro.get()
 label_resultado.config(text=f"Nome: {nome}, Endereço: {endereco}, Bairro: {bairro}")
 
# Função para limpar os campos
def limpar_campos():
 entrada_nome.delete(0, tk.END)
 entrada_endereco.delete(0, tk.END)
 entrada_bairro.delete(0, tk.END)
 label_resultado.config(text="Resultado:")
 
# Criar Botões e posicioná-los
botao_exibir = tk.Button(root, text="Exibir", command=exibir_dados)
botao_exibir.grid(row=5, column=0, padx=10, pady=10, sticky="e")
botao_limpar = tk.Button(root, text="Limpar", command=limpar_campos)
botao_limpar.grid(row=6, column=1, padx=10, pady=10, sticky="w")

# Iniciar o loop da aplicação
root.mainloop()
