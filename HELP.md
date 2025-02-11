### Detailed Configuration
Here is the description of the advanced parameters of DMetFinder.
You can adjust the parameters according to your needs. The following is a list of parameters:

#### Compound SMILES

* Drug molecule structure, like Cc1ccc(cc1)C(=O)O.

#### Compound ID

* The name of the test molecule.

#### Upload MS Files

* The list of the names of the MS data files.

#### Standard Sample File

* MS data of the standard compound. This is used to confirm parent's MS2 spectrum and retention time. This file is not necessary. If you do not have it, DMetFinder will use the first MS data file as the standard sample to find parent.

#### MS Files for Background Correction

* MS data of the blank. This is used to filter out the noise and background peaks but is not necessary. If you set a file path here, DMetFinder will make a background correction before scoring. You can set just one file here and it will be used in all samples. Or set a list of file paths with teh same number as the sample MS data files.

#### Parent Spectrum Searching Module

* **Ionization Type.** Mass spectrometry ionization type. Only + and - supported.
* **Parent Ion Charge.** The charge of the parent compound. The default value is 0 and will automatically select the single/double charged ion with strongest signal. If you do not want to search double-charged parent ion, set it to 1.
* **Parent Neutral Loss.** The neutral fragment loss of the parent compound.
* **Acquisition Delay.** Alignment parameter for MS1 retention time and MS2 scan time. The default value is 0.0, because DMetFinder will automatically calculate the acquisition delay based on standard sample data.

#### MS2 Screening Module

* **PPM range.** The maximum tolerance of the relative error(PPM) of *m/z*.
* **Signal Base.** The basic intensity to distinguish the noise peaks.
* **Signal Limit.** The minimum intensity of the metabolite.
* **Similarity Limit.** The minimum tolerance of MS2 similarity with the parent.

#### Retention Time Range Parameters

* **Retention Time.** The retention time range for which metabolite detection is required.
* **Scan Time Range.** Parameters used to determine spectrum peaks. Do not write a large value, or the different metabolites might converge into a single peak.

#### Fragments Annotation Module

* **Only Use Predicted Spectrum.** If true, DMetFinder will only use CFM-ID to predict parent's MS2 spectrum. Otherwise, DMetFinder will firstly try to find its spectrum in standard sample data.
* **Skip Fragments Prediction.** If true, DMetFinder will not use CFM-ID to predict fragments and annotate them.
* **Manual Annotation.** If true, DMetFinder will pop up a window allowing the user to manually annotate fragments that cannot be confirmed by CFM-ID.

#### Formula Prediction Module

* **Not Use MIST-CF.** If true, DMetFinder will not use MIST-CF to annotate formulas for the precursors.
* **Disable Formula Prediction.** If true, DMetFinder will calculate the molecular formula for unknown metabolites which cannot be matched with metabolic transformation library.
* **Formula Range.** The range of molecular formula prediction for unknown metabolites. The formulacalc module has an algorithm to generate a formula range. Therefore, this is not necessary and the default value is "". If you want to specify the range, please write it in the form like "C0-12H8-16O0-2Cl0-1".

#### MDF Module

* **Try MDF Analyse.** DMetFinder will try to use MDF algorithm to confirm metabolite formulas matched with metabolic transformation library.
* **Metabolism Pathway Combine.** Only 1 and 2 available. If set to 1, the program will only read the metabolism paths included in lib file and fragments annotated in previous module. And if set to 2, it will calculate the combination of different metabolism paths.
* **As Main Scoring Weight.** Beta Option. Different weight scoring for DIA data.

#### Scoring Module

* **mDa Range.** The maximum tolerance of the absolute error of *m/z*.
* **Peak Width.** The width(min) of the peak.
* **Not Merge Close Peaks.** If true, the program will not merge the peaks with both similar *m/z* value and close retention time.
* **Minimum Score.** The minimum score of the metabolite. All the metabolites with scores lower than this value will be filtered out.

#### Structure Prediction Module

* **Not Use BioTransformer.** Disable biotransformer prediction.

#### Debug

* Used to edit output folder name. For example, if you set this to "-a", the output folder will be named as "20xx-xx-xx-<name>-analyse-a". This is useful when you want to compare the results of different parameters. All the output result folders are stored in **_internal/DMetFinder/output** folder.