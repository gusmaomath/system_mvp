
# Sistema de Treinamento VR para Alunos de Medicina

Este repositório contém o código-fonte de um sistema de simulação de treinamento em realidade virtual (VR) para **alunos de medicina**. O sistema foi desenvolvido para auxiliar os alunos a praticarem procedimentos cirúrgicos, tomarem decisões em situações de pressão, e analisarem seu desempenho com base em gráficos e rankings.

## Funcionalidades

O sistema está dividido em quatro principais módulos:

1. **Simulação Cirúrgica com Programação Dinâmica**
    - Os alunos passam por uma sequência de passos cirúrgicos. O sistema usa **programação dinâmica** para otimizar a execução dessas etapas, minimizando o tempo e penalidades por erros.
    
2. **Simulação de Situação de Pressão com Monte Carlo**
    - Este módulo simula cenários de emergência, como o controle de hemorragias. Usamos **simulações de Monte Carlo** para calcular probabilidades de sucesso/falha em diferentes variáveis como tempo de resposta e acertos.

3. **Análise de Desempenho**
    - Geração de gráficos de barras representando as notas de cada aluno, com uma interface clara para visualizar o desempenho individual. Utiliza a biblioteca `Matplotlib`.

4. **Geração de Ranking**
    - O sistema gera um ranking dos alunos com base em suas notas finais, utilizando o algoritmo de **quicksort** para ordenação eficiente.

## Exemplo de Uso

Aqui está um exemplo de como o sistema pode ser utilizado:

```python
# Simulação cirúrgica
cirurgia = SimulacaoCirurgicaPD()
cirurgia.iniciar()
nota_cirurgia, tempo_cirurgia = cirurgia.avaliar()

# Simulação de pressão
pressao = SimulacaoMonteCarlo()
pressao.iniciar()
pressao.simular()
nota_pressao = pressao.avaliar_simulacao()

# Criar alunos com notas fictícias
alunos = [
    Aluno('Matheus', nota_cirurgia),
    Aluno('Ana', 95.0),
    Aluno('Lucas', nota_pressao),
    Aluno('Bianca', 92.3),
    Aluno('João', 80.4)
]

# Analisar o desempenho e gerar ranking
analise = AnaliseRanking(alunos)
analise.gerar_grafico_notas()
analise.exibir_ranking()
analise.gerar_relatorio_txt('relatorio_alunos_completo.txt')
```

## Documentação Completa

### 1. Introdução

Este sistema foi desenvolvido para simular um ambiente de treinamento em realidade virtual (VR) voltado para **alunos de medicina**. O foco do sistema é permitir que os alunos pratiquem suas habilidades cirúrgicas, tomem decisões sob pressão, e melhorem seu desempenho geral com base em diferentes parâmetros de avaliação. O sistema também gera um **ranking** dos alunos, utilizando técnicas de programação dinâmica, simulações de Monte Carlo e algoritmos de ordenação (quicksort).

### 2. Módulos do Sistema

O sistema está dividido em quatro principais componentes:
- **Simulação Cirúrgica com Programação Dinâmica**
- **Simulação de Pressão com Monte Carlo**
- **Análise de Desempenho**
- **Geração de Ranking dos Alunos**

#### 2.1. Simulação Cirúrgica com Programação Dinâmica

Objetivo: A simulação cirúrgica visa criar um ambiente onde o aluno precisa executar uma sequência de passos relacionados a um procedimento cirúrgico. Utilizamos **programação dinâmica** para otimizar a execução desses passos, minimizando penalidades por erros e, consequentemente, calculando uma nota final com base em desempenho.

Estrutura do Código: A classe `SimulacaoCirurgicaPD` define a simulação cirúrgica. Os passos da cirurgia estão definidos na lista `self.passos`. O método `executar_passos` é recursivo e utiliza programação dinâmica (armazenando resultados parciais em `self.dp`) para calcular o menor custo (tempo e penalidades). O método `avaliar` calcula a nota final baseada nos erros e no custo total.

#### 2.2. Simulação de Pressão com Monte Carlo

Objetivo: O objetivo deste módulo é simular situações de emergência onde o aluno deve tomar decisões sob pressão. Utilizamos **simulações de Monte Carlo** para calcular probabilidades de sucesso ou falha em um cenário com várias variáveis aleatórias, como o tempo de resposta e acertos/erros.

#### 2.3. Análise de Desempenho

Objetivo: A análise de desempenho visa apresentar graficamente o desempenho de cada aluno com base nas notas obtidas nos módulos anteriores. Utiliza-se a biblioteca `Matplotlib` para gerar gráficos de barras.

#### 2.4. Geração de Ranking dos Alunos

Objetivo: O ranking é gerado para classificar os alunos com base nas notas obtidas nas simulações. Para isso, utilizamos o **algoritmo de quicksort**, que é eficiente para ordenação de grandes conjuntos de dados.

### 3. Exemplo de Uso Completo

Aqui está um exemplo de como o sistema pode ser utilizado de forma completa:

```python
# Simulação cirúrgica
cirurgia = SimulacaoCirurgicaPD()
cirurgia.iniciar()
nota_cirurgia, tempo_cirurgia = cirurgia.avaliar()

# Simulação de pressão
pressao = SimulacaoMonteCarlo()
pressao.iniciar()
pressao.simular()
nota_pressao = pressao.avaliar_simulacao()

# Criar alunos com notas fictícias
alunos = [
    Aluno('Matheus', nota_cirurgia),
    Aluno('Ana', 95.0),
    Aluno('Lucas', nota_pressao),
    Aluno('Bianca', 92.3),
    Aluno('João', 80.4)
]

# Analisar o desempenho e gerar ranking
analise = AnaliseRanking(alunos)
analise.gerar_grafico_notas()
analise.exibir_ranking()
analise.gerar_relatorio_txt('relatorio_alunos_completo.txt')
```

### 4. Conclusão

Este sistema oferece uma plataforma de treinamento realista para alunos de medicina, permitindo que eles pratiquem suas habilidades em cenários simulados, sejam avaliados em diferentes aspectos, e tenham uma visão clara de seu desempenho através de gráficos e rankings. A utilização de técnicas avançadas como **programação dinâmica** e **simulações de Monte Carlo** permite que o sistema seja flexível e ofereça feedback robusto para o usuário.
