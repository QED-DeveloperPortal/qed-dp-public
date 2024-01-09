---
title: What is MPC and how might I use it?
author: andrew
categories: [public]
tags: [privacy]
date: 2023-05-11 01:26:26
likes: 0
---

MPC (Multiparty Computation) is a technique used to perform computations on data without revealing the data itself. This can be useful in a wide range of applications where data privacy is important. One example of using MPC in an application is in the context of secure machine learning.

Secure machine learning is the process of training machine learning models on sensitive data without compromising the privacy of the data. MPC can be used to enable secure machine learning by allowing multiple parties to collaborate in the training process without revealing their private data.

For example, consider a scenario where multiple hospitals want to collaborate to train a machine learning model to predict the likelihood of a patient developing a particular disease. Each hospital has its own set of patient data, which is sensitive and cannot be shared due to privacy concerns.

To enable collaboration while preserving privacy, the hospitals can use MPC. The data from each hospital is encrypted and distributed among the parties, who collaborate to train the machine learning model using the encrypted data. The MPC protocol ensures that none of the parties can access the data from the other parties, and the resulting trained model can be decrypted and used without revealing any of the underlying data.

This approach allows for secure collaboration and training of machine learning models on sensitive data, without compromising privacy. Similar applications of MPC can be found in other areas, such as finance, where multiple parties need to collaborate while preserving the privacy of their data.