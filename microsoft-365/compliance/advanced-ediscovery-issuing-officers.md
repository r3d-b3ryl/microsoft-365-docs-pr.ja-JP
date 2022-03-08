---
title: 発行担当者を管理Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 組織全体の発行担当者を Advanced eDiscoveryに追加して、組織内の任意の保管コミュニケーションに追加できます。
ms.openlocfilehash: 21c5a3db9cb0cfefb26bc75537f298c7e8a5c09a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63319338"
---
# <a name="manage-issuing-officers-in-advanced-ediscovery"></a>発行担当者を管理Advanced eDiscovery

自分または他のユーザーが、保管担当者であるユーザーに送信される保留通知または他の種類の通信を作成する場合は、発行担当者を指定する必要があります。 通知は、指定された発行担当者に代わって保管担当者に送信されます。 たとえば、組織内のパラリーガルが、ケースの保管担当者に保留通知を作成して送信する責任を負う場合があります。 このシナリオでは、paralegal は組織の弁護士を発行担当者として指定できます。 Who担当者として指定できますか? カストディアン通信の発行担当者として選択できるユーザーには、次の 2 種類があります。

- 通信が代理で送信される特定のケースのメンバー。

- 組織全体の発行担当者のリストに追加されたユーザー。 このリストのユーザーは、組織の任意のケースに発行担当者を追加できます。

この記事では、組織全体の発行担当者の一覧にユーザーを追加および削除する方法について説明します。

## <a name="before-you-add-an-issuing-officer"></a>発行担当者を追加する前に

- 発行担当者を追加または削除するには、組織内の電子情報開示管理者である必要があります。 詳細については、「電子情報開示アクセス[許可を割り当てる」を参照Microsoft 365 コンプライアンス センター](assign-ediscovery-permissions.md)  

- 発行担当者として追加されるユーザーは、組織にアクティブなメールボックスMicrosoft 365があります。

- 組織の発行担当者は最大 15 人です。 発行担当者として指定できるケースのメンバーは、この制限にカウントされません。 この制限は、組織の [発行担当者] ページに追加できるユーザーの数にのみAdvanced eDiscovery。

## <a name="add-an-issuing-officer"></a>発行担当者の追加

1. [設定] Microsoft 365 コンプライアンス センターに移動し、[[Advanced eDiscovery] を](https://go.microsoft.com/fwlink/p/?linkid=2173764)**クリックAdvanced eDiscoveryします**。

   ![[設定Advanced eDiscovery選択]](..\media\HistoricalVersions1.png)

2. [**発行設定**] ページで、[発行担当者] タブを選択して、[発行担当者の管理] **ページを表示** します。

   ![[発行担当者の設定] ページ。](..\media\AeDIssuingOfficers1.png)

3. [ **追加]** をクリックし、発行担当者の一覧に 1 人または複数のユーザーを検索して追加します。

ユーザーを発行担当者として追加すると、ユーザーまたは他のユーザーは、組織内のいかなる場合でも、カストディアン通信の発行担当者としてこれらのユーザーを指定できます。 カストディアン通信の作成の詳細については、「法的保留 [通知を作成する」を参照してください](create-hold-notification.md)。

## <a name="remove-an-issuing-officer"></a>発行担当者を削除する

1. [設定] Microsoft 365 コンプライアンス センターに移動し、[[Advanced eDiscovery] を](https://go.microsoft.com/fwlink/p/?linkid=2173764)**クリックAdvanced eDiscoveryします**。

2. [**発行設定**] ページで、[発行 **担当者] タブを選択** します。

3. 発行担当者リストで 1 人または複数のユーザーを選択し、[削除] をクリック **します**。

発行担当者の一覧からユーザーを削除した後、ユーザーが通信の発行元である特定のケースのメンバーである場合を限り、それらのユーザーを新しい保管担当者の通信で発行担当者として指定できなくなりました。 また、発行担当者を削除しても、ユーザーが発行担当者として削除される前に送信された通信には影響を与えかねない。
