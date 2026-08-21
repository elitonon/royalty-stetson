## Seleção de Dados linha-colecao-artigos-conta-descricao
* Selecione os seguintes campos da tabela basi_030 do banco de dados Oracle para cada registro selecionado no arquivo '030-Itens da Nota Fiscal.md':
	                  'basi_030.linha_produto',
	                  'basi_030.artigo',
	                  'basi_030.descr_referencia',
	                  'basi_030.artigo_cotas',
	                  'basi_030.conta_estoque'
quando a seleção das informações da tabela basi_030 obecederem aos seguintes critérios:
	                  'basi_030.nivel_estrutura' for = ao campo da tabela 'fatu_060.nivel_estrutura' do arquivo '030-Itens da Nota Fiscal.md',
	                  'basi_030.referencia'      for = ao campo da tabela 'fatu_060.grupo_estrutura' do arquivo '030-Itens da Nota Fiscal.md',
	                  'basi_030.artigo_cotas'    for = 6 --STETSON
## Fim da Seleção de Dados linha-colecao-artigos-conta-descricao
