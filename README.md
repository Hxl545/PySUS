# PySUS

Utilizing Google Collaboration

Installation of PYSUS and GEOPANDAS, necessary to run file

	!pip install pysus
	!pip install geopandas

Imports

	from pysus.preprocessing.sinan import read_sinan_dbf
	from pysus.online_data import parquets_to_dataframe
	from pysus.utilities.readdbc import read_dbc
	from pysus.online_data.sinasc import download
	from pysus.online_data.SIH import download
	from pysus.online_data.CIHA import download
	from pysus.online_data.SIA import download
	from pysus.online_data import SINAN
	import pandas as pd
	
List of Diseases

	SINAN.list_diseases()
	
	['Animais Peçonhentos',
 	'Botulismo',
	'Cancer',
 	'Chagas',
	'Chikungunya',
 	'Colera',
	'Coqueluche',
	'Contact Communicable Disease',
	'Acidentes de Trabalho',
	'Dengue',
	'Difteria',
	'Esquistossomose',
	'Febre Amarela',
	'Febre Maculosa',
	'Febre Tifoide',
	'Hanseniase',
	'Hantavirose',
	'Hepatites Virais',
	'Intoxicação Exógena',
	'Leishmaniose Visceral',
	'Leptospirose',
	'Leishmaniose Tegumentar',
	'Malaria',
	'Meningite',
	'Peste',
	'Poliomielite',
	'Raiva Humana',
	'Sífilis Adquirida',
	'Sífilis Congênita',
	'Sífilis em Gestante',
	'Tétano Acidental',
	'Tétano Neonatal',
	'Tuberculose',
	'Violência Domestica',
	'Zika']
	
	
Years Available with disease ('disease name')

	SINAN.get_available_years('Hanseniase')
	
	Out[]: 
	['2001',
 	'2002',
 	'2003',
	'2004',
 	'2005',
	'2006',
 	'2007',
 	'2008',
 	'2009',
 	'2010',
	'2011',
	'2012',
	'2013',
 	'2014',
 	'2015',
 	'2016',
 	'2017',
 	'2018',
 	'2019',
 	'2020',
 	'2021',
 	'2022',
 	'2023']
	
	
Pulling Data from Parquet File ('file', year, month)
	
	TO = download('Hanseniase', 2022, 3)
	TO = download('to', 2022, 3)
	dfTO = parquets_to_dataframe(TO)
	dfTO.head()
	
		PA_CODUNI	PA_GESTAO	PA_CONDIC	PA_UFMUN	PA_REGCT	PA_INCOUT	PA_INCURG	PA_TPUPS	PA_TIPPRE	PA_MN_IND	...	PA_CODOCO	PA_FLQT	PA_FLER	PA_ETNIA	PA_VL_CF	PA_VL_CL	PA_VL_INC	PA_SRV_C	PA_INE	PA_NAT_JUR
	0	2829606	172100	PG	172100	0000	0000	0000	73	00	M	...	1	K	0		0.00	0.00	0.00			1244
	1	2829606	172100	PG	172100	0000	0000	0000	73	00	M	...	1	K	0		0.00	0.00	0.00			1244
	2	7015267	172100	PG	172100	0000	0000	0000	05	00	I	...	1	K	0		0.00	0.00	0.00	131001		2062
	3	7521901	172100	PG	172100	0000	0000	0000	39	00	I	...	1	K	0		0.00	0.00	0.00	145003		2305
	4	7759290	172100	PG	172100	0000	0000	0000	36	00	M	...	1	K	0		0.00	0.00	0.00			1244
	
Converting Parquet File to CSV

	dfTO.to_csv('SIH_TO_3_2022.csv')


Credit to :

	@software{flavio_codeco_coelho_2021_4883502,
	  author       = {Flávio Codeço Coelho and
                  Bernardo Chrispim Baron and
                  Gabriel Machado de Castro Fonseca and
                  Pedro Reck and
                  Daniela Palumbo},
	  title        = {AlertaDengue/PySUS: Vaccine},
 	 month        = may,
 	 year         = 2021,
 	 publisher    = {Zenodo},
 	 version      = {0.5.17},
	  doi          = {10.5281/zenodo.4883502},
	  url          = {https://doi.org/10.5281/zenodo.4883502}
	}
