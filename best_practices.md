---
layout: page
title: Best Practices
permalink: /best_practices/
---


## Best Practice Guidelines

# Best Practice Overview

Best practices in reproducibility are a set of actions and principles that you can take in order to ensure that your work is reproducible. 
Best practices should not be considered a single, static recipe, but rather they are a flexible knowledge of processes and strategies that evolve over time.

# Companion Paper

The companion paper must provide means for the committee to download the artifacts that will enable replicating the findings that are in the original paper contribution. The author-created artifacts that are relevant to this paper must have been placed on a publicly accessible archival repository (e.g. GitHub).

The companion paper must describe the procedure allowing reviewers to easily find their way in the artifacts. That procedure might for example explain the reasons for having organized the artifacts in hierarchies of folders. It might specify what items inside the artifacts must be read, and in which order, what are the main elements to fully review. It might clearly establish relationships between items in the artifacts and the corresponding elements that can be found in the original scientific contribution. It might explain and justify why this or that part of the original paper is not reproducible. The paper should indicate the expected duration of running the whole experimental pipeline.

Ideally, the companion paper should include text/schemas/illustrations that describe what the artifacts contain and how they should be deployed and then used. The companion paper should also contain notes about parameters that can be set or adjusted and about how to recreate the plots. It has to have examples, with comments. You can of course create documents in the archive that provide additional text/schemas/illustrations. In this case, the companion paper should clearly indicate where that can be found in the artifacts.

### About Experiments
The central results and claims of the corresponding published paper should be supported by the submitted experiments, meaning we can recreate result data and graphs that demonstrate similar behavior to that shown in that paper. Typically when the results are about response times, we do not expect to get identical results. Instead, we expect to see that the overall behavior matches the conclusions from the paper, e.g., that a given algorithm is significantly faster than another one, or that a given parameter affects negatively or positively the behavior of a system.

Given a system, the authors should provide the complete set of experiments to reproduce the results that are in the original paper. Typically, each experiment will consist of the following parts.

- A setup phase where parameters are configured and data is loaded,
- A running phase where a workload is applied and measurements are taken,
- A clean-up phase where the system is prepared to avoid interference with the next round of experiments.

The authors should document (i) how to perform the setup, running and clean-up phases, and (ii) how to check that these phases are complete as they should. The authors should document the expected effect of the setup phase (e.g., a cold file cache is enforced) and the different steps of the running phase, e.g., by documenting the combination of command line options used to run a given experiment script.

Each experiment should be automatic, e.g., via a script that takes a range of values for each experiment parameter as arguments, rather than manual, e.g., via a script that must be edited so that a constant takes the value of a given experiment parameter.

We do not expect the authors to perform any additional experiments on top of the ones in their original paper. Any additional experiments submitted will be considered and tested but they are not required.

### About Graphs and Plots
For each graph/plot in the original paper, the authors should describe how the graph/plot is obtained from the experimental measurements. The submission should contain the scripts (or spreadsheets) that are used to generate the graphs/plots. We strongly encourage authors to provide scripts for all their graphs using a tool such as Gnuplot or Matplotlib. Here are two useful tutorials for Gnuplot: [a brief manual and tutorial](http://people.duke.edu/~hpgavin/gnuplot.html), [and a tutorial with details about creating eps figures and embed them using LaTeX](http://www.gnuplot.info/docs/tutorial.pdf) and another two for Matplotlib: [examples from SciPy](https://scipy-cookbook.readthedocs.io/items/idx_matplotlib.html), and a [step-by-step tutorial discussing many features](http://www.labri.fr/perso/nrougier/teaching/matplotlib/).

---
 

# Archive with Artifacts
Replicability is grounded in code, scripts, and datasets that you provide and that form so called “artifacts”. More formally, ACM defines artifacts as follows:

> By “artifact” we mean a digital object that was either created by the authors to be used as part of the study or generated by the experiment itself. For example, artifacts can be software systems, scripts used to run experiments, input datasets, raw data collected in the experiment, or scripts used to analyze results. <br /> &raquo; ACM DL. [Read it here](https://tinyurl.com/ycw6zd7j).

Artifacts contain digital objects that supplement the companion paper. Artifacts are typically a series of files, possibly organized according to a clear and easy-to-grasp hierarchy. Artifacts include for example:

1. The configuration files and scripts to set up and deploy the environment needed for the reviewers to subsequently run your code,
2. The source code if you expose your system as a white box,
3. Input Data: Either the process to generate the input data should be made available, or when the data is not generated, the actual data itself or a link to the data should be provided,
4. The set of experiments (system configuration and initialization, scripts, workload, measurement protocol, ...) used to run the experiments that produce the raw experimental data,
5. The scripts needed to transform the raw experimental data into the graphs, tables, plots, ..., that can be found in the original submission already published in the proceedings of ACM ICMR.
All this material should be extensively described, documented, commented, and easy to understand, for example in specific files coming together with what they describe.

**Note**: We strongly recommend exposing your system as a white box so that anyone can reproduce and reuse your results. If the system is only made accessible as a black box, however, reviewers may still require confidential access to source code, such that they can properly assess the validity of the reproducibility results.

{::options parse_block_html="true" /}
<div class="box">

### Ideal archive of artifacts
Authors are encouraged to strive for this ideal submission for truly replicable work…

At a minimum, the authors should provide a complete set of scripts to install the system, produce the data, run experiments and produce the resulting graphs along with detailed readme file(s) that describe the process step by step so it can be easily redone by a reviewer.

The ideal submission consists of an extremely careful and detailed description of the experiments, their parameters, and of a master script that:

1. installs all systems needed,
2. generates or fetches all needed input data,
3. reruns all experiments and generates all results,
4. generates all graphs, plots, and tables, and finally,
5. recompiles the sources of the paper

... to produce a brand new PDF for the paper with all the reproduced experiments. It’ll allow comparing the obtained material with the one in the original contribution that was accepted at ACM MM.

</div>

---
 

# Packaging Guidelines
These packaging guidelines are meant to cover general cases. Please keep in mind that every individual case is slightly different.

### Environment
Authors should explicitly specify the operating system and tools that should be installed as the environment. Such specification should include dependencies with specific hardware features (e.g., 25 GB of RAM are needed) or dependencies within the environment (e.g., the compiler that should be used must be run with a specific version of the operating system).

Note: The submitted artifacts should not require specific hardware and software that are hard to get access to. The committee will try to do the best to find reviewers who can setup the required environments; however, if no reviewer can be found, the companion paper cannot be accepted.

### System
System setup is one of the most challenging aspects when replicating experiments. System setup will be easier to conduct if it is automatic rather than manual. Authors should test that the system they distribute can actually be installed in a new environment. The documentation should detail every step in the system setup:

- How to obtain the system?
- How to configure the environment if need be (e.g., environment variables, paths)?
- How to compile the system? (existing compilation options should be mentioned)
- How to use the system? (What are the configuration options and parameters to the system?)
- How to make sure that the system is installed correctly?
  
The above tasks should be achieved by executing a set of scripts provided by the authors that will download needed components (systems, libraries), initialize the environment, check that software and hardware is compatible, and deploy the system.

### Tools
The committee suggests that authors use Repro.Zip in order to streamline this process. ReproZip can be used to capture the environment, the input files, the expected output files, and the required libraries. A detailed how-to guide (installing, packing experiments, unpacking experiments) can be found there. ReproZip will help both the authors and the evaluators to seamlessly rerun experiments.

If using ReproZip to capture the experiments proves to be difficult for a particular paper, the committee will work with the authors to find the proper solution based on the specifics of the paper and the environment needed. More tools are available here: <https://reproduciblescience.org/reproducibility-directory/>
