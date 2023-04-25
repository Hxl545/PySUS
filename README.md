# PySUS

Utilizing Google Collaboration

Installation of PYSUS

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
	
	
Pulling Data from Parquet File
	
	TO = download('to', 2022, 3)
	dfTO = parquets_to_dataframe(TO)
	dfTO.head()
	
Converting Parquet File to CSV

	dfTO.to_csv('SIH_TO_3_2022.csv')
