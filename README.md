# Cocriação entre DesignOps e DevOps para IA Invisível

## 🎯 Objetivo

Este documento mostra, todo o processo de mapeamento colaborativo entre DesignOps e DevOps para criar a base de um Design System voltado a uma **API de IA textual** invisível. O propósito é garantir que as diretrizes de design se integrem perfeitamente aos pipelines de desenvolvimento e operação, preservando qualidade, consistência e escalabilidade.


## 📚 Referências

Para estruturar este trabalho, segui três fontes principais:

1. **Jeremy Keith – “Design Ops for Design Systems”**  
   Keith reforça que DesignOps é antes de tudo uma prática cultural: envolve rituais, papéis e fluxos de trabalho que garantem a adoção e evolução de um Design System, não apenas artefatos estáticos.

2. **Brad Frost – “Design Systems are for User Interfaces”**  
   Frost lembra que um Design System é, na verdade, um “sistema de sistemas”. Ele define fronteiras bem claras, o que entra no sistema e o que fica em soluções irmãs, e foca em componentes reutilizáveis.

3. **Vídeo de Pipeline Integrado**  
   Este material ilustra um exemplo prático de como pipelines de MLOps podem se comunicar em tempo real com equipes de design para validação contínua de artefatos.

## 👤 Escopo

Escolhi focar em uma **API de IA textual**, pois é um caso de uso comum (chatbots, assistentes, Q&A) sem UI tradicional. Minha entrega deve:

- Documentar todo o fluxo de criação, teste, versionamento e deploy de **prompts** e **respostas**.  
- Simular feedback colaborativo que eu receberia em sala (post-its brancos).  
- Gerar insumos prontos para um repositório GitHub com CI, documentação viva e exemplos.
  
## 🛠️ Materiais e “Post-its Conceituais”

Imagine que temos três cores de post-it:

- **Azuis (DesignOps):** diretrizes de voz, mapeamento de fluxos, curadoria de dados.  
- **Amarelos (Conexões):** pontos de integração, automações e versionamento cruzado.  
- **Verdes (DevOps):** pipelines de CI/CD, testes, deploy e monitoramento.  

Além disso, utilizei post-its brancos para registrar feedback externo simulado — sugestões ou riscos apontados por “outros grupos”.

---

## 🧱 Detalhamento das Etapas

### 1. Aquecimento e Contextualização

Começamos com uma breve apresentação do desafio: “Vocês vão criar a base de um Design System para uma API de IA textual, integrando DesignOps e DevOps para manter qualidade e consistência em cada release.” Para funcionar solo, listei três papéis essenciais que, em um grupo, seriam revezados: autor de prompts, revisor de qualidade e engenheiro de pipeline. Isso garante clareza sobre quem faz o quê, mesmo sem colegas por perto.

### 2. Cocriação em 3 Camadas

**Camada DesignOps (azul):**  
Descrevi em prosa as principais entregas dessa camada: um guia de tom de voz que estabelece persona e linguajar neutro, mapeamento de intenções (saudações, consultas, respostas de fallback) em um documento de “componentes de prompt” e um processo contínuo de testes de experiência invisível, que envolve tanto simulações automatizadas quanto revisões manuais. Escrevi também sobre o versionamento: cada mudança de prompt recebe uma tag no Git (`design-vX.Y`) e um changelog detalhando autor, data e motivação da alteração. Por fim, destaquei a importância da curadoria de datasets e da manutenção de uma documentação viva em mkdocs, onde exemplos de uso e FAQs ficam sempre atualizados.

**Camada de Conexões (amarelo):**  
Em linguagem narrativa, expliquei como o DesignOps entrega prompts para o DevOps: um webhook dispara um job de QA textual logo que um commit atinge a branch principal. Se o teste de qualidade — que verifica legibilidade, coerência e compliance com o tom — passar, o pipeline de CI/CD prossegue. Também deixei claro que o Design System gerencia apenas prompts e respostas; guidelines de marca e conteúdos extensos vivem em repositórios irmãos, referenciados por links na documentção central. Para fechar, inseri sugestões de feedback (post-its brancos simulados), como “quem aprova a versão final do prompt?” e “incluir webhook para aviso de falhas”.

**Camada DevOps (verde):**  
Aqui, descrevi detalhadamente em frases completas o pipeline de CI/CD: uso de GitHub Actions que baixa o código, instala dependências, executa testes unitários para intents críticas e dispara um deploy canário (5% do tráfego). Se métricas de erro ou latência excederem thresholds, o sistema faz rollback automático. A parte de monitoramento envolve dashboards no Grafana mostrando latência, taxa de erros e perplexidade do modelo, além de alertas integrados ao Slack. Por fim, detalhei a rotina de MLOps: treinos mensais do modelo com novos dados e reuniões quinzenais de validação.

### 3. Troca Simulada

Como não há grupos, registrei em prosa as contribuições que viriam de outros times: sugestões de inclusão de matriz RACI para governança de prompts, métricas de adoção (percentual de microsserviços usando a última versão) e alertas de divergência entre testes automáticos e uso em produção.

### 4. Fechamento e Síntese

Encerrando, destaquei as duas descobertas mais relevantes em parágrafos corridos: a **documentação viva** em mkdocs, complementada por um webhook de QA, é o que mantém DesignOps e DevOps alinhados em cada release; e a diretriz essencial de que **cada prompt deve ser tratado como um componente versionado**, com metadados, autor, data e matriz RACI, permitindo auditoria e governança claras.

