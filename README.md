# 🏆 Backtest Handicap ML Pro - Versão Streamlit

Uma aplicação web avançada para análise de dados de apostas esportivas com busca gulosa otimizada para maximizar ROI.

## ✨ Funcionalidades

- **📊 Interface Web Moderna**: Design responsivo e intuitivo com gradientes e animações
- **🔍 Busca Gulosa Inteligente**: Algoritmo otimizado para encontrar os melhores filtros automaticamente
- **📈 Análise Avançada de ROI**: Cálculo preciso de retorno sobre investimento
- **🎯 Filtros Personalizáveis**: Configure quais tipos de filtros aplicar na otimização
- **📋 Relatórios Detalhados**: Geração de planilhas Excel e arquivos de configuração
- **💾 Configurações Persistentes**: Salve suas preferências de busca gulosa
- **📱 Totalmente Responsivo**: Funciona perfeitamente em desktop e mobile

## 🚀 Como Usar

### 1. Instalação

```bash
# Clone ou baixe os arquivos
# Instale as dependências
pip install -r requirements.txt
```

### 2. Executar a Aplicação

```bash
streamlit run app_streamlit.py
```

### 3. Usar a Interface

1. **📁 Upload do Arquivo**: Envie sua planilha Excel (.xlsx ou .xls) na barra lateral
2. **🎯 Configurações**: Escolha torneio, campeonato, tipo de tip e ROI desejado
3. **⚙️ Busca Gulosa**: Configure filtros avançados na barra lateral (opcional)
4. **🚀 Análise**: Clique em "Iniciar Análise" e aguarde o processamento
5. **📊 Resultados**: Visualize as etapas de otimização na tabela
6. **📄 Relatório**: Selecione uma etapa e gere relatórios Excel/TXT

## 📋 Estrutura dos Dados

Sua planilha Excel deve conter as seguintes colunas obrigatórias:

- **Torneio**: Nome do torneio/liga
- **Campeonato**: Nome do campeonato específico
- **Jogador A**: Primeiro jogador/time
- **Jogador B**: Segundo jogador/time
- **Tip**: Aposta realizada (Over/Under/nome do jogador)
- **Lucro/Prej.**: Valor numérico do lucro ou prejuízo
- **Winrate 1**: Taxa de vitória do primeiro jogador (%)
- **Winrate 2**: Taxa de vitória do segundo jogador (%)

### Colunas Opcionais (para filtros avançados):

- **Time A / Time B**: Times dos jogadores
- **Favorito / Azarão**: Classificação da aposta
- **Placar Envio**: Placar final para cálculo de diferença
- **Linha**: Linha de handicap aplicada

## 🔧 Configurações Avançadas

### Filtros da Busca Gulosa:

- **Winrate Mínimo**: Define thresholds de winrate para filtrar apostas
- **Exclusão de Campeonatos**: Remove campeonatos com performance negativa
- **Exclusão de Jogadores**: Remove apostas específicas a favor/contra jogadores
- **Exclusão de Confrontos**: Remove confrontos prejudiciais
- **Filtros de Tipo**: Filtra por favorito/azarão e mandante/visitante
- **Diferença de Placar**: Filtra por margem de vitória

### Quantidade Mínima:

Configure o número mínimo de entradas necessárias para aplicar cada filtro, evitando decisões baseadas em amostras muito pequenas.

## 📊 Como Funciona a Busca Gulosa

1. **Estado Inicial**: Carrega todos os dados filtrados por torneio/campeonato/tip
2. **Teste de Filtros**: Testa sistematicamente cada tipo de filtro habilitado
3. **Seleção Greedy**: Escolhe sempre o filtro que mais melhora o ROI
4. **Iteração**: Repete o processo até não haver mais melhorias significativas
5. **Resultado**: Produz uma sequência de etapas com ROI crescente

## 📈 Interpretando os Resultados

- **Etapa 0**: Estado inicial sem filtros
- **Etapas 1+**: Cada filtro aplicado sequencialmente
- **ROI Verde**: Valores positivos (lucro)
- **ROI Vermelho**: Valores negativos (prejuízo)
- **Apostas**: Número de entradas restantes após filtros

## 📄 Relatórios Gerados

### Arquivo Excel (com formatação completa):
- **Tips Enviadas**: Dados filtrados da etapa selecionada com fórmulas ROI
- **Confronto**: Análise agrupada por confrontos normalizados
- **Campeonato**: Performance por campeonato (se disponível)
- **Winrate 1/2**: Análise detalhada por faixas de winrate
- **Jogador**: Performance de apostas a favor de jogadores
- **Jogador Contra**: Performance de apostas contra jogadores
- **Time/Time Contra**: Performance por times (se disponível)
- **Jogador Favorito/Azarão**: Análise por favoritos/azarões (se disponível)
- **Tipo Aposta**: Análise Favorito vs Azarão (se disponível)
- **Tipo Local**: Análise Mandante vs Visitante
- **Linha**: Performance por linha de handicap
- **Placar Envio**: Análise por placar final (se disponível)
- **Diferença Placar**: Análise por diferença de gols (se disponível)

**🎨 Formatação Automática:**
- Tabelas com estilo profissional
- Cores verde/vermelho para lucro/prejuízo
- Cabeçalhos formatados
- Largura de colunas otimizada
- Formatação de números e percentuais

### Arquivo TXT:
- Configuração detalhada dos filtros aplicados
- Parâmetros da etapa selecionada
- Métricas principais (ROI, lucro, número de apostas)

## ⚠️ Requisitos do Sistema

- Python 3.8 ou superior
- Navegador web moderno
- Arquivo Excel com estrutura correta
- Mínimo 4GB de RAM (recomendado para datasets grandes)

## 🐛 Solução de Problemas

### Erro ao carregar arquivo:
- Verifique se todas as colunas obrigatórias estão presentes
- Certifique-se que os dados numéricos estão no formato correto
- Remova caracteres especiais dos nomes de colunas

### Análise muito lenta:
- Reduza a quantidade de dados ou use filtros iniciais mais restritivos
- Desabilite filtros desnecessários nas configurações avançadas
- Aumente o valor mínimo de entradas para filtros

### Nenhuma otimização encontrada:
- Verifique se há dados suficientes após filtros iniciais
- Reduza o ROI desejado
- Verifique se os filtros selecionados fazem sentido para seus dados

## 🔄 Diferenças da Versão Original

Esta versão Streamlit mantém **100% das funcionalidades** da versão desktop original, incluindo:

### ✅ **Todas as Configurações da Busca Gulosa:**
- **Filtros de Winrate**: Ajuste de Winrate 1 e 2 mínimos
- **Exclusão de Campeonatos**: Remove campeonatos prejudiciais
- **Exclusão de Jogadores**: Apostas a favor e contra jogadores específicos
- **Exclusão de Confrontos**: Remove confrontos com ROI negativo
- **Exclusão de Times**: Apostas a favor e contra times (se disponível)
- **Filtros por Tipo**: Favorito/Azarão e Mandante/Visitante
- **Filtros de Placar**: Diferença mínima e máxima de placar
- **Configurações de Quantidade**: Mínimo de entradas para cada filtro

### ✅ **Melhorias da Interface Web:**
- **Interface Moderna**: Design responsivo com gradientes e animações
- **Duas Abas Organizadas**: "Básico" para configuração e "Busca Gulosa" para filtros avançados
- **Não requer GUI**: Sem dependências tkinter/customtkinter
- **Acesso Remoto**: Via navegador de qualquer lugar
- **Tabelas Interativas**: Melhor visualização de dados
- **Downloads Diretos**: Relatórios Excel/TXT sem salvar localmente
- **Feedback Visual**: Progress bars e status em tempo real
- **Configurações Persistentes**: Salva automaticamente suas preferências

## 📞 Suporte

Para problemas ou dúvidas:
1. Verifique se sua planilha está no formato correto
2. Consulte os logs de erro na interface
3. Teste com um dataset menor primeiro
4. Verifique se todas as dependências estão instaladas

---

💡 **Dica**: Comece sempre com configurações padrão e ajuste gradualmente conforme necessário. A busca gulosa é otimizada para encontrar automaticamente os melhores filtros!
