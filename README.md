# Calculadora de Retorno do Sistema Solar

Este é um script para calcular o retorno de um sistema solar com base em algumas configurações fornecidas pelo usuário. Ele calcula a capacidade do sistema solar, a quantidade de energia gerada por mês, a economia mensal em reais, a economia anual em reais e a quantidade de CO2 não emitida tanto mensal quanto anualmente.

## Como usar

1.Preencha as configurações do sistema solar:
- **Cidade:** A cidade onde o sistema será instalado.
- **Estado:** O estado onde o sistema será instalado.
- **Quantidade de Módulos:** O número de módulos solares no sistema.
- **Potência do Módulo (Watts):** A potência de cada módulo em watts.
- **Tarifa de Energia Elétrica (R$/kWh):** O valor da tarifa de energia elétrica aplicável ao seu caso.

2. Clique no botão "Calcular".

## Fórmulas

Aqui estão as fórmulas utilizadas para calcular cada resultado:

1. **Capacidade Total do Sistema Solar (kW):**

```
Capacidade Total do Sistema Solar (kW) = (Quantidade de Módulos * Potência do Módulo) / 1000
```
 2. **Horas de Sol por Dia:** Obtidas pela API sunrise-sunset com base nas coordenadas geográficas da cidade e estado fornecidos.

 3. **kWh Gerado p/Mês:**

```
kWh Gerado p/Mês = Capacidade Total do Sistema Solar (kW) * Horas de Sol por Dia * 30
```
Observação: Supõe-se que o mês tem 30 dias.

 4. **Economia Mensal (R$):**

```
Economia Mensal (R$) = kWh Gerado p/Mês * Tarifa de Energia Elétrica
```

 5. **Economia Anual (R$):**

```

Economia Anual (R$) = Economia Mensal (R$) * 12
```

## Exemplo de Uso

Suponha que as seguintes configurações sejam fornecidas:

 - Cidade: Fortaleza
 - Estado: Ceará
 - Quantidade de Módulos: 95
 - Potência do Módulo: 410 Watts
 - Tarifa de Energia Elétrica: R$ 0,50 por kWh

Os resultados seriam os seguintes (considerando 5 horas de sol por dia, como exemplo):

 - Capacidade Total do Sistema Solar (kW): 38,95 kW
 - kWh Gerado p/Mês: 5.842,5 kWh
 - Economia Mensal (R$): R$ 2.921,25
 - Economia Anual (R$): R$ 34.353,00
 - CO2 não Emitidas P/Mês (Toneladas): 2,573037 toneladas
 - CO2 não Emitidas P/Ano (Toneladas): 30,876444 toneladas

## Tecnologias utilizadas

 - HTML
 - Bootstrap 5.3.0
 - jQuery 3.6.0
 - jQuery InputMask 5.0.6

## Observações

 - O script utiliza a API OpenCage Geocoder para converter cidade e estado em coordenadas geográficas.
 - O script utiliza a API sunrise-sunset para obter as horas de sol por dia com base nas coordenadas geográficas.
 - Os valores são arredondados para duas casas decimais.
 - O script utiliza a biblioteca jQuery e o framework Bootstrap para fornecer uma interface interativa.
