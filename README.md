![CTSgetR](https://github.com/dgrapov/CTSgetR/blob/master/etc/ctsgetR_logo.png?raw=true)

R interface to the [Chemical Translation Service (CTS)] (http://cts.fiehnlab.ucdavis.edu/)

### Installation
```R
library(devtools) # install.packages("devtools") if missing
install_github(repo = "CTSgetR", username = "dgrapov")
library(CTSgetR)
```

### How to use the interface
```r
help(CTSgetR)
```

### Example usage
```r
#translate from chemical name to InchiKey
id<-"alanine"
from<-"Chemical Name"
to<-"InChIKey"
CTSgetR(id,from,to,progress=FALSE)

#translate from "InChIKey" to multiple identifiers
id<-c("DMULVCHRPCFFGV-UHFFFAOYSA-N","ZPUCINDJVBIVPJ-LJISPDSOSA-N","ZAGRKAFMISFKIO-QMTHXVAHSA-N")
from<-"InChIKey"
to<- c("Chemical Name", "PubChem CID", "KEGG","Human Metabolome Database")
multi.CTSgetR(id,from,to,progress=FALSE)

#return all possible results for the translation between "PubChem CID" and "Chemical Name"
id<-c("446220")
from<-"PubChem CID"
to<- c("Chemical Name")
CTSgetR(id,from,to,progress=FALSE,limit.values=FALSE)
```


### Check out some more [translation examples](https://github.com/dgrapov/CTSgetR/wiki/Chemical-Translation-System-in-R).
