# 🚀 Projeto Bootcamp Java Developer - Simulador de Aprendizado

Este projeto é uma simulação de um sistema de gerenciamento de Bootcamp, onde desenvolvedores podem se inscrever, consumir conteúdos (cursos e mentorias), progredir e acumular XP (experiência). Ele foi desenvolvido com foco em orientação a objetos e boas práticas de encapsulamento, herança e polimorfismo.

## 🎯 Objetivo

Simular a jornada de aprendizado de um desenvolvedor dentro de um Bootcamp, com controle de progresso, cálculo de XP e registro de conteúdos concluídos.

## 🧱 Estrutura do Projeto

O projeto está dividido em pacotes e classes:

### 📁 `br.com.dio.desafio.dominio`

- **`Conteudo` (abstract class)**  
  Classe base para todos os tipos de conteúdo. Possui título, descrição e método abstrato `calcularXp()`.

- **`Curso` (extends Conteudo)**  
  Representa um curso com carga horária. XP é calculado como `XP_PADRAO * cargaHoraria`.

- **`Mentoria` (extends Conteudo)**  
  Representa uma mentoria com data específica. XP é calculado como `XP_PADRAO + 20`.

- **`Bootcamp`**  
  Contém nome, descrição, data de início/fim, lista de conteúdos e lista de desenvolvedores inscritos.

- **`Dev`**  
  Representa um desenvolvedor. Possui nome, conteúdos inscritos e concluídos. Pode se inscrever em bootcamps, progredir e calcular XP total.

### 📁 `br.com.dio.desafio`

- **`Main`**  
  Classe principal que instancia cursos, mentorias, bootcamp e desenvolvedores. Simula a inscrição e progresso dos devs.

## 🧪 Simulação no `Main`

- Criação de dois cursos e uma mentoria
- Instanciação de um bootcamp com esses conteúdos
- Inscrição de dois devs (`Larah` e `Camila`)
- Simulação de progresso e exibição de conteúdos inscritos, concluídos e XP acumulado

## 📊 Cálculo de XP

| Tipo de Conteúdo | Fórmula de XP |
|------------------|----------------|
| Curso            | `10 * cargaHoraria` |
| Mentoria         | `10 + 20` |

## 📆 Datas

- O bootcamp tem duração fixa de 45 dias a partir da data de criação (`LocalDate.now()`).

## 🛠️ Tecnologias Utilizadas

- Java 17+
- Paradigma de Programação Orientada a Objetos
- API de datas (`java.time.LocalDate`)
- Coleções (`Set`, `LinkedHashSet`, `HashSet`)
- Optional e Stream API

## ▶️ Como Executar

1. Compile os arquivos:
   ```bash
   javac br/com/dio/desafio/**/*.java
   ```
2. Execute a classe principal:
   ```bash
   java br.com.dio.desafio.Main
   ```

## 📌 Observações

- O método `progredir()` consome o primeiro conteúdo da lista de inscritos.
- O sistema não impede que o mesmo conteúdo seja adicionado múltiplas vezes (caso não haja controle externo).
- XP é acumulado apenas com conteúdos concluídos.
