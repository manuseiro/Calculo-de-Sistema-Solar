# Calculadora de Retorno do Sistema Solar

Este é um script para calcular o retorno de um sistema solar com base em algumas configurações fornecidas pelo usuário. Ele calcula a capacidade do sistema solar, a quantidade de energia gerada por mês, a economia mensal em reais, a economia anual em reais e a quantidade de CO2 não emitida tanto mensal quanto anualmente.

## Como usar

1. Preencha as configurações do sistema solar:
   - **Quantidade de Módulos:** O número de módulos solares no sistema.
   - **Potência do Módulo (Watts):** A potência de cada módulo em watts.
   - **Horas de Sol por Dia:** A média de horas de sol por dia na sua região.
   - **Tarifa de Energia Elétrica (R$/kWh):** O valor da tarifa de energia elétrica aplicável ao seu caso.

2. Clique no botão "Calcular".

## Fórmulas

Aqui estão as fórmulas utilizadas para calcular cada resultado:

1. **Capacidade Total do Sistema Solar (kW):**
```
Capacidade Total do Sistema Solar (kW) = (Quantidade de Módulos * Potência do Módulo) / 1000
```

2. **kWh Gerado p/Mês:**
```
kWh Gerado p/Mês = Capacidade Total do Sistema Solar (kW) * Horas de Sol por Dia * 30
```
*Observação: Supõe-se que o mês tem 30 dias.*

3. **Economia Mensal (R$):**
```
Economia Mensal (R$) = kWh Gerado p/Mês * Tarifa de Energia Elétrica
```
4. **Economia Anual (R$):**
```
Economia Anual (R$) = Economia Mensal (R$) * 12
```
5. **CO2 não Emitidas P/Mês (Toneladas):**

```
CO2 não Emitidas P/Mês (Toneladas) = kWh Gerado p/Mês * Média de Emissão de CO2 por kWh / 1.000.000
```
*Observação: Supõe-se que a média de emissão de CO2 por kWh é de 0,4404 kg/kWh.*

6. **CO2 não Emitidas P/Ano (Toneladas):**
```
CO2 não Emitidas P/Ano (Toneladas) = CO2 não Emitidas P/Mês (Toneladas) * 12
```

## Exemplo de Uso

Suponha que as seguintes configurações sejam fornecidas:

- Quantidade de Módulos: 95
- Potência do Módulo: 410 Watts
- Horas de Sol por Dia: 5 horas
- Tarifa de Energia Elétrica: R$ 0,50 por kWh

Os resultados seriam os seguintes:

- Capacidade Total do Sistema Solar (kW): 38,95 kW
- kWh Gerado p/Mês: 5.842,5 kWh
- Economia Mensal (R$): R$ 2.921,25
- Economia Anual (R$): R$ 34.353,9
- CO2 não Emitidas P/Mês (Toneladas): 2,573037 toneladas
- CO2 não Emitidas P/Ano (Toneladas): 30,876444 toneladas

## Observações

- O script utiliza a biblioteca jQuery e o framework Bootstrap para fornecer uma interface interativa.
- Os valores são arredondados para duas casas decimais.

Espero que este arquivo README.md tenha sido útil para entender o funcionamento do script de cálculo do retorno do sistema solar.
