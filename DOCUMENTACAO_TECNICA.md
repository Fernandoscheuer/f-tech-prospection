# F-Tech Prospection - Documentação Técnica

## Visão Geral

A **F-Tech Prospection** é uma plataforma web especializada em prospecção empresarial para os segmentos de **Redes de Computadores** e **Segurança Eletrônica**. A plataforma oferece busca avançada com filtros geográficos e exportação de dados em múltiplos formatos.

## Funcionalidades Principais

### 🎯 Sistema de Filtros
- **Filtro por Estados**: Seleção individual ou múltipla de todos os 27 estados brasileiros
- **Filtro por Segmento**: Duas opções especializadas:
  - Redes de Computadores
  - Segurança Eletrônica

### 🔍 Sistema de Busca
- **Busca por CNAEs**: Utiliza códigos CNAE específicos para cada segmento
- **Busca por Palavras-chave**: Mais de 100 termos técnicos por segmento
- **Validação de Entrada**: Exige seleção de segmento antes da busca
- **Resultados Estruturados**: Exibe informações completas das empresas

### 📊 Sistema de Exportação
- **CSV**: Para análise em planilhas (Excel, Google Sheets)
- **Excel**: Formato .xls compatível com Microsoft Office
- **JSON**: Para integração com outros sistemas e APIs
- **Relatório**: Documento completo em texto com estatísticas

## Arquitetura Técnica

### Frontend
- **Framework**: React 18 com Vite
- **Estilização**: TailwindCSS + Shadcn/UI
- **Ícones**: Lucide React
- **Responsividade**: Mobile-first design

### Serviços
- **empresaService.js**: Gerencia busca e integração com APIs
- **exportService.js**: Gerencia exportação em múltiplos formatos
- **keywords.js**: Contém palavras-chave e CNAEs por segmento

### APIs Integradas (Preparado para)
- **CNPJ.ws**: API comercial para dados empresariais
- **Brasil API**: API gratuita para consulta de CNPJ
- **Dados Simulados**: Sistema de demonstração funcional

## Estrutura de Dados

### Empresa
```javascript
{
  id: string,
  cnpj: string,
  nome: string,
  nomeFantasia: string,
  telefone: string,
  email: string,
  endereco: string,
  cidade: string,
  estado: string,
  cep: string,
  cnae: string,
  atividade: string,
  segmento: string
}
```

## CNAEs por Segmento

### Redes de Computadores
- `6209-1/00` - Suporte técnico em TI
- `6204-0/00` - Consultoria em TI
- `6202-3/00` - Desenvolvimento de software customizável
- `6203-1/00` - Desenvolvimento de software não customizável
- `6190-6/01` - Provedores de acesso à rede
- `4751-2/01` - Comércio varejista de equipamentos de informática
- `4651-1/00` - Comércio atacadista de equipamentos de informática
- E outros...

### Segurança Eletrônica
- `8020-0/01` - Monitoramento de sistemas de segurança
- `8020-0/02` - Outras atividades de segurança
- `8011-1/01` - Vigilância e segurança privada
- `4321-5/00` - Instalações elétricas
- E outros...

## Palavras-chave por Segmento

### Redes de Computadores (Exemplos)
- Infraestrutura: rede, networking, cabeamento, fibra óptica
- Equipamentos: switch, roteador, firewall, wi-fi
- Serviços: suporte técnico, consultoria TI, help desk
- Tecnologias: servidor, cloud, virtualização, backup

### Segurança Eletrônica (Exemplos)
- Sistemas: CFTV, alarme, controle de acesso, monitoramento
- Equipamentos: câmera, sensor, central de alarme, biometria
- Serviços: instalação, manutenção, consultoria
- Tecnologias: reconhecimento facial, inteligência artificial

## Instalação e Configuração

### Pré-requisitos
- Node.js 18+
- pnpm ou npm
- Navegador moderno

### Instalação Local
```bash
# Clone o repositório
git clone [URL_DO_REPOSITORIO]

# Instale as dependências
cd f-tech-prospection
pnpm install

# Execute em desenvolvimento
pnpm run dev

# Build para produção
pnpm run build
```

### Configuração de APIs
Para integração com APIs reais, configure as variáveis de ambiente:

```env
REACT_APP_CNPJ_WS_API_KEY=sua_chave_cnpj_ws
REACT_APP_BRASIL_API_URL=https://brasilapi.com.br/api
```

## Uso da Plataforma

### 1. Seleção de Filtros
1. **Estados**: Clique em "Selecionar Todos" ou escolha estados específicos
2. **Segmento**: Selecione "Redes de Computadores" ou "Segurança Eletrônica"

### 2. Execução da Busca
1. Clique no botão "Buscar"
2. Aguarde o processamento (indicador de loading)
3. Visualize os resultados na seção "Resultados da Busca"

### 3. Exportação de Dados
1. Clique no dropdown "Exportar"
2. Selecione o formato desejado (CSV, Excel, JSON, Relatório)
3. O arquivo será baixado automaticamente

## Limitações Atuais

### Dados de Demonstração
- A versão atual utiliza dados simulados para demonstração
- Para uso em produção, é necessário integrar com APIs reais

### Limites de API
- **CNPJ.ws**: 3 consultas/minuto (versão gratuita)
- **Brasil API**: Uso moderado recomendado

### Escalabilidade
- Para grandes volumes, considere implementar cache
- Rate limiting para evitar sobrecarga das APIs

## Roadmap de Melhorias

### Versão 2.0
- [ ] Integração completa com APIs reais
- [ ] Sistema de cache para otimização
- [ ] Filtros adicionais (porte, faturamento)
- [ ] Histórico de buscas
- [ ] Dashboard com estatísticas

### Versão 3.0
- [ ] Sistema de usuários e autenticação
- [ ] Salvamento de listas de prospecção
- [ ] Integração com CRM
- [ ] API própria para terceiros

## Suporte e Manutenção

### Logs e Debugging
- Console do navegador para erros de frontend
- Network tab para monitorar chamadas de API
- Validação de dados antes de exportação

### Performance
- Lazy loading de componentes
- Debounce em filtros dinâmicos
- Paginação para grandes resultados

### Segurança
- Sanitização de dados de entrada
- Validação de CNPJs
- Rate limiting nas APIs

## Contato e Suporte

Para dúvidas técnicas ou sugestões de melhorias:
- Documentação completa no código-fonte
- Comentários detalhados em cada serviço
- Estrutura modular para fácil manutenção

---

**F-Tech Prospection Platform**  
*Versão 1.0 - 2024*  
*Desenvolvido com React, TailwindCSS e APIs brasileiras*
