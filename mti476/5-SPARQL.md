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

https://w.wiki/Kz5

