---
layout: page
date: 2021-06-15
title: "Exploiting and Defending Against the Approximate Linearity of Apple's NeuralHash"
ref: NEURALHASH
desc: Breaking Apple's NeuralHash through Approximate Linearity
# redirect: https://sites.google.com/site/multipleframesmatching/
pub: ICML ML4Cyber Workshop 2022
pdf: "neuralhash icml ml4cyber 2022.pdf"
arxiv: "2207.14258"
authors: [{first: "Jagdeep Singh", last: Bhatia, sup: '1'}, {first: Kevin, last: Meng, sup: '1'}]
---

Perceptual hashes map images with identical semantic content to the same n-bit hash value, and otherwise assign images to different hashes. Apple's NeuralHash is one such system aiming to detect illegal content on users' devices without compromising consumer privacy. We make the surprising discovery that NeuralHash is *approximately linear*, which inspires the development of novel black-box attacks that can (i) evade detection of 'illegal' images, (ii) generate near-collisions, and (iii) leak information about hashed images, all without access to model parameters. These vulnerabilities pose serious threats to NeuralHash's security goals; to address them, we propose a simple fix using classical cryptographic standards.