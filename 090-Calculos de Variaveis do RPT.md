## Calculos de Variáveis

* inicialize as variaveis 'valor_imposto','valor_liquido', valor_royalti','valor_unitario',valor_imposto_tot',valor_liquido_tot' e 'valor_royalti_tot' em 0,00

* Calcule a variável 'valor_imposto'     usando a fórmula  total(valor_pis) + total(valor_cofins) + total(fatu_060.valor_icms)
* Calcule a variável 'valor_liquido'     usando a fórmula  total(fatu_060.valor_contabil) - valor_imposto
* Calcule a variável 'valor_royalti'     usando a fórmula  (valor_liquido * 18) / 100
* Calcule a variável 'valor_unitario'    usando a fórmula  valor_liquido  / total(fatu_060.qtde_item_fatur)

* Calcule a variável 'valor_imposto_tot' usando a fórmula  valor_imposto_tot + valor_imposto
* Calcule a variável 'valor_liquido_tot' usando a fórmula  valor_liquido_tot + valor_liquido
* Calcule a variável 'valor_royalti_tot' usando a fórmula  valor_royalti_tot + valor_royalti

## Fim Calculos de Variáveis