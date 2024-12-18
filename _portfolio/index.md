---
layout: splash
permalink: /
title: "ML Driven Targeting for HIV-I Inhibition"
header:
  overlay_image: "assets/images/HIV.jpg" # Path to the image
  overlay_filter: 0.5 # Optional; darkens the image
  overlay_full: true # Ensures the image spans the full width
---

## Table of contents

- [HIV-1: The Global Health Challenge We’re Still Fighting 🌍💔](#hiv-1-the-global-health-challenge-were-still-fighting-)
  - [Why HIV-1 is the Virus Scientists Can't Stop Studying 🔬🦠](#why-hiv-1-is-the-virus-scientists-cant-stop-studying-)
  - [Uncovering New Ligand Families for HIV-1: A Journey into Molecular Discovery 🔍🧬](#uncovering-new-ligand-families-for-hiv-1-a-journey-into-molecular-discovery-)
    - [Decoding the Molecular Blueprint: From SMILES to Clusters 💡🔑](#decoding-the-molecular-blueprint-from-smiles-to-clusters-)


## HIV-1: The Global Health Challenge We’re Still Fighting 🌍💔

Human Immunodeficiency Virus Type 1 (HIV-1) has claimed the lives of over *42 million* people and remains a formidable global health challenge. By the end of 2023, approximately *39.9 million* individuals were living with HIV. While a cure remains elusive, remarkable advancements in prevention, diagnosis, treatment, and care—including the management of opportunistic infections—have transformed HIV from a fatal illness into a chronic, manageable condition. Today, individuals with access to proper care can lead long and healthy lives.

Despite these milestones, the fight against HIV is far from over. The scientific community continues to push the boundaries of innovation, developing protein inhibitors and other cutting-edge therapeutic approaches to improve treatment outcomes and combat the virus more effectively.

## Why HIV-1 is the Virus Scientists Can't Stop Studying 🔬🦠

HIV-1 isn’t just another virus in the global health landscape—it’s one of the most studied viruses in both academia and industry. In fact, if you take a look at the research landscape, you'll see that HIV-1 leads the charge in terms of global attention, far outpacing other viruses. It’s like the rockstar of the virology world! Why? Because HIV-1 has proven to be tricky, resilient, and constantly evolving, making it a worthy adversary for researchers and drug developers alike.

{% include HIV1study.html %}

There is some text here.

{% include piechartHIV.html %}

## Uncovering New Ligand Families for HIV-1: A Journey into Molecular Discovery 🔍🧬

Our mission? To uncover potential families of ligands that could be the key to tackling HIV-1. But how do we do that? Well, we’ve got a toolkit of high-tech tricks up our sleeves to get to the heart of this molecular puzzle.

### Decoding the Molecular Blueprint: From SMILES to Clusters 💡🔑

We started with SMILES—the digital language for describing molecular structures. By converting various ligands into these SMILES strings, we could then transform them into Morgan fingerprints, which capture the intricate details of their molecular structure. But here’s where the magic happens: we used UMAP (Uniform Manifold Approximation and Projection) to reduce all that high-dimensional data down to just three simple dimensions. Why? To make the data visualizable and easier to analyze. This step is like taking a 3D map of an entire galaxy and zooming in on the most interesting star systems.

Next, we applied k-means clustering, a method that groups similar items together, like organizing a playlist by genre. The result? Four distinct ligand clusters, each representing a family of compounds with unique characteristics that set them apart from the others.
