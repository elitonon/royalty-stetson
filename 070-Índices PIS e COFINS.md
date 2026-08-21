## Seleção de Dados dos Índices do PIS e COFINS
* Selecione uma única vez A VARIÁVEL 'indice_pis' usando o campo 'rcnb_070.consumo' da tabela rcnb_070 do banco de dados Oracle,
quando a seleção das informações da tabela rcnb_070 obecederem aos seguintes critérios:
	                     'rcnb_070.codigo_empresa'   for  = ao campo da tabela 'fatu_050.codigo_empresa' do arquivo '020-Capa da Nota Fiscal.md',
	                     'rcnb_070.codigo_parametro' for  = 10.
* Selecione uma única vez a variável 'indice_cofins' usando o campo 'rcnb_070.consumo' da tabela rcnb_070 do banco de dados Oracle,
quando a seleção das informações da tabela rcnb_070 obecederem ao seguintes critérios:
	                     'rcnb_070.codigo_empresa'   for  = ao campo da tabela 'fatu_050.codigo_empresa' do arquivo '020-Capa da Nota Fiscal.md',
	                     'rcnb_070.codigo_parametro' for  = 11.
## Fim da Seleção de Dados dos Índices do PIS e COFINS
