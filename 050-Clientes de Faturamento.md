## Seleção de Dados dos Clientes das Notas FIscais
* Selecione os seguintes campos da tabela pedi_010 do banco de dados Oracle para cada registro selecionado no arquivo '020-Capa da Nota Fiscal.md':
	                  'pedi_010.cgc_r',
	                  'pedi_010.cgc_o',
	                  'pedi_010.cgc_2',
	                  'pedi_010.nome_cliente',
	                  'pedi_010.fantasia_cliente',
	                  'pedi_010.situacao_cliente',
                          'pedi_010.telefone_cliente',
                          'pedi_010.endereco_cliente',
                          'pedi_010.cep_cliente',
                          'pedi_010.insc_est_cliente',
                          'pedi_010.portador_cliente',
                          'pedi_010.data_cad_cliente',
                          'pedi_010.mot_exc_cliente',
                          'pedi_010.cdrepres_cliente',
                          'pedi_010.bairro',
                          'pedi_010.cod_cidade',
                          'pedi_010.tipo_cliente',
                          'pedi_010.e_mail'
quando a seleção das informações da tabela pedi_010 obecederem aos seguintes critérios:
	                  'pedi_010.cgc_r' for = ao campo da tabela 'fatu_050.cgc_r' do arquivo '020-Capa da Nota Fiscal.md',
	                  'pedi_010.cgc_o' for = ao campo da tabela 'fatu_050.cgc_o' do arquivo '020-Capa da Nota Fiscal.md',
	                  'pedi_010.cgc_2' for = ao campo da tabela 'fatu_050.cgc_2' do arquivo '020-Capa da Nota Fiscal.md'.
## Fim da Seleção de Dados dos Clientes das Notas FIscais