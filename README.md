# ![nf-core/raredisease](docs/images/nf-core-raredisease_logo_light.png#gh-light-mode-only) ![nf-core/raredisease](docs/images/nf-core-raredisease_logo_dark.png#gh-dark-mode-only)

[![AWS CI](https://img.shields.io/badge/CI%20tests-full%20size-FF9900?labelColor=000000&logo=Amazon%20AWS)](https://nf-co.re/raredisease/results)[![Cite with Zenodo](http://img.shields.io/badge/DOI-10.5281/zenodo.7995798-1073c8?labelColor=000000)](https://doi.org/10.5281/zenodo.7995798)

[![Nextflow](https://img.shields.io/badge/nextflow%20DSL2-%E2%89%A523.04.0-23aa62.svg)](https://www.nextflow.io/)
[![run with conda](http://img.shields.io/badge/run%20with-conda-3EB049?labelColor=000000&logo=anaconda)](https://docs.conda.io/en/latest/)
[![run with docker](https://img.shields.io/badge/run%20with-docker-0db7ed?labelColor=000000&logo=docker)](https://www.docker.com/)
[![run with singularity](https://img.shields.io/badge/run%20with-singularity-1d355c.svg?labelColor=000000)](https://sylabs.io/docs/)
[![Launch on Nextflow Tower](https://img.shields.io/badge/Launch%20%F0%9F%9A%80-Nextflow%20Tower-%234256e7)](https://tower.nf/launch?pipeline=https://github.com/nf-core/raredisease)

[![Get help on Slack](http://img.shields.io/badge/slack-nf--core%20%23raredisease-4A154B?labelColor=000000&logo=slack)](https://nfcore.slack.com/channels/raredisease)[![Follow on Twitter](http://img.shields.io/badge/twitter-%40nf__core-1DA1F2?labelColor=000000&logo=twitter)](https://twitter.com/nf_core)[![Follow on Mastodon](https://img.shields.io/badge/mastodon-nf__core-6364ff?labelColor=FFFFFF&logo=mastodon)](https://mstdn.science/@nf_core)[![Watch on YouTube](http://img.shields.io/badge/youtube-nf--core-FF0000?labelColor=000000&logo=youtube)](https://www.youtube.com/c/nf-core)

## Introduction

**raredisease-1.0** is a Synapsys pipeline designed for the analysis of rare diseases. This version includes the following features: it utilizes fastp for quality control and preprocessing of raw sequencing data, implements bwa-mem2 for efficient and accurate alignment of sequencing reads, employs MarkDuplicates to identify and remove duplicate reads from the aligned BAM files, and runs qCBAM on the aligned BAM files to ensure high-quality data. Additionally, it uses HaplotypeCaller for variant calling and annotates the identified variants. This pipeline focuses on single nucleotide variants (SNVs) and small insertions and deletions (SMNCopyNumberCaller), and **does not include structural variants (SVs), germline copy number variants (GermlineCNVCaller), or mitochondrial DNA (MT) analysis**.

The pipeline is built using [Nextflow](https://www.nextflow.io), a workflow tool to run tasks across multiple compute infrastructures in a very portable manner. It uses Docker/Singularity containers making installation trivial and results highly reproducible. The [Nextflow DSL2](https://www.nextflow.io/docs/latest/dsl2.html) implementation of this pipeline uses one container per process which makes it much easier to maintain and update software dependencies. Where possible, these processes have been submitted to and installed from [nf-core/modules](https://github.com/nf-core/modules) in order to make them available to all nf-core pipelines, and to everyone within the Nextflow community!
