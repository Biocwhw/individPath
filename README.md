# individPath

We here present an approach, called individPath, to detect pathways with significantly disrupted intrapathway relative expression orderings (REOs) for each disease sample compared with the stable, normal intra-pathway REOs pre-determined in previously accumulated normal samples. Please see "Individualized identification of disease-associated pathways with disrupted coordination of gene expression.(Brief Bioinform. 2016 Jan;17(1):78-87. doi: 10.1093/bib/bbv030.)"


R topics documented:

1 function-individPath(tumorFile, refFile, PathwayFile, cutoff)

Arguments:

tumorFile--a numeric matrix(or table) with raw representing genes and column representing samples.

refFile--a numeric matrix(or table) with raw representing genes and column representing samples.

PathwayFile--the name of the pathway file which each row of the table denotes a pathway.

cutoff--selection criteria for stable intra-pathway gene pairs. The default setting is 0.99.

Details:

The significantly disrupted pathways can be determined by testing whether the frequency of reversal gene pairs observed within each pathway is significantly more than what expected by chance using the hypergeometric distribution model.

Value:

Two text files correspond to "individPath_BH_result" and "individPath_pvalue_result", respectively.

2 function-individPathCal(CaseData, StableGP, ReversalGP, NumStable, PathGP)

Description:

This function is used to determine whether each pathway is significantly dysregulated in individual patients.

Arguments:

CaseData--a numeric matrix with one column.

StableGP--all stable intra-pathway gene pairs.

ReversalGP--the number of reversal gene pairs for each pathway in individual patients.

NumStable--the number of all stable intra-pathway gene pairs.

PathGP--the number of stable intra-pathway gene pairs in each pathway.

Value:

A numeric matrix containing the p-value and adjusted-pvalue of each pathway dysregulated in individual patients.

3 function-SRGgenePair(ControlData, CaseData, PathData, cutoff)

Description:

This function is used to identify stable and reversal intra-pathway gene pairs.

Arguments:

ControlData--a numeric matrix(or table) with raw representing genes and column representing samples.

CaseData--a numeric matrix(or table) with raw representing genes and column representing samples.

PathData--the name of the pathway file which each row of the table denotes a pathway.

cutoff--the selection criteria for stable intra-pathway gene pairs. The default setting is 0.99.

Value:

A list with class "SRGgenePair.result" containing the following components:

(1) ReversalStat the number of reversal gene pairs for each pathway in individual patients.

(2) BG.GenePairs all stable intra-pathway gene pairs in normal samples.

(3) PathGP the number of stable intra-pathway gene pairs in each pathway.
