Basado en https://github.com/egonw/SARS-CoV-2-Queries

Cantidad de Contagiados en Chile:

```sparql
SELECT ?date ?numberOfCases WHERE {
  wd:Q87191204 p:P1603 ?numberOfCasesStat .
  ?numberOfCasesStat ps:P1603 ?numberOfCases ;
                      pq:P585 ?date .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],es". }
} ORDER BY ASC(?date)
```

Cantidad de fallecidos en Chile:

```sparql
SELECT ?date ?numberOfDeath WHERE {
  wd:Q87191204 p:P1120 ?numberOfDeathStat .
  ?numberOfDeathStat ps:P1120 ?numberOfDeath ;
                      pq:P585 ?date .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],es". }
} ORDER BY ASC(?date)
```

Gráfico de Contagiados en Chile:

```sparql
#defaultView:LineChart
SELECT ?date ?numberOfCases WHERE {
  wd:Q87191204 p:P1603 ?numberOfCasesStat . 
  ?numberOfCasesStat ps:P1603 ?numberOfCases ;
                      pq:P585 ?date .
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],es". }
} ORDER BY ASC(?date)
```

Gráfico de Contagiados en Sudamérica

```sparql
#defaultView:LineChart
SELECT ?casesPointInTime ?cases ?countryLabel WHERE {
  ?item wdt:P31 wd:Q3241045;
    wdt:P17 ?country;
    p:P1603 ?casesStatement.
  ?casesStatement ps:P1603 ?cases.
  FILTER(?cases > 0 )
  ?casesStatement pq:P585 ?casesPointInTime.
  { ?item wdt:P361 wd:Q86694744. }

  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
}
```


https://w.wiki/Kz5

