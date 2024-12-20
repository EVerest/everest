.. _index:

.. admonition:: Current Version |version|

    You are looking at the documentation for the |version| release of EVerest.
    See `snapshot file <./appendix/snapshot.html>`_ for further version mapping.
    See `versions index <../versions_index.html>`_ for other versions.

.. image:: img/everest_horizontal-color.svg
    :align: right


******************************
Welcome to the EVerest project
******************************

You are at the entry point to the EVerest documentation.

EVerest is an open source modular framework for setting up a full stack
environment for EV charging.

EVerest will help to speed the adoption to e-mobility by utilizing all the open
source advantages for the EV charging world. It will also enable new features
for local energy management, PV-integration and many more.

The EVerest project was initiated by `PIONIX GmbH <https://pionix.com>`_
(`Pionix at LinkedIn <https://www.linkedin.com/company/pionix-gmbh>`_) to help
with the electrification of the mobility sector and is an official project of
the Linux Foundation Energy.


***************
EVerest compass
***************

.. |link_youtube| raw:: html

  <a href="https://www.youtube.com/@lfe_everest" target="_blank">
     <img src="_static/icons/youtube.svg" style="height: 0.8em"> <b>YouTube Channel</b>
  </a>

This EVerest compass shall guide you.

You have several options how to continue from here:

* :ref:`High level introduction <doc_framework>` to EVerest.
  That also includes references to more detailed how-to documents.

* No theory, but directly looking for practice? Try the
  :ref:`Quick Start Guide <quickstartguide_main>`.
  (It is not as quick as a wink of an eye, but hey: You are working on
  21st century high-voltage, tendsetting technology. Give it some time!)

* The EVerest release notes and the development roadmap (TO BE LINKED)
.. |link_roadmap| raw:: html
    <a href="https://github.com/EVerest/EVerest/blob/main/tsc/ROADMAP.md" target="_blank">
      <b>roadmap on GitHub</b>
    </a>

* The :ref:`EVerest source code repositories <reference_repositories>`.
  The EVerest open-source project is hosted on GitHub. Follow the link, if you
  want to get an overview over important repositories and hints where
  to find specific feature implementations.

* Diving into the :ref:`EVerest community <reference_community_channels>`.
  Learn about how to reach the developers and where to find the communication
  channels.
  See also our |link_youtube|, with which you can stay up-to-date with webinars
  and get insights from the Technical Steering Committee recordings.

* **Contribution guides**
  If you want to contribute to the EVerest source code, see the
  `CONTRIBUTION.md file <https://github.com/EVerest/EVerest/blob/main/CONTRIBUTING.md>`_
  in the main EVerest repository.
  Or do you rather want to take part in optimizing the documentation?
  Here is your place to go: :ref:`Documenting EVerest <documenting_everest>`.


For a complete list of all existing documentation pages of EVerest, have a look
at the following pages.

.. note::
  We are currently re-structuring things about EVerest documentation. Up to
  now, those pages do not have all documentation pages listed. That's still
  work-in-progress.

* Explanation pages, which give you an overview of features, concepts, tools
  etc.

* How-to guides, which help you reach a specific goal within EVerest.

* Tutorials, which help you learn concepts or techniques around EVerest.

* Reference pages, which is an automatically generated list of
  inline-documentation.


*****************
Table Of Contents
*****************

.. toctree::
    :numbered:
    :maxdepth: 2
    :glob:

    general/01_framework/index
    general/02_detail_pre_setup
    general/03_quick_start_guide
    general/04_detail_module_concept
    general/05_existing_modules
    general/06_handling_bank_cards
    general/07_configure_plug_and_charge
    dev_tools/index
    tutorials/index
    general/faq
    hardware/*
    appendix/*
    appendix/*/index

Indices and tables
==================

* :ref:`genindex`
* :ref:`search`
