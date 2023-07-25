# Analises para Saude e Medicina

Com o passar do tempo o grupo responsável pelos dados pode mudar a localização, o formato e muito mais do arquivo.

Para você rodar na sua máquina com uma versão mais recente dos dados você pode utilizar o link atual do arquivo:

https://github.com/CSSEGISandData/COVID-19/blob/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv

E clicar no "RAW", que dará a URI https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_confirmed_global.csv

Além disso, na versão mais recente dos dados a informação estranha "Mainland China" foi alterada para "China".

Idem para o arquivo "RAW" de casos de mortos e recuperados, que serão, no futuro:
```
deaths = pd.read_csv("https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_deaths_global.csv")
recovered = pd.read_csv("https://raw.githubusercontent.com/CSSEGISandData/COVID-19/master/csse_covid_19_data/csse_covid_19_time_series/time_series_covid19_recovered_global.csv")
```
