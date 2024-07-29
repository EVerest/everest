.. _index:

.. admonition:: Current Version |version|

    You are looking at the documentation for the |version| release of EVerest.
    See `snapshot file <./appendix/snapshot.html>`_ for further version mapping.
    See `versions index <../versions_index.html>`_ for other versions.

.. image:: img/everest_horizontal-color.svg
    :align: right

***************
What Is EVerest
***************
EVerest is an open source modular framework for setting up a full stack
environment for EV charging.

The modular software architecture fosters customizability and lets you
configure your dedicated charging scenarios based on interchangeable modules.
All this is glued together by MQTT.

EVerest will help to speed the adoption to e-mobility by utilizing all the open
source advantages for the EV charging world. It will also enable new features
for local energy management, PV-integration and many more.

The EVerest project was initiated by `PIONIX GmbH <https://pionix.com>`_
(`Pionix at LinkedIn <https://www.linkedin.com/company/pionix-gmbh>`_) to help with the electrification of the mobility sector and is an official project of the Linux Foundation Energy.

***************
EVerest Compass
***************

You are currently on the main documentation page of EVerest.

There are quite a few other resources that you might want to check out:

.. _index_contact:

Direct contact
==============

.. _index_zulip:

Zulip chat
----------

On the Zulip instance of Linux Foundation Energy, there are chat channels for
EVerest.

This is for thought exchange, for questions and talks about dedicated work on
EVerest topics. Feel free to to drop your own questions and dive into
communication with other EVerest enthusiasts.

We have created working groups (see below) to focus on
special topics in EVerest and get the development communication structured.
You will see those working groups as streams in Zulip.

So, the best place to be near development thought exchange is Zulip.

You can find us here: https://lfenergy.zulipchat.com/

.. _index_mailinglist:

Mailing list
------------

.. |link_mailinglist| raw:: html

    <a href="https://lists.lfenergy.org/g/everest" target="_blank">
        <img src="_static/icons/mail.svg" style="height: 0.8em;"> <b>EVerest mailing list</b>
    </a>

.. |link_announcementlist| raw:: html

    <a href="https://lists.lfenergy.org/g/everest-announce" target="_blank">
        <img src="_static/icons/mail.svg" style="height: 0.8em;"> <b>EVerest announcement list</b>
    </a>

Another way to connect to the steadily growing EVerest community is the mailing
list.

We have set up two separate mailing lists:

1. The most important one is the announcement list. Important news or events
   all around EVerest are shared there. Subscribe here: |link_announcementlist|.
2. Optionally, you can subscribe to the detailed mailing list with all
   developer's exchange: |link_mailinglist|.

If you do not want to ask your questions in the Zulip chat, you can use the
detailed mailinglist to get your questions answered.

Weekly tech meetup and working groups
-------------------------------------

Since the beginning of 2024 we organize our community and development
exchange in the format of working groups.
The formerly called **weekly tech meetup** is now one of those working
groups. Now, we simply call it "General Working Group".

Those are all EVerest working groups:

- General (for general topics and to get a common ground for updates from the
  other working groups)
- Car Communication (car/charger communication with topics ISO 15118, EXI,
  SLAC, CHAdeMO etc)
- Cloud Communication (communication between charger and backends in cloud
  with topics OCPP 1.6, 2.0.1, 2.1 etc)
- EVerest Framework and Tools (framework topics and tools like edm, ev-cli
  etc)
- Testing and CI

You might wanna join us in the general working group to meet the community
without having focused on a special area of EVerest (yet).

For the General Working Group, meet us here each Tuesday at 4pm in CE(S)T
time-zone:

https://zoom-lfx.platform.linuxfoundation.org/meeting/92086494169?password=b2df6774-bc19-46f9-8c71-bbd13a0266a1

To see links to the meetings of all other working groups, see the publicly
available LFE EVerest calendar:

https://zoom-lfx.platform.linuxfoundation.org/meetings/everest

Additionally, you might want to join the working group chat channels in Zulip.
See the "Zulip chat" section above to see how to get there!

1:1 meetup
----------

If you do not want to start talking about your requirements and projects in
a big round, we can also give you the possibility to talk in a 1-on-1 meetup
with a community guide.

Just book a 30-minute meetup here:
https://calendly.com/manuel-ziegler-pionix/30min

.. hint::
    In this meetup, we will try to understand your dedicated requirements and
    see where in the EVerest ecosystem you can contribute or get support. If
    there is a need for technically deeper exchange, we can plan to set your
    topic on the agenda of the weekly tech meetup.

Tech resources about EVerest
============================

.. |link_github| raw:: html

  <a href="https://github.com/EVerest" target="_blank">
    <b>EVerest repositories on GitHub</b>
  </a>

.. |link_roadmap| raw:: html

    <a href="https://github.com/EVerest/EVerest/blob/main/tsc/ROADMAP.md" target="_blank">
      <b>roadmap on GitHub</b>
    </a>

.. |link_youtube| raw:: html

        <a href="https://www.youtube.com/@lfe_everest" target="_blank">
            <img src="_static/icons/youtube.svg" style="height: 0.8em"> <b>YouTube Channel</b>
        </a>

Find the source code, current Pull Requests and an issue tracking on our
home at |link_github|.

For getting at least a rough overview of the things we already implemented
and what is planned for the near future, see our |link_roadmap|.

With our |link_youtube| channel, you can stay up-to-date with webinars and get
insights from the Technical Steering Committee recordings.

And last but not least, also have a look at section
:ref:`FAQ And Best Practices <faq_main>` in this documentation
page to find topics that sometimes people get stuck with.

**************************************
Find Your Way Into EVerest Development
**************************************

If you want to choose video rather than text and code for a quick dive-in, **have a look at our webinar first**:

.. image:: /img/webinar-how-everest-ecosystem-simplifies-charging-use-cases-screenshot.png
  :alt: Screenshot of the webinar video How EVerest Ecosystem simplifies Charging Use Cases
  :target: https://www.youtube.com/watch?v=OJ6kjHRPkyY

Click for watching on YouTube: `Webinar: How the EVerest Ecosystem will simplify Charging Use Cases <https://www.youtube.com/watch?v=OJ6kjHRPkyY>`_

We prepared a path to get step by step into the EVerest world. It will lead you
from a high level overview right into understanding how to implement modules
for your dedicated hardware scenarios or developer use cases.

To walk this path, simply read on and follow the table of contents below.

*****************
Table Of Contents
*****************

But now let's dive in the EVerest journey to get you on board. Start on top
level with the first chapter and walk the path down to your first module
implementation.

.. toctree::
    :numbered:
    :maxdepth: 2
    :glob:

    general/01_framework/index
    general/02_detail_pre_setup/index
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
