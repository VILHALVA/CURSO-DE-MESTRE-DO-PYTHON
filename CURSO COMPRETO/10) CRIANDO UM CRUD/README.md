# CRIANDO UM CRUD
Um CRUD (Create, Read, Update, Delete) é uma aplicação que realiza operações básicas de manipulação de dados em um sistema, como criar, ler, atualizar e excluir registros em um banco de dados. Abaixo, vou fornecer um exemplo simples de como criar um CRUD em Python usando uma lista para armazenar os dados.

```python
class Contato:
    def __init__(self, nome, telefone):
        self.nome = nome
        self.telefone = telefone

class Agenda:
    def __init__(self):
        self.contatos = []

    def adicionar_contato(self, nome, telefone):
        contato = Contato(nome, telefone)
        self.contatos.append(contato)
        print("Contato adicionado com sucesso!")

    def listar_contatos(self):
        if self.contatos:
            print("Lista de contatos:")
            for i, contato in enumerate(self.contatos, start=1):
                print(f"{i}. Nome: {contato.nome}, Telefone: {contato.telefone}")
        else:
            print("Nenhum contato na agenda.")

    def atualizar_contato(self, indice, nome, telefone):
        if 0 < indice <= len(self.contatos):
            self.contatos[indice - 1].nome = nome
            self.contatos[indice - 1].telefone = telefone
            print("Contato atualizado com sucesso!")
        else:
            print("Índice de contato inválido.")

    def excluir_contato(self, indice):
        if 0 < indice <= len(self.contatos):
            del self.contatos[indice - 1]
            print("Contato excluído com sucesso!")
        else:
            print("Índice de contato inválido.")

# Função para exibir as opções do menu
def exibir_menu():
    print("\nMenu:")
    print("1. Adicionar Contato")
    print("2. Listar Contatos")
    print("3. Atualizar Contato")
    print("4. Excluir Contato")
    print("5. Sair")

# Função principal
def main():
    agenda = Agenda()

    while True:
        exibir_menu()
        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            nome = input("Digite o nome do contato: ")
            telefone = input("Digite o telefone do contato: ")
            agenda.adicionar_contato(nome, telefone)
        elif opcao == "2":
            agenda.listar_contatos()
        elif opcao == "3":
            indice = int(input("Digite o índice do contato a ser atualizado: "))
            nome = input("Digite o novo nome do contato: ")
            telefone = input("Digite o novo telefone do contato: ")
            agenda.atualizar_contato(indice, nome, telefone)
        elif opcao == "4":
            indice = int(input("Digite o índice do contato a ser excluído: "))
            agenda.excluir_contato(indice)
        elif opcao == "5":
            print("Saindo...")
            break
        else:
            print("Opção inválida. Tente novamente.")

if __name__ == "__main__":
    main()
```

Neste exemplo, criamos duas classes: `Contato` e `Agenda`. A classe `Contato` representa um contato com atributos de nome e telefone. A classe `Agenda` representa uma agenda telefônica que armazena uma lista de contatos.

A classe `Agenda` possui métodos para adicionar, listar, atualizar e excluir contatos. A função `exibir_menu()` exibe as opções disponíveis para o usuário, e a função `main()` é responsável por executar o programa.

Você pode executar este código em um ambiente Python para testar as operações CRUD básicas em uma agenda telefônica.