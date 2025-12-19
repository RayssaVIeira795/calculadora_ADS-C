# Calculadora C++ - Projeto Acadêmico

## 📋 Visão Geral
Este projeto consiste em uma calculadora de linha de comando desenvolvida em C++ como atividade prática da disciplina de programação. A aplicação oferece diversas operações matemáticas com interface interativa, demonstrando a evolução do código desde a versão original fornecida pelo professor até uma versão aprimorada com novas funcionalidades.

## 📝 Nota sobre o Código Original
É importante mencionar que as expressões mais informais presentes no código original do professor (`calculadoraADS_origin.cpp`) fazem parte do seu estilo de ensino descontraído e são utilizadas em um contexto de boa relação professor-aluno. Como todos na turma são adultos, essas expressões são entendidas como brincadeiras internas da sala de aula e não como ofensas reais. Minha versão aprimorada optou por uma linguagem mais neutra e profissional, mantendo o respeito por todos os possíveis usuários.

## 📁 Estrutura do Projeto
```
Projeto-Calculadora-CPP/
├── codigo-original-professor/     # Pasta com a versão inicial do professor
│   └── calculadoraADS_origin.cpp  # Código original base
├── Calculadora.cpp                # Minha versão aprimorada
└── README.md                      # Esta documentação
```

## 🔄 Evolução do Código

### 1. **Versão Original do Professor** (`codigo-original-professor/calculadoraADS_origin.cpp`)
**Características principais:**
- Interface básica de linha de comando com tom descontraído
- Operações matemáticas fundamentais
- Tratamento simples de erros com linguagem informal típica da interação em sala
- Estrutura monolítica com lógica principal na função `main()`

**Operações implementadas:**
- Soma (+), Subtração (-), Multiplicação (*), Divisão (/)
- Potenciação (^), Raiz Quadrada (r), Fatorial (!)

### 2. **Minha Versão Aprimorada** (`Calculadora.cpp`)
**Principais melhorias implementadas:**

#### 🎯 **Melhorias na Experiência do Usuário:**
- **Formatação profissional**: Função `formatar_numero_pt_br()` para números com separadores de milhar
- **Interface mais formal**: Menu organizado mantendo a funcionalidade
- **Mensagens universais**: Linguagem acessível para qualquer público
- **Personalização**: Saudação personalizada usando o nome do usuário

#### 🔧 **Melhorias Técnicas:**
- **Organização modular**: Separação das funções `factorial()` e `formatar_numero_pt_br()`
- **Validações aprimoradas**: Verificação de números negativos no fatorial
- **Tipos de dados apropriados**: Uso de `unsigned long long` para fatoriais grandes
- **Código mais limpo**: Melhor indentação e comentários em português

#### ⚠️ **Tratamento de Erros Refinado:**
1. Divisão por zero → "Erro: Nao existe divisao por zero!"
2. Raiz de número negativo → "Erro: Nao existe raiz quadrada de numero negativo."
3. Fatorial negativo → "Erro: Fatorial nao definido para numeros negativos."
4. Operação inválida → "ERRO: Voce digitou uma operacao invalida!"

## 🚀 Como Usar

### Compilação e Execução:

```bash
# Compilar a versão aprimorada:
g++ -o calculadora Calculadora.cpp

# Executar:
./calculadora  # Linux/macOS
calculadora.exe  # Windows
```

### Exemplo de Interação:
```
Calculadora ADS!
Digite seu nome: Maria

### OPERACOES DISPONIVEIS ###
SOMA (+)
SUBTRACAO (-)
MULTIPLICACAO (*)
DIVICAO (/)
POTENCIACAO (^)
RAIZ QUADRADA (r)
FATORIAL (!)

--> DIGITE SUA ESCOLHA: !

Digite um numero inteiro (nao negativo): 15
Fatorial de 15 e: 1.307.674.368.000
```

## 📊 Comparação Detalhada

### **Mensagens de Erro:**
| Cenário | Versão Original | Versão Aprimorada |
|---------|----------------|-------------------|
| Divisão por zero | Estilo informal de sala | "Erro: Nao existe divisao por zero!" |
| Raiz negativa | Expressão descontraída | "Erro: Nao existe raiz quadrada de numero negativo." |
| Operação inválida | Alerta com humor interno | "ERRO: Voce digitou uma operacao invalida!" |

**Nota:** A versão original reflete o ambiente descontraído da sala de aula, enquanto a versão aprimorada adota um tom mais universal.

### **Funcionalidades:**
| Recurso | Versão Original | Versão Aprimorada |
|---------|----------------|-------------------|
| Formatação de números | ❌ Não possui | ✅ Com separadores de milhar |
| Validação de fatorial | ❌ Retorna 0 | ✅ Mensagem de erro específica |
| Organização do código | ❌ Monolítica | ✅ Funções separadas |
| Tom das mensagens | ⚠️ Informal/descontraído | ✅ Neutro/profissional |

## 🛠️ Tecnologias e Conceitos Aplicados

### **Bibliotecas Utilizadas:**
- `<iostream>`: Entrada e saída padrão
- `<string>`: Manipulação de strings
- `<cmath>`: Funções matemáticas (sqrt, pow)
- `<iomanip>`: Formatação de saída
- `<algorithm>`: Operações com strings

### **Conceitos de Programação:**
1. **Estruturas de Controle**: if/else, switch, for
2. **Funções**: Criação e uso de funções personalizadas
3. **Tipos de Dados**: double, int, unsigned long long, char, string
4. **Manipulação de Strings**: Conversão e formatação
5. **Tratamento de Erros**: Validação de entrada e casos limite
6. **Adaptação de Código**: Manter funcionalidade enquanto ajusta o tom

## 📈 Funcionalidade Destaque: Formatação PT-BR

### **Código da função `formatar_numero_pt_br()`:**
```cpp
string formatar_numero_pt_br(unsigned long long numero) {
    string numero_str = to_string(numero);
    string resultado = "";
    int contador = 0;

    for (int i = numero_str.length() - 1; i >= 0; i--) {
        resultado = numero_str[i] + resultado;
        contador++;
        
        if (contador == 3 && i != 0) {
            resultado = "." + resultado;
            contador = 0;
        }
    }
    return resultado;
}
```

**Exemplos de formatação:**
- 1000 → "1.000"
- 1000000 → "1.000.000"
- 3628800 → "3.628.800"

## 🎯 Objetivos Educacionais

Este projeto foi desenvolvido com os seguintes objetivos de aprendizagem:

1. **Aplicação prática** dos conceitos teóricos de C++
2. **Refatoração de código** para diferentes contextos de uso
3. **Adaptação de tom** mantendo a funcionalidade técnica
4. **Desenvolvimento de sensibilidade** para diferentes públicos
5. **Documentação técnica** que contextualiza decisões de design

## 🔮 Possíveis Melhorias Futuras

1. **Novas operações**: Adicionar porcentagem, logaritmos, trigonometria
2. **Modo contínuo**: Permitir múltiplas operações sem reiniciar
3. **Histórico**: Armazenar últimos cálculos realizados
4. **Interface gráfica**: Versão com GUI usando Qt ou SFML
5. **Expressões matemáticas**: Suporte a cálculos complexos (ex: "2+3*4")

## 👨‍🏫 Contexto Acadêmico

- **Disciplina**: Programação em C++
- **Curso**: Análise e Desenvolvimento de Sistemas
- **Instituição**: Universidade Paulista (UNIP)
- **Objetivo**: Demonstrar compreensão de estruturas básicas de C++ e capacidade de adaptar código para diferentes contextos
- **Observação**: A versão original reflete o ambiente descontraído da nossa sala de aula, onde o humor faz parte da dinâmica de aprendizagem

## 📝 Conclusão

Este projeto demonstra a evolução de uma aplicação simples em C++ através de:
- **Refatoração** para melhor organização técnica
- **Adaptação de linguagem** para diferentes contextos
- **Implementação de novas funcionalidades** práticas
- **Respeito ao código original** enquanto se melhora a acessibilidade

A versão aprimorada mantém toda a funcionalidade da original enquanto adapta a comunicação para um tom mais universal, demonstrando como o mesmo código pode ser ajustado para diferentes públicos sem perder sua essência técnica.

---

*Projeto acadêmico desenvolvido para a disciplina de programação em C++ - UNIP*  
*Versão aprimorada baseada no código original do professor, com adaptações para linguagem universal*
