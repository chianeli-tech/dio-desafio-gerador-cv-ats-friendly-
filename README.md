# dio-desafio-gerador-cv-ats-friendly-
Solução do desafio Gerador de CV ATS friendly

**Mega prompt gerado no ChatGPT**

# MEGA PROMPT — ATS CV MATCHER

Crie uma aplicação web responsiva chamada **ATS CV Matcher**.

O objetivo da aplicação é simples:
> Comparar um currículo com uma vaga de emprego, identificar o grau de aderência entre ambos e gerar uma versão do currículo otimizada para ATS (Applicant Tracking System), sem jamais inventar experiências, competências, cargos, resultados, certificações ou informações que não estejam presentes no currículo original.
A aplicação deve ser funcional de ponta a ponta, com uma interface moderna, limpa e profissional.
---
# 1. OBJETIVO PRINCIPAL DO PRODUTO

O usuário deve conseguir realizar todo o fluxo em uma única experiência:
1. Colar a descrição de uma vaga.
2. Colar seu currículo atual.
3. Solicitar a análise.
4. Visualizar:
   - score de compatibilidade;
   - palavras-chave encontradas;
   - palavras-chave relevantes ausentes;
   - competências identificadas;
   - principais pontos de aderência;
   - principais lacunas;
   - recomendações de melhoria.
5. Gerar automaticamente uma versão ATS-friendly do currículo.
6. Visualizar e editar o currículo gerado.
7. Exportar o currículo ajustado.

O núcleo da aplicação deve ser curto, objetivo e fácil de entender.
Não criar funcionalidades desnecessárias neste MVP.
---
# 2. REGRA CENTRAL DA APLICAÇÃO

Esta regra deve ser extremamente importante e deve aparecer explicitamente na interface.

## REGRA DE OURO

> **A aplicação melhora a forma como o candidato apresenta sua experiência, mas nunca inventa experiência que ele não possui.**

A aplicação NÃO pode:
- inventar empregos;
- inventar cargos;
- inventar empresas;
- inventar projetos;
- inventar resultados;
- inventar números;
- inventar certificações;
- inventar diplomas;
- inventar idiomas;
- inventar ferramentas;
- inventar tecnologias;
- inventar competências;
- inventar responsabilidades;
- atribuir ao candidato experiências apenas porque aparecem na vaga.

A aplicação PODE:
- reorganizar informações;
- melhorar redação;
- remover redundâncias;
- destacar experiências já existentes;
- utilizar palavras-chave da vaga quando houver correspondência real com o currículo;
- melhorar títulos e subtítulos;
- melhorar descrições de experiências;
- reorganizar competências;
- adaptar o resumo profissional;
- utilizar terminologia mais próxima da utilizada na vaga quando isso representar corretamente uma experiência já existente;
- tornar o currículo mais claro para sistemas ATS;
- sugerir que o candidato adicione determinada competência SOMENTE quando ela realmente existir e estiver ausente ou pouco explícita no currículo.

Quando uma palavra-chave da vaga não estiver presente no currículo, ela deve ser classificada como:
**"Ausente — não adicionar automaticamente"**
e nunca ser incorporada ao currículo como se fosse uma experiência real.
---
# 3. STACK E DESIGN SYSTEM

Utilize:
- React
- TypeScript
- Tailwind CSS
- shadcn/ui
- Lucide Icons

Utilize os componentes do shadcn/ui sempre que houver um componente equivalente.

Priorize:
- Button
- Card
- Input
- Textarea
- Badge
- Progress
- Tabs
- Alert
- Separator
- ScrollArea
- Dialog
- Tooltip
- Dropdown Menu
- Toast / Sonner
- Accordion

A aplicação deve ser totalmente responsiva.

Prioridade:
1. Desktop
2. Tablet
3. Mobile
---
# 4. PALETA VISUAL

A identidade visual deve utilizar como cores principais:
- Azul claro
- Laranja claro
- Amarelo
- Cinza

Criar uma interface profissional, mas não excessivamente corporativa.
Sugestão de distribuição:
### Azul claro
Cor principal da aplicação.
Uso:
- botões principais;
- links;
- elementos de navegação;
- destaques;
- score positivo;
- ícones principais.

### Laranja claro
Uso para:
- recomendações;
- atenção;
- itens que precisam de revisão;
- estados intermediários.

### Amarelo
Uso para:
- palavras-chave ausentes;
- alertas leves;
- pontos que merecem atenção.

### Cinza
Uso para:
- textos secundários;
- bordas;
- backgrounds;
- áreas neutras;
- divisores.

Evitar excesso de cores.
O resultado deve transmitir:
**tecnologia + clareza + confiança + empregabilidade.**
---
# 5. ESTRUTURA GERAL DA APLICAÇÃO

Criar uma aplicação SPA.
Não criar tela de login neste MVP.
Não exigir cadastro.
Não exigir autenticação.
O usuário deve conseguir entrar diretamente na aplicação e realizar uma análise.
Estrutura principal:
## HEADER
Logo textual:
**ATS CV Matcher**
Subtítulo:
**Otimize seu currículo para a vaga — sem inventar experiência.**
No lado direito:
- botão "Nova análise"
---
# 6. HOME / TELA PRINCIPAL

Criar uma tela inicial muito objetiva.
No topo:
## Título
**Compare seu currículo com uma vaga e descubra onde você realmente se encaixa.**

Texto de apoio:
**Cole a descrição da vaga e seu currículo. A aplicação identifica palavras-chave, mede a aderência e cria uma versão ATS-friendly do seu currículo, preservando fielmente sua experiência.**

Abaixo, criar duas áreas principais lado a lado no desktop.
No mobile, empilhar verticalmente.
---
# 7. ÁREA 1 — DESCRIÇÃO DA VAGA

Card:
### "1. Descrição da vaga"
Textarea grande.
Placeholder:
"Cole aqui a descrição completa da vaga..."
Adicionar contador de caracteres.
Adicionar botão:
**Exemplo de vaga**
Esse botão pode preencher a área com dados fictícios para demonstração.
Adicionar pequena orientação:

**Dica:** cole a descrição completa da vaga, incluindo responsabilidades, requisitos e competências desejadas.
---
# 8. ÁREA 2 — CURRÍCULO

Card:
### "2. Seu currículo"
Textarea grande.
Placeholder:
"Cole aqui o texto do seu currículo..."
Adicionar contador de caracteres.
Botão:
**Exemplo de currículo**
Esse botão deve preencher a área com um currículo fictício para demonstração.
Adicionar orientação:
**Dica:** use o currículo atual, mesmo que ele ainda não esteja otimizado para ATS.
---

# 9. AVISO DE INTEGRIDADE

Logo abaixo das duas áreas de entrada, criar um Alert visualmente destacado.

Título:

### "Regra de integridade"

Texto:

> **Seu currículo será otimizado, não inventado.**
>
> A aplicação pode melhorar a redação, reorganizar informações e destacar experiências relevantes. Ela nunca deve criar experiências, cargos, resultados, certificações, competências ou qualificações que não estejam presentes no currículo fornecido.

Utilizar ícone de ShieldCheck.

Esse aviso deve permanecer visível na interface principal.

---

# 10. BOTÃO PRINCIPAL

Criar um botão grande:

**Analisar compatibilidade**

Ícone:

SearchCheck ou ScanSearch.

O botão só deve ficar habilitado quando:

- descrição da vaga tiver conteúdo;
- currículo tiver conteúdo.

Ao clicar:

1. validar os campos;
2. mostrar estado de loading;
3. processar a análise;
4. exibir a página de resultados.

Loading:

**Analisando vaga e currículo...**

Mostrar etapas visuais:

- Identificando requisitos
- Extraindo palavras-chave
- Comparando competências
- Calculando compatibilidade
- Preparando recomendações

---

# 11. RESULTADO DA ANÁLISE

Após a análise, abrir uma tela:

# "Resultado da análise"

Subtítulo:

**Veja como seu currículo se relaciona com esta vaga.**

No topo, apresentar um resumo visual.

---

# 12. SCORE DE COMPATIBILIDADE

Criar um Card grande com:

### "Compatibilidade estimada"

Mostrar um score de:

**0–100**

Exemplo:

**78%**

Utilizar um Progress circular ou visual equivalente.

Importante:

Não apresentar o score como uma garantia de aprovação no processo seletivo.

Adicionar texto:

**Este índice é uma estimativa baseada na correspondência entre o conteúdo da vaga e as informações fornecidas no currículo.**

O score deve ser calculado de forma explicável.

Não utilizar um algoritmo puramente arbitrário.

---

# 13. COMO CALCULAR O SCORE

Criar uma estrutura de análise que considere pelo menos:

### Palavras-chave e termos relevantes
Peso sugerido: 30%

### Competências técnicas
Peso sugerido: 25%

### Experiência profissional / responsabilidades
Peso sugerido: 20%

### Formação e certificações
Peso sugerido: 10%

### Ferramentas / tecnologias
Peso sugerido: 10%

### Idiomas
Peso sugerido: 5%

Esses pesos podem ser ajustados caso a estrutura da vaga não contenha alguma dessas categorias.

O algoritmo deve evitar penalizar excessivamente o candidato quando uma categoria simplesmente não for relevante para aquela vaga.

---

# 14. PALAVRAS-CHAVE

Criar uma seção:

## "Palavras-chave"

Utilizar três grupos visualmente distintos.

### Encontradas

Mostrar badges das palavras-chave relevantes encontradas no currículo.

Exemplo:

- Project Management
- PMP
- Telecom
- Risk Management
- Stakeholder Management

### Parcialmente correspondentes

Mostrar termos em que existe correspondência semântica ou equivalente.

Exemplo:

Vaga:
"Project Planning"

Currículo:
"Planejamento de projetos"

Mostrar:

**Project Planning ↔ Planejamento de projetos**

### Ausentes

Mostrar palavras-chave relevantes encontradas na vaga, mas não identificadas no currículo.

Exemplo:

- Agile
- Jira
- Scrum

Ao lado de cada item:

**Não adicionar automaticamente**

Esse texto é importante.

---

# 15. CLASSIFICAÇÃO DAS PALAVRAS-CHAVE

A análise deve diferenciar:

### Correspondência exata

A expressão aparece claramente no currículo.

### Correspondência equivalente

O currículo apresenta um termo ou experiência semanticamente equivalente.

### Ausente

A competência aparece na vaga, mas não há evidência suficiente no currículo.

### Ambígua

Existe alguma possível relação, mas não há evidência suficiente para concluir que o candidato possui aquela competência.

Nunca transformar "Ambígua" em experiência confirmada.

---

# 16. COMPETÊNCIAS

Criar seção:

## "Competências identificadas"

Dividir em:

### Competências técnicas
### Competências comportamentais
### Ferramentas e tecnologias
### Idiomas
### Certificações

Para cada item, indicar:

- Encontrada
- Parcial
- Ausente

Exemplo:

| Competência | Status |
|---|---|
| Project Management | Encontrada |
| Risk Management | Encontrada |
| Agile | Ausente |
| Jira | Ausente |

---

# 17. PRINCIPAIS PONTOS DE ADERÊNCIA

Criar Card:

## "O que já está funcionando"

Mostrar os principais pontos de correspondência.

Exemplo:

✓ Experiência em gerenciamento de projetos  
✓ Certificação PMP  
✓ Experiência em projetos de telecomunicações  
✓ Inglês avançado  
✓ Experiência com stakeholders

Essas informações devem ser derivadas exclusivamente do currículo.

---

# 18. PRINCIPAIS LACUNAS

Criar Card:

## "O que a vaga pede e não aparece claramente no currículo"

Exemplo:

⚠ Experiência com metodologia Agile não identificada  
⚠ Jira não identificado  
⚠ Experiência com Scrum não identificada

Adicionar abaixo:

**Atenção: uma lacuna não significa necessariamente que você não possua essa experiência. Significa apenas que ela não foi identificada no currículo fornecido.**

Isso é importante.

---

# 19. RECOMENDAÇÕES

Criar seção:

## "Recomendações de otimização"

Mostrar recomendações práticas.

Exemplo:

### Resumo profissional
"Destacar experiência em gerenciamento de projetos e telecomunicações logo no início."

### Experiência profissional
"Dar maior destaque às atividades relacionadas a gerenciamento de projetos."

### Competências
"Reorganizar as competências para colocar primeiro aquelas relacionadas à vaga."

### Palavras-chave
"Utilizar a expressão 'Project Management' quando ela representar corretamente sua experiência já descrita como gerenciamento de projetos."

As recomendações devem sempre respeitar a regra de integridade.

---

# 20. BOTÃO PRINCIPAL DOS RESULTADOS

Adicionar CTA destacado:

**Gerar currículo ATS-friendly**

Subtexto:

**Reorganizar e adaptar seu currículo com base nesta vaga.**

Ao clicar:

Mostrar loading:

**Otimizando seu currículo...**

Etapas:

- Reorganizando conteúdo
- Ajustando terminologia
- Priorizando informações relevantes
- Verificando palavras-chave
- Validando integridade
- Preparando versão final

---

# 21. GERAÇÃO DO CURRÍCULO ATS-FRIENDLY

A aplicação deve gerar uma versão otimizada do currículo.

A estrutura preferencial deve ser:

# NOME DO CANDIDATO

Contato

Localização | Telefone | E-mail | LinkedIn

---

## RESUMO PROFISSIONAL

Resumo objetivo, adaptado à vaga.

---

## COMPETÊNCIAS

Lista organizada das competências relevantes que realmente aparecem no currículo.

---

## EXPERIÊNCIA PROFISSIONAL

### Cargo — Empresa
Período

- Responsabilidade / realização
- Responsabilidade / realização
- Responsabilidade / realização

---

## FORMAÇÃO ACADÊMICA

Curso — Instituição

---

## CERTIFICAÇÕES

Certificação — Instituição

---

## IDIOMAS

Idioma — nível

---

# 22. REGRAS ATS DO CURRÍCULO GERADO

O currículo gerado deve:

- utilizar estrutura simples;
- evitar tabelas complexas;
- evitar colunas;
- evitar gráficos;
- evitar elementos decorativos;
- evitar ícones dentro do currículo;
- evitar imagens;
- evitar barras de nível;
- evitar caixas de texto;
- evitar cabeçalhos excessivamente estilizados;
- utilizar títulos claros;
- utilizar texto selecionável;
- utilizar fontes legíveis;
- priorizar compatibilidade com sistemas ATS.

Usar estrutura linear.

Preferir:

Nome

Contato

Resumo

Competências

Experiência

Formação

Certificações

Idiomas

---

# 23. EDITOR DO CURRÍCULO

Após gerar o currículo, apresentar uma interface dividida em duas áreas.

Desktop:

### Lado esquerdo
Editor.

### Lado direito
Preview.

No mobile:

Editor acima.

Preview abaixo.

O usuário deve poder editar o conteúdo gerado antes da exportação.

---

# 24. ABA "CURRÍCULO ORIGINAL"

Adicionar uma aba:

**Original**

Mostrar o currículo enviado pelo usuário.

---

# 25. ABA "CURRÍCULO OTIMIZADO"

Adicionar:

**Otimizado**

Mostrar a versão gerada.

---

# 26. ABA "COMPARAÇÃO"

Adicionar:

**Comparar**

Mostrar diferenças relevantes entre:

Original

vs.

Otimizado

Destacar:

- termos adicionados;
- termos reorganizados;
- trechos reformulados.

Nunca permitir que uma alteração invente uma experiência.

---

# 27. VALIDAÇÃO DE INTEGRIDADE

Antes de disponibilizar a exportação, executar uma verificação final.

Criar um bloco:

## "Verificação de integridade"

Mostrar:

✓ Informações profissionais preservadas  
✓ Nenhuma experiência nova adicionada  
✓ Nenhuma certificação nova adicionada  
✓ Nenhuma formação nova adicionada  
✓ Palavras-chave utilizadas apenas quando sustentadas pelo currículo  
✓ Estrutura otimizada para ATS

Se houver algum conteúdo que não possa ser confirmado, não incluir automaticamente.

---

# 28. EXPORTAÇÃO

Criar botões:

**Exportar PDF**

**Exportar DOCX**

**Copiar currículo**

O currículo exportado deve preservar a estrutura ATS-friendly.

Para PDF:

- layout simples;
- texto selecionável;
- sem imagens;
- sem elementos gráficos desnecessários.

Para DOCX:

- títulos adequados;
- texto editável;
- estrutura simples;
- sem tabelas desnecessárias.

---

# 29. DOWNLOAD

Após exportar, mostrar toast:

**Currículo exportado com sucesso.**

Permitir que o usuário continue editando.

---

# 30. NOVA ANÁLISE

Adicionar botão:

**Nova análise**

Ao clicar:

Perguntar com Dialog:

"Começar uma nova análise?"

Opções:

**Cancelar**

**Nova análise**

Se confirmado, limpar:

- vaga;
- currículo;
- análise;
- currículo otimizado.

---

# 31. DADOS FICTÍCIOS PARA DEMONSTRAÇÃO

Criar dados fictícios realistas para que a aplicação possa ser testada sem necessidade de inserir dados reais.

Criar pelo menos um exemplo completo.

### Vaga fictícia

Cargo:

**Gerente de Projetos de Tecnologia**

Empresa:

**Tech Solutions Brasil**

Descrição contendo:

- gerenciamento de projetos;
- planejamento;
- gestão de riscos;
- stakeholders;
- orçamento;
- cronograma;
- Agile;
- Scrum;
- Jira;
- inglês;
- PMP.

### Currículo fictício

Nome:

**Carlos Almeida**

Experiência fictícia coerente:

- Gerente de Projetos;
- projetos de tecnologia;
- planejamento;
- gestão de riscos;
- gestão de stakeholders;
- orçamento;
- cronograma;
- PMP;
- inglês.

Não adicionar Agile, Scrum ou Jira ao currículo fictício se eles não estiverem originalmente presentes.

Isso deve demonstrar claramente o comportamento da aplicação.

---

# 32. MOTOR DE ANÁLISE

Estruturar a aplicação de forma que o mecanismo de análise possa posteriormente utilizar uma API de LLM.

Criar uma camada de serviço separada, por exemplo:

`analysisService`

Responsabilidades:

- extrair requisitos da vaga;
- extrair informações do currículo;
- identificar entidades;
- classificar competências;
- comparar conteúdos;
- calcular score;
- gerar recomendações;
- gerar currículo otimizado;
- executar validação de integridade.

Não acoplar a interface diretamente à implementação do LLM.

---

# 33. ESTRUTURA DE DADOS

Criar interfaces TypeScript semelhantes a:

```typescript
interface JobRequirement {
  category: string;
  keyword: string;
  importance: "high" | "medium" | "low";
  evidenceRequired: boolean;
}

interface KeywordMatch {
  keyword: string;
  status: "found" | "partial" | "missing" | "ambiguous";
  evidence?: string;
}

interface AnalysisResult {
  score: number;
  keywords: KeywordMatch[];
  competencies: {
    name: string;
    category: string;
    status: "found" | "partial" | "missing";
  }[];
  strengths: string[];
  gaps: string[];
  recommendations: string[];
}

interface OptimizedResume {
  content: string;
  changes: {
    type: "reworded" | "reordered" | "highlighted";
    description: string;
  }[];
  integrityCheck: {
    passed: boolean;
    warnings: string[];
  };
}

Pode adaptar os tipos conforme necessário.

34. LÓGICA DE IA

A aplicação deve instruir o modelo de IA de forma extremamente explícita.

Use uma instrução equivalente a:

Você é um especialista em análise de currículos e otimização para sistemas ATS.

Sua função é comparar uma descrição de vaga com um currículo fornecido pelo candidato.

Você deve melhorar a forma como o candidato apresenta experiências que já possui.

NUNCA invente informações.

Não crie:

experiências;
empregos;
cargos;
empresas;
certificações;
formações;
competências;
tecnologias;
ferramentas;
idiomas;
resultados;
números;
métricas;
responsabilidades.

Uma competência mencionada na vaga só pode ser considerada presente quando existir evidência suficiente no currículo.

Se houver equivalência semântica entre termos, marque como correspondência parcial/equivalente e explique a relação.

Se uma competência não estiver no currículo, classifique como ausente.

Não transforme uma exigência da vaga em uma característica do candidato.

Ao gerar o currículo otimizado:

preserve todos os fatos do currículo original;
reorganize informações relevantes;
melhore a redação;
utilize terminologia da vaga somente quando ela representar corretamente uma experiência já existente;
priorize as informações mais relevantes para a vaga;
elimine redundâncias;
mantenha o conteúdo factual;
não adicione informações não comprovadas.

Se houver dúvida, prefira NÃO adicionar a informação.

35. TRANSPARÊNCIA DA IA

Na interface, incluir uma pequena informação:

Como funciona?

Texto:

A análise compara os requisitos da vaga com as informações presentes no currículo. O resultado é uma estimativa de compatibilidade, não uma garantia de aprovação no processo seletivo.

36. PRIVACIDADE

Adicionar uma seção discreta:

Privacidade

Texto:

Seu currículo pode conter informações pessoais. Evite inserir dados desnecessários. A aplicação deve minimizar o armazenamento de informações pessoais sempre que possível.

Não armazenar currículos indefinidamente no MVP.

Caso seja necessário persistir dados para funcionamento da sessão, utilizar armazenamento temporário.

37. ESTADOS DA APLICAÇÃO

Implementar corretamente:

Estado inicial

Campos vazios.

Estado com dados

Campos preenchidos.

Estado de análise

Loading.

Estado de resultados

Dashboard de análise.

Estado de geração

Loading.

Estado de currículo gerado

Editor + preview.

Estado de exportação

Feedback visual.

Estado de erro

Mensagem clara e acionável.

Exemplo:

Não foi possível concluir a análise. Verifique se a descrição da vaga e o currículo possuem conteúdo suficiente e tente novamente.

38. RESPONSIVIDADE

Desktop:

Layout em duas colunas para entrada.

Resultados em cards organizados.

Editor + preview lado a lado.

Tablet:

Reduzir espaçamento.

Mobile:

Uma coluna.

Cards empilhados.

Botões principais com largura adequada.

Textareas com altura suficiente.

Não criar horizontal scrolling.

39. ACESSIBILIDADE

Utilizar:

labels;
contraste adequado;
foco visível;
navegação por teclado;
aria-label quando necessário;
botões semanticamente corretos;
mensagens de erro associadas aos campos.

Não depender exclusivamente de cores para comunicar status.

Exemplo:

Encontrado:

ícone + texto + cor

Ausente:

ícone + texto + cor

Parcial:

ícone + texto + cor

40. MICROCOPY

Manter a linguagem da aplicação em português do Brasil.

Tom:

profissional;
claro;
direto;
confiável;
amigável.

Evitar linguagem excessivamente técnica.

O usuário deve entender o produto em poucos segundos.

41. DASHBOARD DE RESULTADOS

Organizar os resultados aproximadamente assim:

Resultado da análise
Score

78%

Resumo

"Seu currículo apresenta boa correspondência com os requisitos de gerenciamento de projetos e experiência técnica."

Palavras-chave

Encontradas | Parciais | Ausentes

Competências

Encontradas | Parciais | Ausentes

Pontos fortes

Lista.

Lacunas

Lista.

Recomendações

Lista.

CTA

Gerar currículo ATS-friendly

42. DESIGN DOS CARDS

Utilizar:

bordas suaves;
border-radius moderado;
sombras discretas;
bastante espaço em branco;
hierarquia tipográfica clara.

Não exagerar em:

gradientes;
animações;
efeitos 3D;
glassmorphism;
sombras pesadas.

A aplicação deve parecer uma ferramenta profissional de produtividade.

43. ANIMAÇÕES

Usar animações sutis:

fade-in;
progress;
loading;
transições de tabs.

Evitar animações que atrasem o fluxo.

44. ÍCONES

Utilizar Lucide Icons.

Sugestões:

FileText
SearchCheck
CheckCircle2
AlertTriangle
XCircle
ShieldCheck
Sparkles
Download
Copy
RefreshCw
ArrowRight
Check
Info
Lightbulb
45. ARQUITETURA

Organizar o código de forma modular.

Sugestão:

src/
  components/
    Header.tsx
    JobInput.tsx
    ResumeInput.tsx
    IntegrityNotice.tsx
    AnalysisScore.tsx
    KeywordMatches.tsx
    CompetencyMatches.tsx
    StrengthsCard.tsx
    GapsCard.tsx
    RecommendationsCard.tsx
    ResumeEditor.tsx
    ResumePreview.tsx
    IntegrityCheck.tsx
    ExportButtons.tsx

  pages/
    Home.tsx
    Analysis.tsx
    ResumeOptimization.tsx

  services/
    analysisService.ts
    resumeService.ts
    exportService.ts

  types/
    analysis.ts
    resume.ts

  data/
    demoData.ts

A estrutura pode ser adaptada conforme a arquitetura padrão do Lovable.

46. MVP — NÃO CRIAR AGORA

Não implementar neste primeiro MVP:

login;
cadastro;
pagamento;
assinatura;
histórico de currículos;
dashboard administrativo;
banco de dados complexo;
sistema de usuários;
integração com LinkedIn;
candidatura automática;
scraping de vagas;
envio automático de currículo;
acompanhamento de processos seletivos;
notificações;
marketplace;
sistema de recrutadores.

O produto deve concentrar-se exclusivamente no fluxo:

Vaga → Currículo → Match → Recomendações → Currículo ATS-friendly → Exportação

47. EXPERIÊNCIA PRINCIPAL

O usuário deve conseguir chegar ao resultado com o menor número possível de cliques.

Fluxo ideal:

HOME
  ↓
Colar vaga
  ↓
Colar currículo
  ↓
Analisar compatibilidade
  ↓
RESULTADO
  ↓
Gerar currículo ATS-friendly
  ↓
Editar
  ↓
Verificar integridade
  ↓
Exportar
48. CRITÉRIOS DE ACEITAÇÃO

A aplicação estará correta quando:

O usuário conseguir colar uma vaga.
O usuário conseguir colar um currículo.
O sistema conseguir analisar os dois.
O sistema apresentar um score de compatibilidade.
O sistema apresentar palavras-chave encontradas.
O sistema apresentar palavras-chave ausentes.
O sistema identificar competências.
O sistema mostrar pontos de aderência.
O sistema mostrar lacunas.
O sistema apresentar recomendações.
O usuário conseguir gerar uma versão ATS-friendly.
O usuário conseguir editar a versão gerada.
O usuário conseguir comparar original e otimizado.
O sistema executar uma verificação de integridade.
O usuário conseguir exportar o currículo.
O sistema nunca adicionar automaticamente experiência que não esteja comprovada.
O aviso sobre não inventar experiências aparecer claramente na interface.
O sistema funcionar sem login.
A aplicação funcionar em desktop e mobile.
A interface utilizar shadcn/ui.
A identidade visual utilizar azul claro, laranja claro, amarelo e cinza.
Os dados fictícios permitirem testar o fluxo completo.
49. PRINCÍPIO FINAL DE UX

A aplicação deve responder rapidamente à pergunta do usuário:

"O quanto meu currículo está alinhado com esta vaga e como posso apresentá-lo melhor sem mentir?"

Toda decisão de interface deve servir a essa pergunta.

Não transformar o produto em um sistema complexo de recrutamento.

O MVP deve ser:

simples → rápido → transparente → útil → confiável.

Construa agora a aplicação completa seguindo todas as especificações acima.


