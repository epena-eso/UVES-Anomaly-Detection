
UVES, Anomaly Detection

Table of Contents

    Project name and goals
    Deliverables
    Timeline/duration
    Team
    Risks
    Related documents
    Project status
        2019-04-22
        2019-05-08
            Summary:
            AI:
            Next meeting:
        2019-05-16
            Summary of the discussed items:
            AI:
            Next meeting: May 30th 10:00 ESO premises.

Project name and goals

Length: 3 months

Start: May 1.

The progress of this project is followed in the OneDrive document found here. The one drive document is the master document for the project's progress, and this wiki page "merely" a summary.
Deliverables

    "Black Box algorithm" for anomaly detection in UVES biases, flats and arcs.
    Obtain an assessment of the applicability to other instrument data
    Implement ML in the quality control part of operations

Timeline/duration
Team

    Nicolas Haddad (ESO) - UVES instrument responsible
    Eduardo Pena (ESO) - Software specialist AI
    Luca Sbordone (ESO) - UVES instrument scientist
    Willem-Jan de Wit (ESO) - SciOps quality something
    Roberto Munoz (MetricArts)
    Joaquin Prieto (MetricArts)

Risks
Related documents
Project status
2019-04-22

    Internal meeting between NHA, LSB, and WDW on the data to be given to MetricArts.

2019-05-08
Summary:

    Meeting at ESO with Metricarts and EPe, NHa, LSb, WdW. Goal: data delivery and explanation on the data.
    One year of bias/arcs/flats delivered.
    Deep learning and clustering approach will be the start by M.A.
    Allow access to usher.com

AI:

    MetricArts/EPe: inform of technical information and costs of using the Clout
    LSB: data - identify keywords and extract keyword values that uniquely describe each file
    LSB: data - label faulty data
    EPE: Create whatapp group for quick communiction.

Next meeting:

    16-5, 09:30 ESO premises.

2019-05-16

    Progress meeting.

    Present: EPe, NHa, LSb, WdW, RMu (MetricArts), Joaquin ? (MetricArts)

    Start: ~10:30

Summary of the discussed items:

    Computing power "Architecture": A Virtual Machine (VM) on the Azure server for all data products (Azure Blob or Datalake) and an 'elastic' Jupyter (virtual) server on Azure for the "real" training and data visualization. [Elastic means that a VM can change size in cores and RAM]. The VM is replicated to the PARANAL gluster. This depends on the size of the data.
    Notebooks developed on the Jupyter VM will be stored on Github (MicroSoft) under configuration control (and shared).
    For the bias analysis the "Hotdog approach" is probably the most convenient, i.e. train the machine what is a good hotdog (bias frame) and all images that do not correspond to a hotdog ... are not hotdogs (biases).
    Images: for testing the ML-blackbox: Add a synthetic signal. For unsupervised ML the number of bad UVES images is too low. "Auto-encoder" DL as an image reduction to its essence combined with a comparative network.
    A note on possible futher QC implementation: instrument generated "bad images". A template that moves various functions in an "unforeseen" way in order to create a database of bad images which will be added to an image DB to teach the model.
    Image normalization: how to normalize the images when you have hot pixels, CR hits? Does one pre-process and remove before learning or can the machine learn this? In ML practice, there is a set of operational parameters which define what are the acceptable pixel values. On the other hand, hot pixels themselves have been seen as used as a reference by the learning process (EPe).
    NB: Each of the UVES images has an overscan region, which are always there and there is probably no need to take them out.
    The total size of the data delivered by Garching is not clear. This is important for the type of cloud storage and the cost.

AI:

    deliver for the 10 year data delivery coming from Garching Isabelle P.
    MA: set up the VM / jupyter server / datalake /
    WdW: to make two copies of the disk one copy to Paranal one copy to MA.

Next meeting: May 30th 10:00 ESO premises.
