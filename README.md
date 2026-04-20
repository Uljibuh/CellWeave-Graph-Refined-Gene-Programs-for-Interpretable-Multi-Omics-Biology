# CellWeave-Graph-Refined-Gene-Programs-for-Interpretable-Multi-Omics-Biology


🧠 Core Idea

CellWeave is a framework for interpreting disease mechanisms from paired single-cell RNA and ATAC data by combining interpretable gene programs with structured gene interaction networks. It first learns gene programs using Non-negative Matrix Factorization, where each program represents a coordinated biological function shared across cells. Then, instead of treating these programs as flat gene lists, CellWeave introduces a gene interaction graph within each program and uses a Graph Neural Network to refine gene-level contributions based on regulatory relationships such as transcription factor binding, chromatin accessibility, and gene co-regulation. This produces context-aware gene program representations that better reflect how biological systems operate in normal and disease conditions.

🧩 Biological Motivation
Single-cell multi-omics data reveals that:

genes do not act independently
gene programs are modular but internally structured
disease often arises from rewiring within programs, not just between them

However, most existing approaches treat gene programs as:

simple weighted gene lists

CellWeave instead assumes:

each gene program contains an internal regulatory network

🔬 Method Overview (conceptual flow)

1. Gene Program Discovery
Using Non-negative Matrix Factorization, we identify:
shared gene programs across cells
each program represents a biological function (e.g., immune activation, cell cycle, stress response)

2. Construction of Program-Specific Gene Graphs
For each gene program, we construct a biologically informed gene graph using:
transcription factor → target relationships
enhancer–gene links from ATAC data
gene co-regulation signals
This defines the internal structure of a program.

3. Graph-Based Refinement of Gene Programs
A Graph Neural Network is applied inside each program to:
propagate regulatory influence between genes
refine gene contributions based on local network context
identify context-dependent gene importance
This step transforms each program from a static gene list into a structured regulatory module.

4. Reconstruction of Multi-Omics Signals
The refined gene programs are used to reconstruct:
gene expression (RNA)
chromatin accessibility (ATAC)
This ensures that learned structures are consistent with observed biology.


5. Disease Interpretation
By comparing refined programs across conditions (normal vs disease), CellWeave identifies:
which gene programs are disrupted
which internal regulatory relationships are rewired
which genes change their functional context within the same program


🧠 Key Biological Insight
Instead of viewing disease as:

changes in gene expression or changes in gene sets
CellWeave views disease as:
changes in the internal regulatory structure of gene programs
This allows the model to capture:
subtle regulatory rewiring
context-dependent gene function
hidden substructure within biological pathways

🔥 What Makes This Different
Compared to standard multi-omics methods:
Traditional approaches:
gene programs = flat feature vectors
ignore internal structure
focus on differential expression

CellWeave:
gene programs = structured regulatory networks
models interactions inside programs
captures disease as network-level rewiring within modules

🧬 Expected Biological Outputs
CellWeave enables:
refined gene importance within pathways
identification of submodules inside canonical pathways
detection of disease-specific regulatory rewiring
cross-modality consistency between RNA and ATAC
