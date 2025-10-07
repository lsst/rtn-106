#####################################
First alerts end-to-end demonstration
#####################################

.. abstract::

   A roadmap for the end-to-end science demonstration of the LSST alert distribution and follow-up ecosystem, to be executed with the first alerts as part of the early science program.


Introduction
============

This is a living document that will evolve as the plans for the alert end-to-end demo evolves.


Goals
=====

To use Rubin data to test and demonstrate the functionality and science-readiness of individual components of the automated alert follow-up ecosystem.

The target audience of this demo is both the science community and the general public.


Timeline
========

After the Rubin Observatory shutdown, and once all prerequisite conditions are met, the alerts end-to-end demo will proceed.


Shutdown dates
--------------

These dates are subject to change by the respective observatories.

* Sep 22 - Oct 20: Rubin Observatory shutdown
* Oct 3 - Nov 24: SOAR shutdown
* Oct 13 - Nov 7: Gemini N shutdown


Prerequisites
-------------

The conditions under which the first alerts end-to-end demo can occur are:

* agency security review complete (done)
* all observatories are on-sky
* all components are online
* compatible fields are scheduled for observations
* draft EPO announcements are prepared
* humans are available


The demo
--------

The following sequence of events might run in one night for one or more science targets, or over a few nights.

1. Image acquisition: observations are acquired at Rubin Observatory.

2. Alert production: Rubin DIA and AP pipelines run, distrubting alerts to brokers.

3. ANTARES: a science filter identifies targets of interest for this end-to-end demo.

4. GOATS: queries and retrieves the targets of interest, down-selects, and triggers AEON.

5. AEON: recieves follow-up trigger request from GOATS and executes observations with SOAR, Gemini, or Las Cumbres Observatories.

6. GOATS: recieves and processes the follow-up observations, and runs, e.g., spectral classification.

7. Hermes: results are shared with the science community.

8. Press: announcement from EPO/Comms teams goes out via the usual channels.




Targets
=======

Potential science use cases and targets for the end-to-end demo, and relevant considerations for each.

The most effective science use case will be one that is common (high probability of finding one) and for which same-night follow-up can yield a classification.


Supernovae
----------

Any extragalactic field (i.e., high Galactic latitude) should yield several SN candidates.

ANTARES already has filters that can identify SN candidates.

GOATS/AEON could schedule follow-up spectra for several candidates, and it's likely at least one could be classified (e.g., Type I, II, and sub-type).

In the SN field, classifications are regularly shared by time-domain surveys, and reported to the `Transient Name Server <https://www.wis-tns.org/>`_ to obtain an IAU designation.


Variable star
-------------

Similar case as supernovae, but for Galactic fields.

For example, M-dwarf flares are pretty common, and this might work ok for press, but the scientific community might not be impressed.


Tidal Disruption Event (TDE)
----------------------------

TDEs are nuclear transients, good candidates are in host galaxies with no AGN.

They are new and popular in astronomy, and they are good for EPO because they are black holes.

They are more rare in galaxy cores than supernovae, but if we aim for a TDE but end with a supernova, that would be fine.

Microlensing event
------------------

As with variable stars, could be discovered in a Galactic field, but typically the follow-up is rapid-candence photometry not a single spectrum.


Solar system object
-------------------

ANTARES does not currently have filters for moving objects, and instead passes them on to the SNAPS broker.
This might be a too-challenging case for automatic follow-up, for this demo.

A known moving object that changes in brightness could potentially be automatically identified,
but confirmation of cometary activity (e.g., outgassing) might require too long a follow-up timescale.

A new moving object (such as an NEO) would be unlikely on any given single night.


Components
==========

Brief descriptions and links to documentation for each of the components that are being incorporated into this alerts end-to-end demo.


Rubin EPO and Comms
-------------------

EPO: Education and Public Outreach

Comms: Communications team

The Rubin EPO and Communications teams will bring this demo to the public with graphcs and press articles.

Contacts: Gaëlle Suter, Kristen Metzger, Stephanie Deppe


Rubin DIA and AP
----------------

DIA: Difference Image Analysis

AP: Alert Production

`LSST Science Pipelines documentation <https://pipelines.lsst.io/>`_

DIA refers to the process of image subtraction and difference-image source detection.
AP refers to the production and distribution of alert packets for difference-image sources.
This software is run by Rubin Data Management as part of Prompt Processing.

Contact: Eric Bellm


ANTARES
-------

ANTARES: Arizona–NOIRLab Temporal Analysis and Response to Events System

`ANTARES broker <https://antares.noirlab.edu/>`_

ANTARES is a full-service, real-time broker that adds contextual value to ingested alerts from multiwavelength astronomical catalogs.
Users can write their own filters to identify specific classes of objects, create watch lists for direct notification, or develop catalogs for large-scale comparisons. 
Users can interact with the system via a web portal, API, or substreams of alerts from filters.

Contact: Tom Matheson


GOATS
-----

GOATS: Gemini Observation and Analysis of Targets System

`GOATS documentation <https://goats.readthedocs.io/en/latest/>`_

GOATS is a browser-based user interface providing end-to-end automation of the entire time-domain/multi-messenger astronomy follow-up process, including target selection, triggering follow-up observations, and data reduction and analysis.
It was built using the `TOM Toolkit`.
The DRAGONS software is already integrated into GOATS.

Contact: Monika Soraisam


AEON
----

AEON: Astronomical Event Observatory Network

`AEON documentation <https://aeonplus.github.io/>`_

AEON provides rapid, flexible, programmable access to multi-wavelength telescope facilities such as SOAR and Gemini.
Alert brokers and Target Observation Managers (TOMs) can submit follow-up observations in real-time without human intervention with AEON.

Contact: César Briceño


Las Cumbres
-----------

`Las Cumbres Observatory <https://lco.global/>`_

Las Cumbres is comprised of many robotic telescopes around the world, functioning as a single facility.
Observations can be automatically triggered with AEON.

Contact: Rachel Street


TOM Toolkit
^^^^^^^^^^^

TOM: Target Observation Manager

`TOM Toolkit documentation <https://tom-toolkit.readthedocs.io/en/stable/>`_

Software infrastructure developed by Las Cumbres that enables anyone to build and customize a TOM for their particular science goals.
Includes software to interface with ANTARES and AEON.

Contact: Rachel Street


Hermes
^^^^^^

`Hermes documentation <https://hermes.lco.global/about>`_

HERMES is a Message Exchange Service for Multi-Messenger Astronomy applications that allow users to both send and review messages related to a variety of events and targets of interest as well as understand opportunities for follow-up.

Contact: Rachel Street


SOAR
----

SOAR: Southern Astrophysical Research Telescope

`SOAR telescope <https://noirlab.edu/science/programs/ctio/telescopes/soar-telescope>`_

SOAR is a 4m telescope in Chile (Cerro Pachón), offers target-of-opportunity observations for time domain follow-up, and interfaces with AEON.

Contact: César Briceño


Gemini
------

`Gemini Observatory <https://www.gemini.edu/>`_

Gemini Observatory, 8m twin telescopes in Chile (Cerro Pachón) and Hawaii, offers target-of-opportunity observations for time domain follow-up, and interfaces with AEON.
The Gemini Multi-Object Spectrograph (GMOS) is particularly common for transient spectroscopy.

Contact: Bryan Miller


DRAGONS
^^^^^^^

DRAGONS: Data Reduction for Astronomy from Gemini Observatory North and South

`DRAGONS documentation <https://dragons.readthedocs.io/>`_

Software infrastructure for automated processing of imaging and spectroscopic data from Gemini Observatory, including GMOS longslit spectra (but can be extended to other facilities).

Contact: Bryan Miller


GPP
^^^

GPP: Gemini Program Platform

`GPP XT1 Early Science Call <https://www.gemini.edu/observing/phase-i-proposing-time/gpp-xt1>`_

Gemini Observatory's new web-based platform for proposals and observation preparation, with AEON compatibility.

Contact: Bryan Miller



