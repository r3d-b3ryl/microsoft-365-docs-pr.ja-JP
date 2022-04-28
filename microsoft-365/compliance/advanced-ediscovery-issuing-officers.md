---
title: 電子情報開示で発行担当者を管理する (プレミアム)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
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
description: 組織全体の発行担当者を電子情報開示 (プレミアム) に追加して、組織内の任意のケースで任意の親権通信に追加できます。
ms.openlocfilehash: 894da37088599d1c8b0f9d473bf64311a09cc566
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093638"
---
# <a name="manage-issuing-officers-in-ediscovery-premium"></a>電子情報開示で発行担当者を管理する (プレミアム)

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

自分または他のユーザーが、ケースで保管担当者であるユーザーに送信される保留通知またはその他の種類の通信を作成する場合は、発行元の担当者を指定する必要があります。 通知は、指定された発行元の担当者に代わってカストディアンに送信されます。 たとえば、組織内の paralegal が、ケース内で保管担当者に保留通知を作成して送信する役割を担う場合があります。 このシナリオでは、paralegal は組織内の弁護士を発行責任者として指定できます。 Whoは発行元の担当者として指定できますか? カストディアン通信の発行元担当者として選択できるユーザーには、次の 2 種類があります。

- 通信の代理として送信される特定のケースのメンバー。

- 組織全体の発行担当者の一覧に追加されたすべてのユーザー。 この一覧のユーザーは、組織内の任意のケースに発行元担当者を追加できます。

この記事では、組織全体の発行担当者の一覧にユーザーを追加および削除する方法について説明します。

## <a name="before-you-add-an-issuing-officer"></a>発行元担当者を追加する前に

- 発行担当者を追加または削除するには、組織内の電子情報開示管理者である必要があります。 詳細については、[Microsoft Purview コンプライアンス ポータルの電子情報開示アクセス許可の割り当てに関するページを参照](assign-ediscovery-permissions.md)してください。  

- 発行元担当者として追加されたユーザーは、Microsoft 365組織内にアクティブなメールボックスを持っている必要があります。

- 組織には、最大 15 人の発行担当者を含めることができます。 発行元の担当者として指定できるケースのメンバーは、この制限にカウントされません。 この制限は、電子情報開示 (プレミアム) の **[発行元担当者**] ページに追加できるユーザーの数にのみ適用されます。

## <a name="add-an-issuing-officer"></a>発行元担当者を追加する

1. コンプライアンス ポータルで、[電子情報開示 (プレミアム)](https://go.microsoft.com/fwlink/p/?linkid=2173764) に移動し、**電子情報開示 (プレミアム) 設定** をクリックします。

   ![電子情報開示 (プレミアム) 設定を選択する](..\media\HistoricalVersions1.png)

2. **設定** ページで、[**発行担当者**] タブを選択して、[**発行担当者の管理**] ページを表示します。

   ![[発行元の担当者の設定] ページ。](..\media\AeDIssuingOfficers1.png)

3. [ **追加]** をクリックし、1 人以上のユーザーを検索して、発行担当者の一覧に追加します。

発行元の担当者としてユーザーを追加した後、自分または他のユーザーは、組織内のいずれの場合でも、これらのユーザーをカストディアン通信の発行元担当者として指定できるようになります。 カストディアン通信の作成の詳細については、「 [訴訟ホールド通知を作成する」を](create-hold-notification.md)参照してください。

## <a name="remove-an-issuing-officer"></a>発行元の担当者を削除する

1. コンプライアンス ポータルで、[電子情報開示 (プレミアム)](https://go.microsoft.com/fwlink/p/?linkid=2173764) に移動し、**電子情報開示 (プレミアム) 設定** をクリックします。

2. **設定** ページで、[**発行元担当者**] タブを選択します。

3. 発行元の担当者の一覧で 1 人以上のユーザーを選択し、[ **削除**] をクリックします。

発行元の担当者の一覧からユーザーを削除した後、ユーザーが特定のケースの通信の発行元である場合を除き、それらのユーザーを新しいカストディアン通信の発行元担当者として指定できなくなります。 また、発行元の担当者を削除しても、ユーザーが発行元担当者として削除される前に送信された通信には影響しません。
