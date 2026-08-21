### PRIMEIRA ETAPA - FATURAMENTO

## Seleção de Dados da Capa da Nota Fiscal

* Selecione os seguintes campos da tabela fatu_050 do banco de dados Oracle:
	         'fatu_050.num_nota_fiscal',
	         'fatu_050.serie_nota_fisc',                                     
	         'fatu_050.data_emissao',
	         'fatu_050.cgc_r',
	         'fatu_050.cgc_o',
	         'fatu_050.cgc_2'
quando a seleção das informações da tabela fatu_050 obecederem aos seguintes critérios:
	         'fatu_050.codigo_empresa' for  = ao campo de tela 'codigo empresa' do arquivo '010-Tela.md',
                 'fatu_050.data_emissao'   for >= que o campo da tela 'data inicial' do arquivo '010-Tela.md',
	         'fatu_050.data_emissao'   for <= que o campo da tela 'data final' do arquivo '010-Tela.md',
	         'fatu_050.situacao_nfisc' for <> 2
	         'fatu_050.pedido_venda'   for  > 0.
## Fim da Seleção de Dados da Capa da Nota Fiscal
