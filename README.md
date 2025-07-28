The R markdown file is the script for the analysis of tissue infiltrating immune cells in 12,285 breast tumours from 22 studies participating in the B-CAST project.

There are two linked data sets

**case_data.csv** is the clinical data set for 12,285 cases with a single row per case

study -        study acromym     
bcac_id	-		   unique identifier in BCAC database.    
site -         variable use to adjust by study where studies with few events are pooled    
yod -          year of diagnosis.    
morphology -   tumour morhology     
age_diag -     age at diagnosis     
status -       vital status at last follow up     
years_status - years to last follow up     
enter -        time (years) between diagnsosis and recruitment     
grade -        tumour grade     
size -         tumour size                
nodes -        number positive lymph nodes     
er -           estrogen receptor status     
pr -           progesterone receptor status     
her2 -         HER2 status     
br_death -     death from breast cancer     
er_ast -       automated score for estrogen receptor using astrogrid (a)     
er_ari -       automated score for estrogen receptor using Ariol (b)     
fu_15 -        follow-up time censored at 15 years     
br_15 -        breast cancer specific death at 15 years with unknown coded as breast cancer death     
bcss_15 -      breast cancer specific death at 15 years with unknown censored
core_size -    size of tissue cores in tissue micro-arrays
horm -         indicator variable for adjuvant hormone therapy     
tras -         indicator variable for adjuvant trastuzumab     
radio -        indicator variable for radiotherapy     
chemo -        indicator variable for adjuvant chemotherapy

(a)	see description of how these derived in  Ali HR, et al   Astronomical algorithms for automated analysis of tissue protein expression in breast cancer.  Br. J. Cancer  108, 602-12, 2013.  PMID 23329232        
(b) see Howat WJ et al.  Performance of automated scoring of ER, PR, HER2, CK5/6 and EGFR in breast cancer tissue microarrays in the Breast Cancer Association Consortium.  J Pathol Clin Res  1, 18-32, 2015.  PMID 27499890

**tiic_scores.csv** is the automate scores for each tissues micro-array core across 4 markers.  There is one row per marker and core (n = 99,051).
This table has a many-to-one relationship with the case data as there are multiple markers and some cases include more than 1 tumour core in TMAs

study	-			            study acronym          
bcac_id	-		            unique identifier in BCAC database          
core_id	-		            unique tissue micro-array core identifier          
core_size	-		          TMA core size          
marker	-		            IHC marker          
area_all_mn	-		        total tissue area from mininet algorithm          
area_stroma_mn	-	      total stromal tissue area from mininet algorithm          
area_tumour_mn 	-	      total tumour tissue area from mininet algorithm          
area_artefact_mn	-	    area of artefact from mininet algorithm        
area_all_til_halo	-     percentage of all tissue occupied by TIICs from halo algorithm        
area_stroma_til_halo -	percentage of stroma occupied by TIICs from halo algorithm        
area_tumour_til_halo	- percentage of tumour occupied by TIICs from halo algorithm
