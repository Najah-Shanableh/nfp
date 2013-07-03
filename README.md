# Nurse Family Partnership Impact Evaluation
 
## Introduction
 
As part of the Data Science for Social Good Fellowship (http://dssg.io), we are evaluating the effectiveness of the Nurse-Family Partnership (NFP), a home-visitation program that pairs a nurse with an at-risk first-time mother for the duration of her pregnancy and the first two years of her child's life.  Numerous studies have documented NFP's positive benefits for the mothers, children, and society, including three randomized controlled trials (RCT) (http://www.nursefamilypartnership.org/proven-results/published-research).  However, most of those studies focus on a single state or locality, and NFP has been scaled to a national effort operating in diverse communities.  The cost of conducting an RCT at the national level may be prohibitive.

DSSG is comparing administrative data from NFP to several public national datasets.  Our goal is to identify women who are similar on all 
observable characteristics (such as demographics) in the two datasets and compare their outcomes.  (Although we cannot know whether the women in our comparison group participated in NFP, assuming that they are non-participants biases our results toward zero, making it less likely that we find impact.)

Our project has three goals:

1) To provide a rough evaluation of NFP's impact at a national level (although this will not be a rigorous program evaluation, it will provide
an educated estimate of NFP's effectiveness).

2) To develop a methodology for basic impact evaluation of nonprofit programs where resource limitations and program size make traditional experimental evaluations impractical or impossible.

3) To explore correlations in NFP's data between outcomes and other characteristics of the mothers, with the goal of helping NFP identify high-risk situations and techniques that seem to reduce those risks.  This knowledge will inform NFP's ongoing quality improvement processes.


## Methodology

Our intention is to conduct an impact evaluation using propensity score matching (PSM) (e.g. http://faculty.smu.edu/Millimet/classes/eco7377/papers/rosenbaum%20rubin%2083a.pdf).  PSM is a form of matching where cases are paired by their estimated probability of selection into treatment.  For example, income, age, and educational background plausibly affect whether a pregnant woman enrolls in NFP.  If we estimated the probability that each woman enrolls in NFP based on these characteristics (using, say, probit regression), then we could match an NFP enrollee with a 70% chance of enrolling with a non-enrollee with a 70% chance of enrolling.  Assuming we account for all the relevant factors that determine NFP enrollment, then the differences we observe between women in the program and women not in the program will on average be a good estimate of the program's effectiveness.  An initial overview of the matching process in R is available in the script PSM_Script.R.

NFP intends to evaluate outcomes at birth; in child health and development; in mother's life course development; and in intimate partner violence, child abuse, and neglect.  They have asked that we particularly consider child development and mother's life course outcomes.  These outcomes include the following:

Child Development and Health:
- Immunization rates
- Breastfeeding rates
- Language, cognitive, behavioral, and emotional development (as measured by the Ages and Stages Questionnaire)
- Physical growth, including height and weight

Mother's Life Course:
- Educational attainment
- Employment
- Governmental and community assistance
- Pregnancy interval
- Smoking/substance abuse

## Comparison Data Sets

We have identified the following comparison datasets:

1. Current Population Survey (CPS)

2. National Survey of Children's Health (NSCH): The NSCH is conducted by the National Center for Health Statistics at the Centers for Disease Control.  It includes information on breastfeeding and child weight (though height is not available for children under age 10).  It also includes a variety of demographic data points that can be used to match individuals in the survey to comparable individuals in NFP's data set.  To read more about the NSCH and request a copy of the data, visit www.childhealthdata.org.  More detail about which variables we are using from the NSCH and how we are recoding them is available in the cleaning script, NSCH_Prep.R.

3. National Immunization Survey (NIS): The NIS is conducted jointly by the National Center for Immunizations and Respiratory Diseases and the National Center for Health Statistics.  It includes provider-reported immunizations for several vaccines and thousands of people each year.  It also includes demographic and socioeconomic variables that we can use to match with individuals in the NFP dataset.  To read more about the NIS and to download a copy of the data, visit www.cdc.gov/nchs/nis.htm.  More detail about which variables we are using from NIS and how we are recoding them is available in the cleaning script, NIS_Prep.R.

