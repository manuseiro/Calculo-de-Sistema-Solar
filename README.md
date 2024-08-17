# Calcular o retorno de sistemas de energia solar

Este projeto é uma ferramenta web simples que permite calcular o retorno de um sistema de energia solar baseado em diversas variáveis, como consumo mensal, quantidade de módulos solares, tarifa de energia elétrica, e outros fatores. Além disso, a aplicação calcula a quantidade de CO2 que deixará de ser emitido devido ao uso de energia solar.

## Funcionalidades

- **Cálculo da Capacidade Total do Sistema Solar**: Calcula a capacidade total do sistema solar com base na quantidade e potência dos módulos solares.
- **Estimativa da Energia Gerada por Mês**: Estima a quantidade de energia gerada mensalmente, levando em conta as horas de sol na localização especificada.
- **Cálculo da Economia Mensal e Anual**: Calcula quanto dinheiro será economizado com a geração de energia solar.
- **Estimativa de CO2 Não Emitido**: Calcula a quantidade de CO2 que deixará de ser emitido com base na energia gerada pelo sistema solar.
- **Sugestão de Quantidade de Módulos**: Sugere a quantidade de módulos solares necessários com base no consumo médio mensal informado.
- **Seleção Dinâmica de Cidade e Estado**: Preenche automaticamente os campos de cidade e estado com base em dados obtidos das APIs do IBGE e OpenCage.

## Tecnologias Utilizadas

- **HTML/CSS**: Estrutura e estilização da interface.
- **JavaScript (jQuery)**: Manipulação do DOM e cálculo dinâmico dos valores.
- **APIs Externas**:
  - [OpenCage Geocoder](https://opencagedata.com/): Utilizada para converter o nome da cidade e estado em coordenadas geográficas (latitude e longitude).
  - [Sunrise-Sunset API](https://sunrise-sunset.org/api): Utilizada para calcular as horas de sol por dia na localização especificada.
  - [IBGE API de localidades](https://servicodados.ibge.gov.br/api/v1/localidades/): Utilizada para obter a lista de estados e cidades do Brasil.

## Como Usar

1. **Clone o Repositório**: Clone o repositório para o seu ambiente local.

   ```bash
   git clone https://github.com/seu-usuario/calcular-rss.git
   ```
   
2. **Navegue até o Diretório**: Entre na pasta do projeto.

	```bash
	cd calculadora-solar
	```

Abra o arquivo HTML: Você pode abrir o arquivo index.html no seu navegador preferido para utilizar a calculadora.

Preencha os Campos: Insira as informações necessárias como a cidade, estado, consumo médio mensal, quantidade de módulos solares, potência do módulo, tarifa de energia elétrica, e o fator de emissão de CO2.

Calcule o Retorno: Clique em "Calcular" para visualizar os resultados, incluindo a economia mensal, anual, e a quantidade de CO2 não emitida.

## Uso/Exemplos

**Capacidade Total do Sistema Solar (kW)**: Esse campo calcula a capacidade total do sistema solar em quilowatts (kW). A potência de cada módulo é dada em watts (W), então é necessário dividir por 1000 para converter para kW.

    Capacidade Total do Sistema Solar = Quantidade de Módulos * Potência do Módulo / 1000

**Exemplo:** Se você tiver 10 módulos de 400 W cada, a capacidade total será:

    Capacidade Total = 10 * 400 / 1000 = 4 kW

**Horas de Sol por Dia**: Este valor é calculado utilizando a API Sunrise-Sunset, que retorna o horário do nascer e pôr do sol com base nas coordenadas geográficas da cidade informada. A diferença entre o pôr do sol e o nascer do sol dá o total de horas de sol disponíveis por dia na localidade.

    Horas de Sol por Dia = (Horário do Pôr do Sol - Horário do Nascer do Sol) em horas
    

**Exemplo:** Se o sol nascer às 6:00 e se pôr às 18:00, as horas de sol por dia serão:

    Horas de Sol por Dia = 18:00 - 6:00 = 12 horas

**kWh Gerado por Mês**: Este cálculo estima a energia gerada por mês em kilowatt-hora (kWh). Multiplica-se a capacidade total do sistema solar pelas horas de sol por dia e, em seguida, pelo número médio de dias no mês (30).


    kWh Gerado por Mês = Capacidade Total do Sistema Solar * Horas de Sol por Dia * 30
    
**Exemplo:** Para um sistema de 4 kW e 5 horas de sol por dia:

    kWh Gerado por Mês = 4 * 5 * 30 = 600 kWh

**Economia Mensal (R$)**: A economia mensal em reais (R$) é calculada multiplicando-se a quantidade de energia gerada por mês (em kWh) pela tarifa de energia elétrica (em R$/kWh).
Economia Mensal (R$)

    Economia Mensal = kWh Gerado por Mês * Tarifa de Energia Elétrica

**Exemplo:** Se a energia gerada for 600 kWh e a tarifa for R$0,50/kWh:

    Economia Mensal = 600 * 0,50 = R$ 300,00

**Economia Anual (R$)**: A economia anual é simplesmente 12 vezes a economia mensal, assumindo que o sistema gera a mesma quantidade de energia todos os meses.

    Economia Anual = Economia Mensal * 12

**Exemplo:** Se a economia mensal for R$ 300,00:

    Economia Anual = 300 * 12 = R$ 3.600,00

**CO2 Não Emitido por Mês (kg CO2)**: Este campo estima a quantidade de dióxido de carbono (CO2) que deixaria de ser emitida devido à geração de energia solar. O fator de emissão de CO2 é a quantidade de CO2 emitido por kWh de eletricidade gerada por fontes não renováveis (normalmente expressa em kg CO2/kWh).

    CO2 Não Emitido por Mês = kWh Gerado por Mês * Fator de Emissão de CO2

**Exemplo:** Para 600 kWh gerados por mês e um fator de emissão de 0,092 kg CO2/kWh:

    CO2 Não Emitido por Mês = 600 * 0,092 = 55,2 kg CO2

**CO2 Não Emitido por Ano (kg CO2)**: A quantidade de CO2 não emitido por ano é calculada multiplicando-se o valor mensal por 12.

    CO2 Não Emitido por Ano = CO2 Não Emitido por Mês * 12

**Exemplo:** Se a quantidade de CO2 não emitido por mês for 55,2 kg:

    CO2 Não Emitido por Ano = 55,2 * 12 = 662,4 kg CO2

**Sugestão de Quantidade de Módulos**: Este cálculo sugere a quantidade de módulos solares necessária para cobrir o consumo mensal médio. Ele é baseado no consumo de energia (kWh), nas horas de sol disponíveis, e na potência de cada módulo.

    Quantidade de Módulos Sugerida = Consumo Mensal / (Horas de Sol por Dia * 30 * Potência do Módulo / 1000)

**Exemplo:** Para um consumo de 500 kWh/mês, 5 horas de sol/dia, e módulos de 400 W:

    Quantidade de Módulos Sugerida = 500 / (5 * 30 * 0,4) ≈ 8,33 módulos (arredondado para 9 módulos)

## Customização

Você pode personalizar o cálculo alterando os valores padrões no código, como o fator de emissão de CO2 ou adicionando novas funcionalidades.

## Contribuindo

Se você quiser contribuir com este projeto, sinta-se à vontade para fazer um fork do repositório, criar um branch para suas modificações e enviar um pull request.

1. Faça o fork do projeto.
2. Crie um branch para sua feature ('git checkout -b feature/sua-feature').
3. Commit suas mudanças ('git commit -m 'Adicionar nova feature').
4. Envie para o branch ('git push origin feature/sua-feature').
5. Crie um novo Pull Request.
	
## Licença

Este projeto está licenciado sob a MIT License.

Este README foi gerado para a Calculadora de Retorno do Sistema Solar, uma aplicação web para ajudar na estimativa de retorno financeiro e ambiental de sistemas solares fotovoltaicos.
