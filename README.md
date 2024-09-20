The R markdown file is the script for the analysis of tissue infiltrating immune cells in 17,265 breast tumours from 22 studies participating in the B-CAST project.

The data are available on the European genome Phenome Archive at https://ega

There are two linked data sets

**case_data.csv** is the clinical data set for 17,265 cases with a single row per case

site0		-		site variable used in ER neg analysis           
site1		-		site variable used in ER pos analysis          
study		-		study          
bcac_id  -  	unique identifier in BCAC database          
morphology	-tumour morphology          
age_diag	-	age at diagnosis          
enter			-	time from diagnosis to study entry          
fu_15		-		follow-up in years censored at 15                    
br_15		-		breast cancer death censored at 15 years          
grade		-		tumour grade          
size		-		tumour size (mm)          
nodes		-		number positive regional nodes          
er			-	  estrogen receptor status          
pr			-	  progesterone receptor status          
her2		-		her2 status          
er_ast		-	estrogen receptor automated score using astrogrid (see a)          
er_ari		-	estrogen receptor score using ariol


**tiic_scores.csv** is the automate scores for each tissues micro-array core across 4 markers.  There is one row per marker and core (n = 128,308).
This table has a many:1 relationship with the case data as there are multiple markers and some cases include more than 1 tumour core in TMAs

study	-			          study acronym          
bcac_id	-		          unique identifier in BCAC database          
core_id	-		          unique tissue micro-array core identifier          
core_size	-		        TMA core size          
marker	-		          IHC marker          
area_all_mn	-		      total tissue area from mininet algorithm          
area_stroma_mn	-	    total stromal tissue area from mininet algorithm          
area_tumour_mn 	-	    total tumour tissue area from mininet algorithm          
area_artefact_mn	-	  area of artefact from mininet algorithm        
area_all_til_halo	-  percentage of all tissue occupied by TIICs from halo algorithm        
area_stroma_til_halo -	percentage of stroma occupied by TIICs from halo algorithm        
area_tumour_til_halo	-percentage of tumour occupied by TIICs from halo algorithm


The third data set is derived from the two primary data sets

**imputed_data.csv** includes the merged non-imputed data and ten imputed data sets at each of six minimum area (mm2) thresholds for exclusion of core level data. 
Each data set at each threshold comprises one row per case with TIIC scores based on the mean value for multiple cores.
Thus the total number of rows is 1,139,490 - 17,265 cases x 11 imputed data sets x 6 thresholds.

.imp	-    	       imputation number (0 is non-imputed data)        
.id			-	         patient identified        
site0	-			       site variable used in ER neg analysis         
site1		-		       site variable used in ER pos analysis        
study		-		       study        
morphology	-		   tumour morphology        
age_diag	-		     age at diagnosis        
enter		-		       time from diagnosis to study entry        
fu_15		-		       follow-up in years censored at 15         
br_15		-		        breast cancer death censored at 15 years        
grade		-		        tumour grade        
size	-			        tumour size (mm)        
nodes		-		        number positive regional nodes        
er		-		          estrogen receptor status        
pr		-		          progesterone receptor status        
her2	-			        her2 status        
er_ast	-			      estrogen receptor automated score using astrogrid (see a)        
er_ari	-			      estrogen receptor score using ariol        
age1	derived  -     variable: age at diagnosis as fractional polynomial function (see b)        
age2	derived  -     variable: age at diagnosis as fractional polynomial function (see b)        
cores_CD163		-      number cores for patient with CD163 scores        
cores_CD20		-	    number cores for patient with CD20 scores        
cores_CD8			-      number cores for patient with CD8 scores        
cores_FOXP3		-      number cores for patient with FOXP3 scores        
std_all_CD8		-	    (see c)        
std_tumour_CD8	-	  (c)        
std_all_CD20		-    (c)        
std_stroma_CD20	-  (c)        
std_tumour_CD20		-  (c)        
std_all_CD163		-    (c)        
std_stroma_CD163	-	(c)        
std_tumour_CD163	-	(c)        
std_all_FOXP3		-    (c)        
std_stroma_FOXP3	-	(c)        
std_tumour_FOXP3	-	(c)        
threshold		-	      minimum area (mm2) threshold for inclusion or core data

(a) 	see description of how these derived in  Ali HR, et al   Astronomical algorithms for automated analysis of tissue protein expression in breast cancer.  Br. J. Cancer  108, 602-12, 2013.  PMID 23329232        
Howat WJ et al.  Performance of automated scoring of ER, PR, HER2, CK5/6 and EGFR in breast cancer tissue microarrays in the Breast Cancer Association Consortium.  J Pathol Clin Res  1, 18-32, 2015.  PMID 27499890

(b) 	calculated as described in manuscript methods

(c) 	mean standardised log percentage area TIIC all/stroma/tumour and CD163, CD20, CD8, FOXP3
