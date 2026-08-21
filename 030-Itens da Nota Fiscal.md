## Seleção de Dados dos Itens da Nota Fiscal
* Selecione os seguintes campos da tabela fatu_060 do banco de dados Oracle para cada registro selecionado no arquivo '020-Capa da Nota Fiscal.md':
	               'fatu_060.nivel_estrutura',
	               'fatu_060.grupo_estrutura',                     
	               'fatu_060.subgru_estrutura',
	               'fatu_060.item_estrutura',
	               'fatu_060.valor_icms',
	               'fatu_060.qtde_item_fatur',
	               'fatu_060.valor_contabil'
quando a seleção das informações da tabela fatu_060 obecederem aos os seguintes critérios:
	               'fatu_060.ch_it_nf_cd_empr'  for = ao campo da tabela 'fatu_050.codigo_empresa' do arquivo '020-Capa da Nota Fiscal.md',
	               'fatu_060.ch_it_nf_num_nfis' for = ao campo da tabela 'fatu_050.num_nota_fiscal' do arquivo '020-Capa da Nota Fiscal.md',
	               'fatu_060.ch_it_nf_ser_nfis' for = ao campo da tabela 'fatu_050.serie_nota_fisc' do arquivo '020-Capa da Nota Fiscal.md'.
## Fim da Seleção de Dados dos Itens da Nota Fiscal

