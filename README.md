# <img src="docs/assets/climb-logo-no-text.png" height=25> CliMB-DC

This repository contains **CliMB-DC**, a Data-Centric copilot system that builds upon the [CliMB](https://github.com/vanderschaarlab/climb) ecosystem.

## 📦 Installation: CliMB-DC
The installation process is analogous to the original CliMB system, with the only difference being in the [📈 Install the CliMB package step](https://climb-ai.readthedocs.io/en/latest/installation.html#install-the-climb-package). You should replace the command:
```bash
git clone https://github.com/vanderschaarlab/climb.git
```
with:
```bash
git clone -b climb-dc-canonical https://github.com/vanderschaarlab/climb.git
```

## 🚀 Usage: CliMB-DC

In order to run CliMB-DC, you can follow the original [CliMB quickstart guide](https://climb-ai.readthedocs.io/en/latest/quickstart.html) but choose the *engine* (in the *Research Management* page, *Select engine* dropdown) to be:
```
openai_dc
```
or
```
azure_openai_dc
```
depending on the OpenAI model provider you are using.

## 📃 Note on Licensing

The code inside [`impl_agpl` directory](./src/climb/tool/impl_agpl) is only compatible with the [AGPL-3.0 license](https://choosealicense.com/licenses/agpl-3.0/).

It is not compatible with the [Apache-2.0 license](https://choosealicense.com/licenses/apache-2.0/), under which the core of the project (CliMB-DC **core**) is licensed.

If you wish to use the extra tools provided in the `impl_agpl` directory, you must explicitly install the `[extra]` version of CliMB-DC like so:

```bash
# Clone the *CliMB-DC* repository.
git clone -b climb-dc-canonical https://github.com/vanderschaarlab/climb.git
cd climb
# Install with the `[extra]` option.
pip install -e climb[extra]
```

If you are forking/deriving from the code that **requires the tools in the `impl_agpl` directory** (i.e. CliMB-DC with `[extra]`), you **must** also license your code under the AGPL-3.0 license.

**Note:**

The code of CliMB-DC **core** does not depend on the code in the `impl_agpl` directory or its functionality. The `[extra]` version is *completely isolated and optional*.
Hence the core of CliMB-DC can be used under the Apache-2.0 license while the tools in the `impl_agpl` directory can be used *only* under the AGPL-3.0 license.

---

*Below you can find the content of the original README.md file for the CliMB system.*

<!-- CliMB README.md -->

<!-- exclude_docs -->
[![Documentation Status](https://readthedocs.org/projects/climb-ai/badge/?version=latest)](https://climb-ai.readthedocs.io/en/latest/?badge=latest)
[![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?logo=YouTube&logoColor=white)](https://www.youtube.com/watch?v=76XuR0K3F5Y)

[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-370/)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](./LICENSE.txt)
<!-- [![PyPI-Server](https://img.shields.io/pypi/v/climb-ai?color=blue)](https://pypi.org/project/climb-ai/) -->
<!-- [![Downloads](https://static.pepy.tech/badge/climb-ai)](https://pepy.tech/project/climb-ai) -->

[![arXiv](https://img.shields.io/badge/arXiv-2301.12260-b31b1b.svg)](http://arxiv.org/abs/2410.03736)
[![slack](https://img.shields.io/badge/chat-on%20slack-purple?logo=slack)](https://join.slack.com/t/vanderschaarlab/shared_invite/zt-1u2rmhw06-sHS5nQDMN3Ka2Zer6sAU6Q)
<!-- exclude_docs_end -->

# <img src="docs/assets/climb-logo-no-text.png" height=25> CliMB

> **CliMB**: **Cli**nical **M**achine learning **B**uilder

This repository is the implementation of the system as described in the preprint [CliMB: An AI-enabled Partner for Clinical Predictive Modeling](http://arxiv.org/abs/2410.03736).

[<img src="docs/assets/play.svg" height=12> Watch the demo](https://www.youtube.com/watch?v=76XuR0K3F5Y)

[![Demo Video](docs/assets/video-demo.gif)](https://www.youtube.com/watch?v=76XuR0K3F5Y)



## 🏥 Overview
CliMB is an AI-enabled partner designed to empower clinician scientists to create predictive models from real-world clinical data, all within a single conversation. With its no-code, natural language interface, CliMB guides you through the entire data science pipeline, from data exploration and engineering to model building and interpretation. The intuitive interface combines an interactive chat with a dashboard that displays project progress, data transformations, and visualizations, making it easy to follow along. Leveraging state-of-the-art methods in AutoML, data-centric AI, and interpretability tools, CliMB offers a streamlined solution for developing robust, clinically relevant predictive models.

<img src="docs/assets/climb-fig-clinical.png" width=45% alt="CliMB Clinical Figure"> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src="docs/assets/climb-fig-main.png" width=45% alt="CliMB Conceptual Figure">

Our vision is for CliMB to integrate seamlessly into the clinician's workflow, supporting the complete cycle of clinical predictive modeling, and ultimately democratizing machine learning and AI utilization in healthcare.

<!-- exclude_docs -->
> [!NOTE]
> The intended target audience of CliMB is a clinician scientists with some basic Python and AI knowledge.
> If you do not consider yourself "tech-savvy", the installation and configuration steps in particular may require assistance from your IT department.
<!-- exclude_docs_end -->
<!-- include_docs
```{admonition} Target audience
:class: note

The intended target audience of CliMB is a clinician scientists with some basic Python and AI knowledge.
If you do not consider yourself "tech-savvy", the installation and configuration steps in particular may require assistance from your IT department.
```
include_docs_end -->



## 🔏 Data Privacy
<!-- exclude_docs -->
> [!WARNING]  
> It is crucial to understand the data privacy and confidentiality implications of using CliMB. Please ensure to read and understand the [Data Privacy documentation section](https://climb-ai.readthedocs.io/en/latest/dataprivacy.html) in full prior to installing and using the system.
<!-- exclude_docs_end -->
<!-- include_docs
```{admonition} Warning
:class: attention

It is crucial to understand the data privacy and confidentiality implications of using CliMB. Please ensure to read and understand the [Data Privacy documentation section](dataprivacy.md) in full prior to installing and using the system.
```
include_docs_end -->

When using CliMB with real-world clinical data, you as the clinician scientist act as the data steward, and are responsible for ensuring that the use of the data complies with all the relevant laws and regulations, as well as ethical considerations. CliMB aims to provide a secure and privacy-preserving environment for data exploration and model building, while balancing this with leveraging the capabilities of the most advanced large language models (LLMs).

We provide a detailed section in the documentation, which summarizes the data privacy fundamentals of CliMB and should allow you to make an informed decision about using the system with your data. It is essential that you read and understand this prior to using CliMB, please find the link below:

<!-- exclude_docs -->
#### [📕 **Must-read:** Data Privacy documentation](https://climb-ai.readthedocs.io/en/latest/dataprivacy.html)
<!-- exclude_docs_end -->
<!-- include_docs
#### [📕 **Must-read:** Data Privacy documentation](dataprivacy.md)
include_docs_end -->



## 📦 Installation

<!-- exclude_docs -->
> [!WARNING]  
> Please read the [🔏 Data Privacy](https://climb-ai.readthedocs.io/en/latest/dataprivacy.htmldata-privacy) documentation section before proceeding with this step, in order to understand whether CliMB is compatible with your data and use case.

Please follow the steps in [📦 Installation](https://climb-ai.readthedocs.io/en/latest/installation.html) section in the documentation to install CliMB.

To update to the latest version of CliMB, please follow [📦⬆️ Updating CliMB](https://climb-ai.readthedocs.io/en/latest/installation.html#updating-climb)
<!-- exclude_docs_end -->
<!-- include_docs
```{admonition} Warning
:class: attention

Please read the [🔏 Data Privacy](dataprivacy.md) section before proceeding with this step, in order to understand whether CliMB is compatible with your data and use case.
```

Please follow the steps in [📦 Installation](docs/installation.md) section in the documentation to install CliMB.

To update to the latest version of CliMB, please follow [📦⬆️ Updating CliMB](docs/installation.md#updating-climb)
include_docs_end -->



## 🚀 Usage
First, navigate to the the CliMB **repo directory** in the terminal.
<!-- exclude_docs -->
> [!TIP]
> The location of the **repo directory** is explained in the [📈 Install the CliMB package](https://climb-ai.readthedocs.io/en/latest/installation.html#install-the-climb-package) section of the documentation. Don't forget to run `cd climb` to change to the repo directory.
<!-- exclude_docs_end -->
<!-- include_docs
```{admonition} Repo directory
:class: tip

The location of the **repo directory** is explained in the [📈 Install the CliMB package](installation.md#install-the-climb-package) section of the documentation. Don't forget to run `cd climb` to change to the repo directory.
```
include_docs_end -->

To launch CliMB UI, run the command:
```bash
streamlit run entry/st/app.py
```

This will show the output like:
```
  You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8501
  Network URL: http://192.168.0.68:8501
```

<!-- exclude_docs -->
The best way to get started with CliMB is to follow the [**🚀 Quickstart Guide**](https://climb-ai.readthedocs.io/en/latest/quickstart.html) in the documentation.

### Troubleshooting and getting help

If you encounter errors or problems when running CliMB for the first time, please check out the [🛠️ Troubleshooting](https://climb-ai.readthedocs.io/en/latest/troubleshooting.html) section, as it has the resolution steps for some common installation and set up problems. For any other problems, please submit a GitHub issue [here](https://github.com/vanderschaarlab/climb/issues), or ask us on [Slack](https://join.slack.com/t/vanderschaarlab/shared_invite/zt-1u2rmhw06-sHS5nQDMN3Ka2Zer6sAU6Q), `#climb` channel.
<!-- exclude_docs_end -->
<!-- include_docs
The best way to get started with CliMB is to follow the [**🚀 Quickstart Guide**](quickstart.md) in the documentation.

If you encounter errors or problems when running CliMB for the first time, please check out the [🛠️ Troubleshooting](troubleshooting.md) section, as it has the resolution steps for some common installation and set up problems. For any other problems, please submit a GitHub issue [here](https://github.com/vanderschaarlab/climb/issues), or ask us on [Slack](https://join.slack.com/t/vanderschaarlab/shared_invite/zt-1u2rmhw06-sHS5nQDMN3Ka2Zer6sAU6Q).
include_docs_end -->



<!-- exclude_docs -->
## 📚 Documentation

You will find much more useful information in the [project documentation](https://climb-ai.readthedocs.io/).

We have compiled some of the most common questions in the [FAQ](https://climb-ai.readthedocs.io/en/latest/faq.html) section, so please do check it out.
<!-- exclude_docs_end -->



## 📝 Disclaimer

By accessing and using this software, you acknowledge and agree that you do so at your own risk. The copyright holders and contributors of this software and its associated web-based tools disclaim any liability for inaccuracies, errors, or omissions in the analyses generated or for any actions taken based on these analyses. 

This software is provided on an "as-is" basis without any warranties, expressed or implied, including but not limited to accuracy, fitness for a particular purpose, or compatibility with regulatory requirements. The copyright holders and contributors assume no responsibility for any clinical or non-clinical outcomes that may arise from use of this software or its results.

**Data Privacy and Confidentiality:**  
You are solely responsible for ensuring that any data entered into this system complies with relevant confidentiality and data privacy regulations, including HIPAA, GDPR, or any other applicable standards. As this software utilizes third-party, proprietary large language model (LLM) APIs, the copyright holders and contributors are not responsible for data security or regulatory compliance in relation to the use of these external APIs. It is the user's responsibility to anonymize data as required and to ensure that data-sharing practices align with the applicable privacy laws and institutional policies.

<!-- exclude_docs -->
You acknowledge that you have read and understood the [Data Privacy documentation](https://climb-ai.readthedocs.io/en/latest/dataprivacy.html) and the implications of using this software with your data described therein.
<!-- exclude_docs_end -->
<!-- include_docs
You acknowledge that you have read and understood the [Data Privacy documentation](dataprivacy.md) and the implications of using this software with your data described therein.
include_docs_end -->

By proceeding to use this software, you agree to these terms and accept full responsibility for your use and management of any data within this system.



## ✍️ Citing

If you use CliMB in your work, please cite the [associated paper](http://arxiv.org/abs/2410.03736):
```bibtex
@article{saveliev2024climb,
  title={CliMB: An AI-enabled Partner for Clinical Predictive Modeling},
  author={Saveliev, Evgeny and Schubert, Tim and Pouplin, Thomas and Kosmoliaptsis, Vasilis and van der Schaar, Mihaela},
  journal={arXiv preprint arXiv:2410.03736},
  year={2024}
}
```
