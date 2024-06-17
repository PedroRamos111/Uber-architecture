# Uber-architecture
## Introdução

O aplicativo Uber é um sistema complexo e de alta escala. Este trabalho prático visa analisar a arquitetura de software deste aplicativo, explorando suas tecnologias, evolução, requisitos e desafios.

## Caracterização do Sistema

### Requisitos do Sistema

*   **Nicho de Mercado:** Transporte privado urbano e delivery de alimentos
    - A diversidade de serviços tanto de transporte individual e compartilhado (Uber)  e o seu serviço de entrega de comidas(Uber eats) exige uma arquitetura flexível e escalável, capaz de acomodar diferentes fluxos de trabalho e integrações com diversos parceiros (motoristas, restaurantes, etc.).
    
*   **Número de Clientes:** Milhões de clientes em todo o mundo
    - O Uber opera em centenas de cidades ao redor do mundo, com milhões de usuários ativos. Esta vasta base de usuários exige alta escalabilidade, tolerância a falhas e mecanismos eficientes de gerenciamento de dados e tráfego.
  
*   **Número de Acessos Simultâneos:** Potencialmente muito alto, especialmente em horários de pico
    - O número de acessos simultâneos varia ao longo do dia, com picos em horários de rush e eventos especiais. Com isso a arquitetura deve ser capaz de lidar com picos de demanda sem comprometer o desempenho, utilizando técnicas como balanceamento de carga e dimensionamento automático de recursos.
  
*   **Requisitos de Segurança:** Elevados, envolvendo dados pessoais, financeiros e de localização
    - O Uber lida com dados sensíveis de usuários (localização, informações de pagamento, histórico de viagens) e motoristas (dados pessoais, informações bancárias).Nesse sentido a segurança é crítica, exigindo criptografia de dados, autenticação robusta, controles de acesso rigorosos e mecanismos de prevenção e detecção de fraudes.
      
*   **Requisitos de Confiabilidade:** Mercado competitivo
    - A Uber opera em um mercado  competitivo, a indisponibilidade do serviço pode levar à perda de clientes a. Portanto, a tolerância a falhas é crucial para garantir que o serviço permaneça operacional mesmo em caso de falhas.
      
*   **Requisitos de Escalabilidade:** Essenciais, devido ao rápido crescimento da plataforma
    - A Uber está em constante expansão, entrando em novos mercados e adquirindo novos usuários. A escalabilidade  permite que a empresa adicione recursos de forma rápida e eficiente para atender à crescente demanda.
      
*   **Requisitos de Performance:** Importantes para garantir uma experiência fluida e responsiva
    - A Uber busca oferecer uma experiência de usuário rápida e eficiente, desde a solicitação de um carro até o pagamento da corrida. Otimizações de banco de dados, cache e código são essenciais para garantir tempos de resposta rápidos e um aplicativo responsivo.

### Dados da Empresa

| Indústria               | Tecnologia      |
| --------------------- | ------------- |
| **Fundação**            | Junho de 2010   |
| **Presença em cidades no mundo** | +10,5 mil     |
| **Presença em cidades no Brasil** | +500          |
| **Presença em países**    | 70             |
| **Funcionários no Brasil** | +1 mil         |
| **Motoristas/entregadores parceiros no mundo** | 6,5 milhões   |
| **Motoristas/entregadores parceiros no Brasil*** | 1 milhão     |
| **Usuários no mundo**      | 142 milhões    |
| **Usuários no Brasil**    | 30 milhões\*   |
| **Viagens/entregas por dia no mundo** | 26 milhões    |

---

## Histórico da arquitetura
### MVC
- A primeira base de código da uber seguia o padrão MVC. No entanto , dois grandes problemas levaram a equipe de desenvolvimento da Uber a abandona-lo:
    01. Classes de Controller muito grandes tornando dificil leitura e modificação;
    02. Dificuldade em testar as classes que cresciam muito;
Resumidamente, o padrão arquitetural não era escalável.
### VIPER
- Como alternativa ao MVC, os desenvolvedores da Uber voltaram sua atenção para o VIPER que permitia a adoção de uma arquitetura limpara para iOS e trazia maior capacidade de abstração. Contudo, essa arquitetura também apresentava desvantagens:
    01. Especifica para iOS
    02. Estados orientados por visualizações
    03. Dificuldade em implementar nós apenas para visão lógica ou lógica de visualização.
### Riblets
- Padrão arquitetural que os desenvolvedores apresentaram para englobar as vantagens do VIPER e contornar suas desvantagens.

![Riblets](Arquitetura/image.png "Visão geral de um app construido com Riblets")

---

## Considerações
Considerando a necessidade de alta confiabilidade, escalabilidade e performance, a arquitetura do Uber provavelmente utiliza tecnologias como microsserviços, computação em nuvem, cache distribuído e sistemas de mensageria para garantir que o serviço esteja sempre disponível, responsivo e capaz de atender às demandas de milhões de usuários em todo o mundo.

## Referências

*   **Engineering the Architecture Behind Uber's New Rider App:** https://www.uber.com/blog/new-rider-app-architecture/
*   **Engenharia da arquitetura por trás do novo aplicativo do motorista Uber:** https://imasters.com.br/android/engenharia-da-arquitetura-por-tras-do-novo-aplicativo-do-motorista-uber
*   **Fatos e Dados sobre a Uber:** https://www.uber.com/pt-BR/newsroom/fatos-e-dados-sobre-uber/
