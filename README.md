# 🌐 TechInclusive Congress 2025 (PoC)

![Project Status](https://img.shields.io/badge/Status-Finalizado-success?style=for-the-badge)
![Acessibilidade](https://img.shields.io/badge/Acessibilidade-WCAG%202.2%20AAA-blueviolet?style=for-the-badge)
![Performance](https://img.shields.io/badge/PageSpeed-100%2F100-brightgreen?style=for-the-badge)

> **Prova de Conceito (PoC)** desenvolvida para o capítulo acadêmico: *"Acessibilidade Web como Critério de Qualidade de Software: O Impacto da Inclusão Digital na Experiência do Usuário e na Conversão de Negócios"*.

---

## 📖 Sobre o Projeto

Este repositório não contém apenas uma Landing Page. Ele serve como **objeto de estudo prático** para demonstrar a aplicação da metodologia **Shift-Left Testing** no desenvolvimento Frontend.

O objetivo foi criar uma interface visualmente complexa (utilizando *Glassmorphism*, *Parallax 3D* e texturas), garantindo, simultaneamente, pontuação máxima em ferramentas de auditoria técnica (Google PageSpeed Insights) e conformidade legal com a **Lei Brasileira de Inclusão (LBI)**.

### 🎯 Objetivos Técnicos
- **Governança de Código:** Implementar travas automáticas (`git hooks`) que impedem commits de código inacessível.
- **Design Inclusivo:** Provar que estética moderna e acessibilidade não são excludentes.
- **Alta Performance:** Atingir score 100 em Core Web Vitals.

---

## 🛠️ Tecnologias & Ferramentas

O projeto foi construído utilizando padrões modernos de desenvolvimento web e ferramentas de automação de qualidade (QA).

<div align="center">

| Categoria | Tecnologias |
| :--- | :--- |
| **Frontend Core** | ![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white) ![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black) |
| **Quality Assurance** | ![Husky](https://img.shields.io/badge/Husky-brown?style=for-the-badge&logo=npm&logoColor=white) ![Pa11y](https://img.shields.io/badge/Pa11y-Ci%2FCd-blue?style=for-the-badge) ![Axe-Core](https://img.shields.io/badge/Axe--Core-Automated-orange?style=for-the-badge) |
| **Infra & Deploy** | ![Git](https://img.shields.io/badge/GIT-E44C30?style=for-the-badge&logo=git&logoColor=white) ![Firebase](https://img.shields.io/badge/Firebase-039BE5?style=for-the-badge&logo=Firebase&logoColor=white) |
| **Design System** | ![Figma](https://img.shields.io/badge/Glassmorphism-UI-purple?style=for-the-badge) ![W3C](https://img.shields.io/badge/W3C-WCAG%20Compliant-green?style=for-the-badge) |

</div>

---

## ⚙️ A Engenharia por Trás (Husky Workflow)

O diferencial deste repositório é a configuração do **Husky** como "porteiro" de qualidade. O fluxo de trabalho segue a lógica abaixo:

1.  **Tentativa de Commit:** O desenvolvedor executa `git commit`.
2.  **Interceptação:** O Husky pausa o processo e aciona o gancho `pre-commit`.
3.  **Auditoria:** A biblioteca **Pa11y** varre o código HTML em busca de erros de contraste, semântica e atributos ARIA.
4.  **Decisão Binária:**
    * 🔴 **Falha:** Se houver erros, o commit é bloqueado (Exit Code 1).
    * 🟢 **Sucesso:** Se o código estiver limpo, o commit é enviado.

### Exemplo de Bloqueio (Simulação)
> *O terminal abaixo demonstra o Husky bloqueando um código com baixo contraste, conforme documentado no estudo.*

```bash
# Simulação de erro no terminal
Error: This element has insufficient contrast at this conformance level.
Expected a contrast ratio of at least 4.5:1, but text in this element has a contrast ratio of 1.61:1.
husky - pre-commit script failed (code 2)
