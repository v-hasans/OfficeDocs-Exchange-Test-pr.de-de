﻿---
title: 'The Distributed Transaction Coordinator Service must be started before setup can continue_MSDTCStopped: Exchange 2013 Help'
TOCTitle: The Distributed Transaction Coordinator Service must be started before setup can continue_MSDTCStopped
ms:assetid: 96e33c94-348e-4a0b-9585-9bee81be4355
ms:mtpsurl: https://technet.microsoft.com/de-de/library/ms.exch.setupreadiness.msdtcstopped(v=EXCHG.150)
ms:contentKeyID: 50476270
ms.date: 04/24/2018
mtps_version: v=EXCHG.150
ms.translationtype: HT
---

# The Distributed Transaction Coordinator Service must be started before setup can continue\_MSDTCStopped

 

_**Gilt für:** Exchange Server_

_**Letztes Änderungsdatum des Themas:** 2012-06-05_

Der Inhalt dieses Themas wurde für Microsoft Exchange Server 2013 nicht aktualisiert. Dennoch kann er für Exchange 2013 gültig sein. Weitere Hilfe finden Sie in den Community-Ressourcen weiter unten.

Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie die Foren unter [Exchange Server](https://go.microsoft.com/fwlink/p/?linkid=60612), [Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=267542) oder [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkid=285351).

Microsoft Exchange Server 2007 setup cannot continue because its attempt to install the Client Access Server or Unified Messaging server roles failed because the Distributed Transaction Coordinator service is not started on the target computer.

Exchange 2007 setup requires the computer that you are installing Microsoft Exchange to have the Distributed Transaction Coordinator service status set to **Started**.

The Distributed Transaction Coordinator service provides services designed to ensure successful and complete transactions, even with system failures, process failures, and communication failures.

Each computer participating in a distributed transaction manages its own resources and data and also acts in concert with other computers in the transaction. Above all, a distributed transaction must commit or abort its work entirely on all participating computers. The Distributed Transaction Coordinator performs the transaction coordination role for the components involved and acts as a transaction manager for each computer that manages transactions.

Both the Client Access Server and Unified Messaging server roles have dependencies on the Distributed Transaction Coordinator service.

To resolve this issue, verify that the Distributed Transaction Coordinator service status is set to **Started** on the local computer, and then rerun Microsoft Exchange setup.

**To set the status of the Distributed Transaction Coordinator service to 'Started'**

1.  Right-click **My Computer**, and then click **Manage**.

2.  Expand the **Services and Applications** node, and then click the **Services** node.

3.  In the right pane, locate the **Distributed Transaction Coordinator**.

4.  Right-click **Distributed Transaction Coordinator**, and then click **Properties**.

5.  Set the **Startup Type** to **Automatic** and the **Service status** to **Started**.

6.  Click **Apply**, and then click **OK**.

