---
layout: splash
permalink: /
title: "ML Driven Targeting for HIV-I Inhibition"
header:
  overlay_image: "assets/images/HIV.jpg" # Path to the image
  overlay_filter: 0.5 # Optional; darkens the image
  overlay_full: true # Ensures the image spans the full width
---

---
# Table of contents

- [Introduction](#introduction)
- [Is HIV-1 studied a lot? 🔬🦠](#is-hiv-1-studied-a-lot-)
- [Uncovering New Ligand Families for HIV-1: A Journey into Molecular Discovery 🔍🧬](#uncovering-new-ligand-families-for-hiv-1-a-journey-into-molecular-discovery-)
  - [Decoding the Molecular Blueprint: From SMILES to Clusters 💡🔑](#decoding-the-molecular-blueprint-from-smiles-to-clusters-)
- [Analysis of different properties of the ligands](#analysis-of-different-properties-of-the-ligands)
  - [Focusing In: The Target That Stands Out 🎯🦠](#focusing-in-the-target-that-stands-out-)
  - [Are the families similar in Ki values? 🔑💥](#are-the-families-similar-in-ki-values-)
  - [Molecular Weight: A Crucial Factor in Drug Discovery 🏋️‍♀️💊](#molecular-weight-a-crucial-factor-in-drug-discovery-)
  - [Hydrophobicity: The Permeability Puzzle 💧🧪](#hydrophobicity-the-permeability-puzzle-)
  - [Stereocenters: The Complexity Factor 🔀🧬](#stereocenters-the-complexity-factor-)
  - [Hydrogen Bonds: The Secret Weapon of Binding Interactions 🧪💨](#hydrogen-bonds-the-secret-weapon-of-binding-interactions-)
  - [Tanimoto Similarities: Unraveling the Molecular Family Resemblance 🧬🔍](#tanimoto-similarities-unraveling-the-molecular-family-resemblance-)
  - [TPSA: A Key to Bioavailability and Drug Design 💊💡](#tpsa-a-key-to-bioavailability-and-drug-design-)
  - [The Radar of Drug Design: Profiling Our Top 10 Gag-Pol Inhibitors 🎯💊](#the-radar-of-drug-design-profiling-our-top-10-gag-pol-inhibitors-)
- [Insights gained on illuminating the Path to Optimized HIV-1 Inhibitors 🧪💊](#insights-gained-on-illuminating-the-path-to-optimized-hiv-1-inhibitors-)
- [Affinity Prediction](#affinity-prediction)
---

# Introduction

Human Immunodeficiency Virus Type 1 (HIV-1) has claimed over 42 million lives and remains a significant global health challenge. By the end of 2023, approximately 39.9 million people were living with HIV. While a cure is yet to be found, remarkable advancements in prevention, diagnosis, treatment, and care—including managing opportunistic infections—have transformed HIV from a fatal illness into a chronic, manageable condition. Today, individuals with access to proper care can lead long and healthy lives.

Despite these strides, the fight against HIV is far from over. The scientific community continues to innovate, developing protein inhibitors and other cutting-edge therapeutic approaches to enhance treatment outcomes and combat the virus more effectively. Developing effective inhibitors for HIV-1 remains a complex and crucial goal for both industry and academia.

Our objective is to identify families of ligands with shared structural and chemical properties that can inhibit HIV-1, facilitating the design of novel, targeted inhibitors. To achieve this, we will leverage clustering algorithms to classify ligands based on their characteristics, paving the way for more precise and effective therapeutic interventions.

# Is HIV-1 studied a lot? 🔬🦠

HIV-1 isn’t just another virus in the global health landscape—it’s one of the most studied viruses in both academia and industry. In fact, if you take a look at the research landscape, you'll see that HIV-1 leads the charge in terms of global attention, far outpacing other viruses. It’s like the rockstar of the virology world! Why? Because HIV-1 has proven to be tricky, resilient, and constantly evolving, making it a worthy adversary for researchers and drug developers alike.

{% include HIV1_study.html %}

{% include pie_chart_HIV.html %}

# Uncovering New Ligand Families for HIV-1: A Journey into Molecular Discovery 🔍🧬

Our mission? To uncover potential families of ligands that could be the key to tackling HIV-1. But how do we do that? Well, we’ve got a toolkit of high-tech tricks up our sleeves to get to the heart of this molecular puzzle.

## Decoding the Molecular Blueprint: From SMILES to Clusters 💡🔑

We started with *SMILES*, the digital language for describing molecular structures. By converting various ligands into these SMILES strings, we could then transform them into *Morgan Fingerprints*, which capture the intricate details of their molecular structure. But here’s where the magic happens: we used *UMAP* (Uniform Manifold Approximation and Projection) to reduce all that high-dimensional data down to just three simple dimensions. Why? To make the data visualizable and easier to analyze. This step is like taking a 3D map of an entire galaxy and zooming in on the most interesting star systems.

Next, we applied *K-means* clustering, a method that groups similar items together, like organizing a playlist by genre. The result? *Four* distinct ligand clusters, each representing a family of compounds with unique characteristics that set them apart from the others.

Cluster plot

# Analysis of different properties of the ligands

Now lets start analysing some properties of these clusters to gain some insights.

## Focusing In: The Target That Stands Out 🎯🦠

Our analysis then led us to a critical decision, which HIV-1 target should we focus on? After analyzing the clusters, we found that the *Gag-Pol Polyprotein [489-587]* was the most prevalent target across all four groups (as illustrated below). This polyprotein is a key player in the virus’s lifecycle, making it a prime target for further exploration. 

So, we’ve decided to zoom in on gag-pol and dive deeper into the ligands that target this particular protein.

{% include targets_by_cluster.html %}

## Are the families similar in Ki values? 🔑💥

In drug discovery, *Ki* is the superstar we need to understand. It measures how tightly a ligand binds to its target - the stronger the binding, the better the drug. Think of it like a handshake: a firm, steady grip means the ligand is really connecting with its target, which is exactly what we want in our potent inhibitors.

By analyzing how Ki values vary across our clusters, we can spot potential ligand families that show promise. The boxplot below shows the distribution of Ki values across the clusters, and there’s a notable trend: *Cluster 1* stands out with the lowest mean Ki, suggesting it’s particularly strong at binding to its target.

{% include boxplot_ki_by_cluster.html %}

## Molecular Weight: A Crucial Factor in Drug Discovery 🏋️‍♀️💊

Let’s talk about Molecular Weight (MW) — a key player in drug discovery. When designing drugs, especially for a complex target like HIV-1, MW significantly influences properties like absorption, solubility, and bioavailability.

According to Lipinski’s Rule of Five, molecules with a molecular weight under *500 Daltons* tend to have favorable absorption and bioavailability. However, as molecules get larger, they often face challenges like poor membrane permeability and inefficient clearance. While larger molecules might bind more effectively to their targets, they also struggle with penetrating tissues and reaching their sites of action.

When examining inhibitors of the HIV-1 Gag-pol polyprotein, most compounds exceed the 500 Dalton threshold. However, *Cluster 3* stands out with a mean molecular weight of 461 Daltons, the only family under 500. This offers researchers an exciting avenue to explore smaller, more flexible compounds while balancing potency and selectivity.

## Hydrophobicity: The Permeability Puzzle 💧🧪

Next up: hydrophobicity, the balancing act between water-loving (hydrophilic) and water-hating (hydrophobic) properties. This is measured by *LogP*, which indicates how a compound distributes itself between watery and fatty environments (like cell membranes).

An ideal LogP range is typically between 0 and 5, ensuring that the compound has good membrane permeability and solubility. Too hydrophobic? You risk poor solubility and nonspecific binding. Too hydrophilic? It won’t cross membranes effectively.

For inhibitors of the HIV-1 Gag-pol polyprotein, hydrophobicity values don’t perfectly align with the ideal range. *Clusters 0 and 2* are the only ones with LogP values within the desired range. This highlights room for improvement, as researchers tweak these compounds to find the perfect balance of permeability, solubility, and efficacy. It’s a fine-tuned process, much like brewing the perfect cup of coffee—not too bitter, not too watery!

{% include boxplot_logP_by_cluster.html %}

## Stereocenters: The Complexity Factor 🔀🧬

Now let’s dive into stereocenters—a critical element in drug design. A stereocenter introduces *chirality*, meaning the compound can have different mirror-image forms (stereoisomers), each potentially behaving differently in the body.

While stereocenters can improve a drug’s potency and selectivity, they also make the synthesis process more challenging. More stereocenters mean higher complexity, more steps during production, and increased costs.

For HIV-1 inhibitors, the number of stereocenters ranges between *2 and 5* across different ligand families. This balance is essential: enough structural complexity to boost activity, but not so much that synthesis becomes infeasible for large-scale production.

{% include boxplot_stereocenters_by_cluster.html %}

## Hydrogen Bonds: The Secret Weapon of Binding Interactions 🧪💨

We also wanted to dive into hydrogen bonds - those little but mighty interactions that help stabilize a ligand’s binding to its target. Hydrogen bond donors and acceptors play a pivotal role in how tightly and specifically a ligand can bind to a target protein.

We applied the same rigorous statistical tests to analyze hydrogen bond properties. Here’s what we found: for H-bond donors, all pairwise comparisons showed significant differences between clusters — except for clusters 1 and 0. For H-bond acceptors, the differences were significant across all clusters — except for clusters 1 and 3. This suggests that *cluster 1* has some unique binding characteristics, further setting it apart as a promising ligand family.

{% include boxplot_hdonors_by_cluster.html %}

{% include boxplot_hacceptors_by_cluster.html %}

## Tanimoto Similarities: Unraveling the Molecular Family Resemblance 🧬🔍

To dig deeper into the molecular relationships within each cluster, we turned to Tanimoto similarity, a handy metric that tells us how similar the structures of ligands are. It’s like matching up photos of people at a party and seeing how much they look alike—the Tanimoto score ranges from 0 (no similarity) to 1 (exactly the same).

So, what did we find? The highest similarity was in cluster 1, but the average similarity value was just *0.41*. Not exactly a perfect match, right? This suggests that while the ligands in the clusters share chemical properties, their actual structures are not identical.

## TPSA: A Key to Bioavailability and Drug Design 💊💡

Finally, let’s talk about Topological Polar Surface Area (TPSA), a critical measure of a compound’s bioavailability. TPSA helps us understand how well a compound can cross cell membranes, which is crucial for drugs taken orally. A TPSA under *140 angstroms* generally indicates good oral bioavailability.

When analyzing the clusters, *1 and 3* stood out with mean TPSA values below 140 angstroms, suggesting they may have excellent potential for oral administration. This is a promising find and a big step forward in designing effective and accessible drugs!

{% include mean_tpsa_by_cluster.html %}

## The Radar of Drug Design: Profiling Our Top 10 Gag-Pol Inhibitors 🎯💊

To visualize the key properties of our top 10 drugs targeting the HIV-1 Gag-Pol polyprotein, we turned to radar plots — a dynamic way to capture their strengths and weaknesses across multiple dimensions. Here’s a closer look at the five critical properties we evaluated:

1. **BBB Martins** (Blood-Brain Barrier Permeability): The blood-brain barrier acts as the brain’s bouncer, keeping harmful compounds out. For our drugs, low BBB values are ideal to avoid neurotoxicity—a major concern when designing safe therapeutics.

2. **hERG Inhibition**: Cardiac arrhythmia is one of the most frequent adverse effects of drugs, often caused by inhibition of the hERG cardiac gene. Minimizing this interaction is crucial for ensuring cardiovascular safety.

3. **Bioavailability** (`Bioavailability_Ma`): Drugs taken orally face hurdles like absorption through the gut and metabolism in the liver. A high bioavailability score is key for ensuring the drug reaches its target effectively.

4. **Aqueous Solubility** (`Solubility_AqSolDB`): Drugs must dissolve well in the bloodstream to circulate efficiently. Good solubility is a must for our compounds to mix seamlessly with polar environments like blood.

5. **Clinical Toxicity** (`ClinTox`): Every drug comes with some level of toxicity, but keeping this low is essential for meeting FDA and EMA approval.

What Did We Learn?

Our radar plots revealed that *nine* of our ten drugs share a consistent profile, with the first drug standing out as an exception. Here’s the breakdown:

- **Toxicity Insights**: While brain and cardiac toxicities (BBB: mean 0.511; hERG: mean 0.725) are on the medium-to-high side, clinical toxicity levels (ClinTox: mean 0.38) are comfortably low—an encouraging sign for meeting regulatory standards.

- **Diffusion Potential**: The bioavailability scores (mean 0.69) suggest our drugs diffuse well, offering good efficacy potential.

- **Solubility Checks**: The drugs exhibit moderate solubility (log solubility mean: -2.43), striking a balance between dissolving in blood and penetrating the non-polar viral membrane.

# Insights gained on illuminating the Path to Optimized HIV-1 Inhibitors 🧪💊

From our analysis of ligand clusters targeting HIV-1 Gag-pol polyprotein, *clusters 1 and 3* bring unique strengths and areas for improvement. Here are a few:

- **Affinity**: Cluster 1 stands out with the lowest mean Ki, indicating stronger binding affinity and potential for high efficacy. This makes it a promising candidate for further exploration.

- **Molecular Weight**: While molecular weights across clusters are generally high, cluster 3 is an outlier, boasting the only mean under 500 Daltons. This lower weight offers flexibility in optimization and may enhance membrane permeability.

- **TPSA**: Cluster 3 has the lowest mean TPSA, suggesting excellent bioavailability. However, cluster 1 also maintains a value under the critical 140-angstrom threshold, reinforcing its potential as an orally bioavailable drug family.

- **Stereocenters**: With a mean of just 2 stereocenters, cluster 3 offers simpler synthesis and lower production costs but may lack specificity. Cluster 1, with a mean of 4 stereocenters, strikes a better balance between structural complexity and ease of production, making it a versatile contender.

- **LogP**: Hydrophobicity remains a challenge, as LogP values across all clusters are higher than the optimal range. Improvements here are essential to enhance solubility and membrane permeability for all ligand families.

In summary, **Cluster 1** emerges as a promising lead with strong affinity, balanced structural complexity, and good bioavailability. **Cluster 3** offers intriguing advantages in molecular weight and synthesis simplicity but requires significant enhancement in specificity and binding characteristics. Moving forward, refining LogP values and leveraging the distinct strengths of these clusters will be key to developing potent, selective, and accessible inhibitors for HIV-1 Gag-pol polyprotein. 

The analysis of our top 10 drug candidates offers an optimistic outlook. These compounds demonstrate manageable toxicity levels, satisfactory solubility, and strong bioavailability, positioning them as promising options for further development. While hurdles like reducing BBB penetration and hERG inhibition persist, these drugs show significant potential to meet the stringent criteria for commercialization. The path toward a safe and effective HIV-1 inhibitor is shining with possibility!

# Affinity Prediction