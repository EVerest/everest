.. tutorial_citrineos:

.. _tutorial_citrineos_main:

##########################################
How To: OCPP 2.0 and CitrineOS
##########################################

This is a tutorial on how use `CitrineOS <https://citrineos.github.io/quickstart.html />`_ as the CSMS to run

    .. code block::
        
        everest-core/build/run-scripts/run-sil-ocpp201.sh

#. DevContainer Setup

    If you followed the `How to Mac <https://everest.github.io/nightly/tutorials/how_to_mac/index.html>`_ tutorial, you should have the EVerest already running inside VSCode DevContainer, and a Nodered Charging Station simulator running at http://localhost:1880/ui.

#. CitrineOS Setup

    From inside DevContainer:

    .. code block::

        git clone https://github.com/citrineos/citrineos-core
        docker-compose up -d

    Then visit localhost:8055 in your browser and use the default credentials:

    .. code block::

        username: admin@citrineos.com
        password: CitrineOS!
    
    Visit `this page <http://localhost:8055/admin/content/ChargingStations />`_
    to see a list of provisioned Charging Stations.

    .. image:: img/01_provisioned_cs.png
      :alt: List of Charging Stations provisioned in CitrineOS.
    
#. Configure SIL OCPP 2.0

    It's necessary to make the Charging Station Device Model match the info provisioned in the CitrineOS CSMS.
    The EVerest framework stores the Device Model in a sqlite3 database at:

    .. code block::
        everest-core/build/dist/share/everest/modules/OCPP201/device_model_storage.db 
        
    The easiest way to adjust the Device Model is through a VSCode sqlite3 extension, to edit the following
    Device Model records:

    .. code block::
        VARIABLE_ID: 3 (NetworkConnectionProfiles)
        Set ocppCsmsUrl inside column VALUE with the CitrineOS url
        Example: ws://localhost:8081/CHARGER01

    .. image:: 02_ocpp_csms_url.png
      :alt: OCPP CSMS URL in NetworkConnectionProfiles Variable

    .. code block::
        VARIABLE_ID: 121 (Identity) 
        Set the VALUE to a charger identifier
        Example: CHARGER01

    .. image:: 03_identity.png
      :alt: Identity Variable

    Finally start the SIL OCPP 2.0.1 simulation that connects to the CitrineOS CSMS:

    .. code block::
        everest-core/build/run-scripts/run-sil-ocpp201.sh

    .. image:: 04_run-sil-ocpp201.png
      :alt: List of Charging Stations provisioned in CitrineOS.