---
title: "Design Considerations and Analysis of Multi-Level Erasure Coding in Large-Scale Data Centers"
date: 2023
publishDate:  2023
authors: ["Meng Wang", "Jiajun Mao", "Rajdeep Rana", "John Bent", "Serkay Olmez", "Anjus George", "Garrett Wilson Ransom", "Jun Li", "Haryadi S Gunawi"]
publication_types: ["2"]
abstract: "
Multi-level erasure coding (MLEC) has seen large deployments in the field, but there is no in-depth study of design considerations for MLEC at scale. In this paper, we provide comprehensive design considerations and analysis of MLEC at scale. We introduce the design space of MLEC in multiple dimensions, including various code parameter selections, chunk placement schemes, and various repair methods. We quantify their performance and durability, and show which MLEC schemes and repair methods can provide the best tolerance against independent/correlated failures and reduce repair network traffic by orders of magnitude. To achieve this, we use various evaluation strategies including simulation, splitting, dynamic programming, and mathematical modeling. We also compare the performance and durability of MLEC with other EC schemes such as SLEC and LRC and show that MLEC can provide high durability with higher encoding throughput and less repair network traffic over both SLEC and LRC."
featured: true
publication: "SuperComputing, 2023."
links:
  - icon_pack: fas
    icon: scroll
    name: Link
    url: 'https://ucare.cs.uchicago.edu/pdf/sc23-mlec.pdf'
  - icon_pack: ai
    icon: github
    name: Artifact
    url: 'https://github.com/ucare-uchicago/mlec-sim'
---
