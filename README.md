# Sistema de Cadastro em C

## 📌 Descrição

Projeto em **C** que permite cadastrar pessoas com **nome** e **idade**, listar os cadastros e controlar um limite de até 100 pessoas.
É um projeto acadêmico desenvolvido para praticar **estruturas de dados**, **vetores**, **structs** e **entrada/saída no console**.

---

## 🛠 Tecnologias

* Linguagem C
* Console/Terminal
* Estruturas de dados (structs, arrays)
* Laços de repetição e condicionais

---

## ⚙ Funcionalidades

* Adicionar pessoa (nome e idade)
* Listar todas as pessoas cadastradas
* Controle de limite de cadastros (máx. 100 pessoas)
* Menu interativo no console

---

## 💻 Código

```c
#include <stdio.h>
#include <string.h>

#define MAX 100

typedef struct {
    char nome[50];
    int idade;
} Pessoa;

int main() {
    Pessoa lista[MAX];
    int opcao, total = 0;
    
    do {
        printf("\n--- Sistema de Cadastro ---\n");
        printf("1. Adicionar Pessoa\n");
        printf("2. Listar Pessoas\n");
        printf("3. Sair\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &opcao);
        getchar();

        if(opcao == 1) {
            if(total < MAX) {
                printf("Nome: ");
                fgets(lista[total].nome, 50, stdin);
                lista[total].nome[strcspn(lista[total].nome, "\n")] = 0;
                printf("Idade: ");
                scanf("%d", &lista[total].idade);
                getchar();
                total++;
                printf("Pessoa cadastrada com sucesso!\n");
            } else {
                printf("Limite de cadastro atingido.\n");
            }
        } else if(opcao == 2) {
            printf("\n--- Lista de Pessoas ---\n");
            for(int i=0; i<total; i++) {
                printf("%d. %s - %d anos\n", i+1, lista[i].nome, lista[i].idade);
            }
        }

    } while(opcao != 3);

    printf("Encerrando programa.\n");
    return 0;
}
```
