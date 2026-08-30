# Query references

Search for a specific reference using a keyword or a Digital Object
Identifier (DOI). If the `query` is a character string, then all
character columns in the table are searched and the entries for which at
least one partial match was found are returned. Alternatively, a named
list can be used to look for an exact match in a specific column (see
Details section).

## Usage

``` r
search_references(query, doi = NULL, ...)
```

## Arguments

- query:

  either a character string including a single keyword or a named list
  containing a custom query (see details section below). Note that if an
  empty character string is passed, then all available entries are
  returned.

- doi:

  `character` a Digital Object Identifier (DOI) of the article. Note
  that `query` is ignored if `doi` is specified.

- ...:

  Additional arguments passed to
  [`rmangal_request()`](https://docs.ropensci.org/rmangal/reference/rmangal_request.md),
  including the argument `cache` that allows requests caching.

## Value

An object of class `mgSearchReferences`, which is a list that includes a
wide range of details associated to the reference, including all
datasets and networks related to the publication that are included in
Mangal database.

## Details

Names of the list should match one of the column names within the table.
For the `reference` table, those are:

- `id`: unique identifier of the reference

- `first_author`: first author

- `doi`: use `doi` instead

- `jstor`: JSTOR identifier

- `year`: year of publication.

Note that for lists with more than one element, only the first element
is used, the others are ignored. An example is provided below.

## References

- <https://mangal.io/#/>

- <https://mangal-interactions.github.io/mangal-api/#references>

## Examples

``` r
# \donttest{
search_references(doi = "10.2307/3225248")
#> Found 1 reference.
#> $id
#> [1] 132
#> 
#> $doi
#> [1] "10.2307/3225248"
#> 
#> $first_author
#> [1] "koslucher"
#> 
#> $year
#> [1] "1973"
#> 
#> $jstor
#> [1] "https://www.jstor.org/stable/3225248"
#> 
#> $pmid
#> [1] NA
#> 
#> $bibtex
#> [1] "@article{Koslucher_1973, doi = {10.2307/3225248}, url = {https://doi.org/10.2307%2F3225248}, year = 1973, month = {jul}, publisher = {{JSTOR}}, volume = {92}, number = {3}, pages = {441}, author = {Dale G. Koslucher and G. Wayne Minshall}, title = {Food Habits of Some Benthic Invertebrates in a Northern Cool-Desert Stream (Deep Creek, Curlew Valley, Idaho-Utah)}, journal = {Transactions of the American Microscopical Society}}"
#> 
#> $paper_url
#> [1] "https://www.jstor.org/stable/pdf/3225248.pdf?refreqid=excelsior%3Ae2741b937f74579b7875d7ade8f58f47"
#> 
#> $data_url
#> [1] "https://globalwebdb.com/"
#> 
#> $created_at
#> [1] "2019-03-08T19:27:48.551Z"
#> 
#> $updated_at
#> [1] "2019-03-08T19:27:48.551Z"
#> 
#> $datasets
#>    id                    name
#> 1 133 koslucher_minshall_1973
#>                                                                                   description
#> 1 Food web strucutre of a noterhen cool-desert stream (Deep Creek), Curlew Valley, Idaho-Utah
#>   public               created_at               updated_at ref_id user_id
#> 1   TRUE 2019-03-08T19:27:50.152Z 2019-03-08T19:27:50.152Z    132       4
#> 
#> $networks
#> $networks[[1]]
#>     id                    name                     date
#> 1 1517 koslucher_minshall_1973 1969-11-01T00:00:00.000Z
#>                                                                                   description
#> 1 Food web strucutre of a noterhen cool-desert stream (Deep Creek), Curlew Valley, Idaho-Utah
#>   public all_interactions               created_at               updated_at
#> 1   TRUE            FALSE 2019-03-08T19:27:51.061Z 2019-03-08T19:27:51.061Z
#>   dataset_id user_id geom_type geom_lon geom_lat
#> 1        133       4      <NA>       NA       NA
#> 
#> 
#> attr(,"row.names")
#> [1] 1
#> attr(,"class")
#> [1] "mgSearchReferences"
search_references(list(jstor = 3683041))
#> Found 1 reference.
#> $id
#> [1] 9
#> 
#> $doi
#> [1] "10.2307/3683041"
#> 
#> $first_author
#> [1] "elberling"
#> 
#> $year
#> [1] "1999"
#> 
#> $jstor
#> [1] "3683041"
#> 
#> $pmid
#> [1] NA
#> 
#> $bibtex
#> [1] "@article{10.2307/3683041, ISSN = {09067590, 16000587}, URL = {http://www.jstor.org/stable/3683041}, author = {Heidi Elberling and Jens M. Olesen}, journal = {Ecography}, number = {3}, pages = {314-323}, publisher = {[Nordic Society Oikos, Wiley]}, title = {The Structure of a High Latitude Plant-Flower Visitor System: The Dominance of Flies}, volume = {22}, year = {1999}}"
#> 
#> $paper_url
#> [1] "https://www.jstor.org/stable/3683041?seq=1#page_scan_tab_contents"
#> 
#> $data_url
#> [1] "https://www.nceas.ucsb.edu/interactionweb/data/plant_pollinator/excel/elberling&olesen_1999.xls"
#> 
#> $created_at
#> [1] "2019-02-22T20:09:13.872Z"
#> 
#> $updated_at
#> [1] "2019-02-22T20:09:13.872Z"
#> 
#> $datasets
#>   id                  name
#> 1  9 elberling_olesen_1999
#>                                                   description public
#> 1 Flower-visiting insect at Mt. Latnjatjarro, northern Sweden   TRUE
#>                 created_at               updated_at ref_id user_id
#> 1 2019-02-22T20:09:17.994Z 2019-02-22T20:09:17.994Z      9       2
#> 
#> $networks
#> $networks[[1]]
#>    id                               name                     date
#> 1 909 elberling_olesen_1999_19940823_909 1994-08-23T00:00:00.000Z
#>                                                   description public
#> 1 Flower-visiting insect at Mt. Latnjatjarro, northern Sweden   TRUE
#>   all_interactions               created_at               updated_at dataset_id
#> 1            FALSE 2019-02-24T22:21:32.444Z 2019-02-24T22:21:32.444Z          9
#>   user_id geom_type geom_lon geom_lat
#> 1       2     Point     18.5    68.35
#> 
#> 
#> attr(,"row.names")
#> [1] 1
#> attr(,"class")
#> [1] "mgSearchReferences"
search_references(list(year = 2010))
#> Found 5 references.
#> $id
#> [1]  74  76 111  85 164
#> 
#> $doi
#> [1] "10.1007/s10641-010-9606-0"        "10.3989/scimar.2011.75n2309"     
#> [3] "10.1071/mf09202"                  NA                                
#> [5] "10.1111/j.1461-0248.2009.01437.x"
#> 
#> $first_author
#> [1] "ricciardi"        "ronaldo angelini" "rayner"           "angelini"        
#> [5] "kaiser-bunbury"  
#> 
#> $year
#> [1] "2010" "2010" "2010" "2010" "2010"
#> 
#> $jstor
#> [1] NA NA NA NA NA
#> 
#> $pmid
#> [1] NA NA NA NA NA
#> 
#> $bibtex
#> [1] "@article{Ricciardi_2010,doi = {10.1007/s10641-010-9606-0},url = {https://doi.org/10.1007%2Fs10641-010-9606-0},year = 2010,month = {feb},publisher = {Springer Nature},volume = {87},number = {4},pages = {333--347},author = {Francesco Ricciardi and Massimo Boyer and Jeff Ollerton},title = {Assemblage and interaction structure of the anemonefish-anemone mutualism across the Manado region of Sulawesi, Indonesia},journal = {Environmental Biology of Fishes}}"                                                                          
#> [2] "@article{Angelini_2010, doi = {10.3989/scimar.2011.75n2309}, url = {https://doi.org/10.3989%2Fscimar.2011.75n2309}, year = 2010, month = {nov}, publisher = {Departmento de Publicaciones del {CSIC}}, volume = {75}, number = {2}, pages = {309--319}, author = {Ronaldo Angelini and Filomena Vaz-Velho}, title = {Ecosystem structure and trophic analysis of Angolan fishery landings}, journal = {Scientia Marina}}"                                                                                                                         
#> [3] "@article{Rayner_2010, doi = {10.1071/mf09202}, url = {https://doi.org/10.1071%2Fmf09202}, year = 2010, publisher = {{CSIRO} Publishing}, volume = {61}, number = {8}, pages = {909}, author = {Thomas S. Rayner and Bradley J. Pusey and Richard G. Pearson and Paul C. Godfrey}, title = {Food web dynamics in an Australian Wet Tropics river}, journal = {Marine and Freshwater Research}}"                                                                                                                                                    
#> [4] "@article{angelini2010mixed, title={Mixed food web control and stability in a Cerrado river (Brazil)}, author={Angelini, RONALDO and Aloisio, GUSTAVO RIBEIRO and Carvalho, ADRIANA ROSA}, journal={Pan-American Journal of Aquatic Sciences}, volume={5}, number={3}, pages={421--431}, year={2010}}"                                                                                                                                                                                                                                             
#> [5] "@article{Kaiser_Bunbury_2010, doi = {10.1111/j.1461-0248.2009.01437.x}, url = {https://doi.org/10.1111%2Fj.1461-0248.2009.01437.x}, year = 2010, month = {apr}, publisher = {Wiley}, volume = {13}, number = {4}, pages = {442--452}, author = {Christopher N. Kaiser-Bunbury and Stefanie Muff and Jane Memmott and Christine B. Müller and Amedeo Caflisch}, title = {The robustness of pollination networks to the loss of species and interactions: a quantitative approach incorporating pollinator behaviour}, journal = {Ecology Letters}}"
#> 
#> $paper_url
#> [1] "https://link.springer.com/article/10.1007%2Fs10641-010-9606-0"            
#> [2] "https://doi.org/10.3989%2Fscimar.2011.75n2309"                            
#> [3] "http://www.publish.csiro.au/mf/MF09202"                                   
#> [4] "https://panamjas.org/pdf_artigos/PANAMJAS_5(3)_421-431.pdf"               
#> [5] "https://onlinelibrary.wiley.com/doi/full/10.1111/j.1461-0248.2009.01437.x"
#> 
#> $data_url
#> [1] "https://www.nceas.ucsb.edu/interactionweb/data/anemone_fish/ricciardi-et-al-2010.xls"
#> [2] "https://globalwebdb.com/"                                                            
#> [3] "https://globalwebdb.com/"                                                            
#> [4] "https://globalwebdb.com/"                                                            
#> [5] "http://www.web-of-life.es/2.0/map.php"                                               
#> 
#> $created_at
#> [1] "2019-02-26T20:11:58.429Z" "2019-02-26T21:18:52.787Z"
#> [3] "2019-03-06T14:49:40.733Z" "2019-02-28T17:26:42.053Z"
#> [5] "2019-03-21T19:21:35.795Z"
#> 
#> $updated_at
#> [1] "2019-02-26T20:11:58.429Z" "2019-02-26T21:18:52.787Z"
#> [3] "2019-03-06T14:49:40.733Z" "2019-02-28T17:26:42.053Z"
#> [5] "2019-03-21T19:21:35.795Z"
#> 
#> $datasets
#>    id                      name
#> 1  75            ricciardi_2010
#> 2  77             angelini_2010
#> 3 112         rayner_et_al_2010
#> 4  86       angelini_et_al_2010
#> 5 167 kaiser-bunbury_et_al_2010
#>                                                                                       description
#> 1 structure of local anemonefish-anemone networks across the Manado region of Sulawesi, Indonesia
#> 2                                                        Food web of the Angolan fishery landings
#> 3                            Food web structure of a wet Tropic river (Mulgrave River), Australia
#> 4         Interaction of a mixed food web in the Corrente River in the Paraná River Basin, Brazil
#> 5             Plant-pollinator system at two sites in Black River Gorges National Park, Mauritius
#>   public               created_at               updated_at ref_id user_id
#> 1   TRUE 2019-02-26T20:12:00.676Z 2019-02-26T20:12:00.676Z     74       2
#> 2   TRUE 2019-02-26T21:18:55.909Z 2019-02-26T21:18:55.909Z     76       3
#> 3   TRUE 2019-03-06T14:49:42.906Z 2019-03-06T14:49:42.906Z    111       4
#> 4   TRUE 2019-02-28T17:26:45.617Z 2019-02-28T17:26:45.617Z     85       4
#> 5   TRUE 2019-03-21T19:21:38.571Z 2019-03-21T19:21:38.571Z    164       4
#> 
#> $networks
#> $networks[[1]]
#>     id                         name                     date
#> 1 1071 ricciardi_2010_20060701_1071 2006-07-01T00:00:00.000Z
#>                                                                                              description
#> 1 structure of local anemonefish-anemone networks across the Manado region of Sulawesi, Indonesia,  Bajo
#>   public all_interactions               created_at               updated_at
#> 1   TRUE            FALSE 2019-02-26T20:12:57.710Z 2019-02-26T20:12:57.710Z
#>   dataset_id user_id geom_type geom_lon geom_lat
#> 1         75       2     Point  124.778    1.787
#> 
#> $networks[[2]]
#>     id                        name                     date
#> 1 1101 angelini_2010_20100601_1101 2010-06-01T00:00:00.000Z
#>                                description public all_interactions
#> 1 Food web of the Angolan fishery landings   TRUE            FALSE
#>                 created_at               updated_at dataset_id user_id
#> 1 2019-02-26T21:19:01.124Z 2019-02-26T21:19:01.124Z         77       3
#>   geom_type
#> 1   Polygon
#>                                                                                   geom_lon
#> 1 10.95337, 11.62354, 11.64551, 12.12891, 13.60107, 11.95312, 10.70068, 10.95337, 10.95337
#>                                                                                          geom_lat
#> 1 -17.25000, -17.25000, -15.53838, -13.96605, -11.13529, -5.00000, -5.00000, -17.25000, -17.25000
#> 
#> $networks[[3]]
#>     id                            name                     date
#> 1 1488 rayner_et_al_2010_20040401_1488 2004-04-01T00:00:00.000Z
#>                                                            description public
#> 1 Food web structure of a wet Tropic river (Mulgrave River), Australia   TRUE
#>   all_interactions               created_at               updated_at dataset_id
#> 1            FALSE 2019-03-06T14:49:45.109Z 2019-03-06T14:49:45.109Z        112
#>   user_id geom_type geom_lon  geom_lat
#> 1       4     Point 145.8646 -17.12026
#> 
#> $networks[[4]]
#>     id                              name                     date
#> 1 1448 angelini_et_al_2010_20030501_1448 2003-05-01T00:00:00.000Z
#>                                                                       description
#> 1 Interaction of a mixed food web in the Corrente River in the Paraná River Basin
#>   public all_interactions               created_at               updated_at
#> 1   TRUE            FALSE 2019-02-28T17:26:47.593Z 2019-02-28T17:26:47.593Z
#>   dataset_id user_id geom_type geom_lon  geom_lat
#> 1         86       4     Point -52.0155 -18.56476
#> 
#> $networks[[5]]
#>     id                        name                     date
#> 1 1599 kaiser-bunbury_et_al_2010_1 2003-09-01T00:00:00.000Z
#>                                                                           description
#> 1 Plant-pollinator system at two sites in Black River Gorges National Park, Mauritius
#>   public all_interactions               created_at               updated_at
#> 1   TRUE            FALSE 2019-03-21T19:23:49.316Z 2019-03-21T19:23:49.316Z
#>   dataset_id user_id geom_type geom_lon  geom_lat
#> 1        167       4     Point 57.45094 -20.42637
#> 
#> 
#> attr(,"row.names")
#> [1] 1 2 3 4 5
#> attr(,"class")
#> [1] "mgSearchReferences"
# }
```
