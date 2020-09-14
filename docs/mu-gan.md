# MU-GAN

> MU-GAN: Facial Attribute Editing based on Multi-attention Mechanism.

- [Brief introduction](#brief-introduction)
- [Main contributions](#main-contributions)
- [Method overview](#method-overview)
- [Experiments](#experiments)

:::tip 🌏 Source
Available at: <https://arxiv.org/abs/2009.04177>. Source code at: [SuSir1996/MU-GAN](https://github.com/SuSir1996/MU-GAN).
:::

## Brief introduction

Task: **facial attribute editing**, which has two main objectives:

1. To translate an image from a source domain to a target one
2. only change the facial regions related to a target attribute and preserving the attribute-excluding details

The **Multi-attention U-Net-based Generative Adversarial Network (MU-GAN)**:

- "Classic convolutional encoder-decoder" --> "Symmetric U-Net-like structure in a generator": Apply an additive attention mechanism to build attention-based U-Net connections for adaptively transferring encoder representations to complement a decoder with attribute-excluding detail and enhance attribute editing ability.
- A self-attention mechanism is incorporated into convolutional layers for modeling long-range and multi-level dependencies across image regions.

## Main contributions

CNN-based GANs are good at editing local attributes and synthesizing images with few geometric constraints. However, they have difficulty in editing images with geometric or structural patterns (such as facial attribute editing). It is also known that there are complex coupling relationships among facial attributes (e.g.: gender and beard).

![](./assets/2020-09-14-18-51-47.png)

Thus, a desired model needs to have the ability to decouple attributes in order to meet the requirements of the target labels. To solve these problems, we construct a new generator with a novel encoder-decoder architecture and propose a **Multi-attention U-Net-based GAN (MU-GAN) model.**

- We construct a symmetric U-Net-like architecture generator based on additive attention mechanism, which effectively enhances our method's detail preservation and attribute manipulation abilities.
- We take a self-attention mechanism into the existing encoder-decoder architecture thus effectively enforcing geometric constraints on generated results.
- We introduces a multi-attention mechanism to help attribute decoupling, i.e., it only changes the attributes that need to be changed.

## Method overview

## Experiments