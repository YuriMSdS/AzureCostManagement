# AzureCostManagement

## Introdução
O projeto aborda a Otimização de Custos no Azure e faz parte do exame AZ 900,  tem como objetivo principal explorar e implementar estratégias para reduzir os custos associados ao uso da plataforma Azure. À medida que os recursos são migrados para a nuvem, é fundamental entender como gerenciar e otimizar gastos para garantir um retorno máximo sobre o investimento.

## Importância da otimização de custos
A nuvem oferece flexibilidade e escalabilidade, mas também pode levar a despesas inesperadas se não forem geridas corretamente. Este projeto aborda questões como:
- Quais recursos estamos usando realmente?
- Estamos pagando mais do que deveríamos por serviços que não utilizamos?
- Como podemos otimizar nossa infraestrutura para reduzir custos?

## Objetivos
- **Analisar os Gastos Atuais**: Entender onde e como está sendo gastando na plataforma Azure.
- **Identificar Oportunidades de Economia**: Encontrar áreas nas quais é possível reduzir custos sem comprometer a eficiência.
- **Implementar Melhores Práticas**: Adotar práticas recomendadas para a gestão e monitoramento de custos na nuvem.

## Metodologia
O projeto será desenvolvido em várias etapas, sendo:

### 1. **Monitoramento de Custos**
Usar o **Azure Cost Management** para acompanhar e analisar os gastos. Isso incluirá:
- Configurar painéis de controle que forneçam visibilidade sobre os custos.
- Analisar tendências de gastos ao longo do tempo.

### 2. **Dimensionamento de Recursos**
O objetivo é garantir que estamos utilizando o tamanho adequado de recursos. Isso envolve:
- Avaliar o uso atual de máquinas virtuais, bancos de dados e outros serviços.
- Ajustar o tamanho dos recursos com base na demanda real.

### 3. **Automação de Desligamento de Recursos**
Desenvolver scripts para desligar recursos que não estão em uso, como:
- Máquinas virtuais que ficam ligadas fora do horário de trabalho.
- Serviços que podem ser desativados durante períodos de baixa atividade.

### 4. **Utilização de Instâncias Reservadas**
Explorar como e quando usar instâncias reservadas para economizar em comparação com o modelo de pagamento sob demanda. Isso inclui:
- Calcular o custo total de propriedade (TCO) para diferentes opções.
- Analisar a viabilidade de compromissos de longo prazo.

## Ferramentas e Recursos Utilizados
- **Azure Cost Management + Billing**: Para monitorar e gerenciar gastos.
- **Azure Advisor**: Para obter recomendações sobre otimização de recursos.
- **PowerShell e Azure CLI**: Para automação e gerenciamento de recursos.

## Como fazer
#### Utilizando Azure Cost Management

- **Avaliar o Uso Atual de Recursos**:
  1. No portal do Azure, acesse a seção de **Máquinas Virtuais**.
  2. Verifique métricas de uso, como CPU, memória e I/O.
  
- **Comparar com as Necessidades**:
  1. Identifique se os recursos estão sobrecarregados ou subutilizados.
  2. Use o Azure Advisor para receber recomendações de dimensionamento.

- **Ajustar Tamanhos de Recursos**:
  1. Caso identifique recursos subutilizados, reduza o tamanho da máquina virtual ou mude para um SKU mais adequado.
  2. Para recursos sobrecarregados, considere aumentar a capacidade ou adicionar instâncias adicionais.

#### Com dimensionamento de recursos

- **Avaliar o Uso Atual de Recursos**:
  1. No portal do Azure, acesse a seção de **Máquinas Virtuais**.
  2. Verifique métricas de uso, como CPU, memória e I/O.
  
- **Comparar com as Necessidades**:
  1. Identifique se os recursos estão sobrecarregados ou subutilizados.
  2. Use o Azure Advisor para receber recomendações de dimensionamento.

- **Ajustar Tamanhos de Recursos**:
  1. Caso identifique recursos subutilizados, reduza o tamanho da máquina virtual ou mude para um SKU mais adequado.
  2. Para recursos sobrecarregados, considere aumentar a capacidade ou adicionar instâncias adicionais.

#### Através da automação de desligamento de recursos

- **Criar Scripts de Automação**:
  1. Utilize **Azure Automation** para criar runbooks que desliguem recursos fora do horário comercial.
  2. Exemplo de script em PowerShell:
     ```powershell
     $resourceGroupName = "RG-DEV" #Nome do RG
     $vmName = "VirtualMachine1" #Nome da VM
     Stop-AzVM -ResourceGroupName $resourceGroupName -Name $vmName -Force
     ```
- **Agendar Execuções**:
  1. Agende o runbook para ser executado em horários específicos usando o **Azure Scheduler** ou o **Azure Logic Apps**.
  2. Teste os scripts para garantir que apenas os recursos desejados sejam desligados.

- **Monitorar e Ajustar**:
  1. Revise regularmente quais recursos estão sendo desligados e se há necessidade de ajustes no horário ou na configuração.

#### Utilizando instâncias reservadas

- **Analisar Necessidades de Longo Prazo**:
  1. Avalie os recursos que você usa regularmente e que podem se beneficiar de um compromisso de longo prazo.
  
- **Calcular o Custo Total de Propriedade (TCO)**:
  1. Utilize a **Calculadora TCO do Azure** para comparar os custos de instâncias sob demanda e reservadas.
  2. Considere fatores como descontos por comprometimento de 1 ou 3 anos.

- **Comprar Instâncias Reservadas**:
  1. No portal do Azure, acesse **Máquinas Virtuais** e selecione **Instâncias Reservadas**.
  2. Siga o processo para comprar instâncias reservadas com base na análise anterior.

- **Revisar e Ajustar**:
  1. Acompanhe os custos e a utilização das instâncias reservadas ao longo do tempo.
  2. Reavalie anualmente para garantir que as reservas ainda atendem às suas necessidades.

## Referências
- [Calculadora TCO do Azure](https://azure.microsoft.com/en-us/pricing/tco/calculator/): Uma ferramenta útil para estimar o custo total de propriedade de serviços em nuvem.
- [Documentação Oficial do Azure](https://docs.microsoft.com/azure/): Recursos e guias sobre todos os serviços disponíveis no Azure.
