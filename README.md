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
	
	
Years Available with disease

	SINAN.get_available_years('Hanseniase')
	
	
Pulling Data from Parquet File
	
	TO = download('to', 2022, 3)
	dfTO = parquets_to_dataframe(TO)
	dfTO.head()
	
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
