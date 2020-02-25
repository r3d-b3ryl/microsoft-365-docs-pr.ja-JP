---
title: 「デバイスのライセンスを管理する」
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: デバイスで使用するためにライセンスをグループに割り当てる方法について説明します。
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242322"
---
# <a name="manage-licenses-for-devices"></a>「デバイスのライセンスを管理する」

Office 365 ProPlus for 教育 (デバイス) を使用している場合は、Azure AD グループを使用して、デバイスにライセンスを割り当てることができます。 デバイスにライセンスがある場合は、そのデバイスを使用するすべてのユーザーが Office 365 を使用できます。 たとえば、組織内のユーザーによって使用される20個のラップトップおよびタブレットがあるとします。 各デバイスにライセンスを割り当てると、デバイスのいずれかにログインする各ユーザーは、自分のライセンスを必要とせずに Office 365 を使用します。

> [!IMPORTANT]
> Office 365 ProPlus (デバイス) は、教育用の A3 および A5 ボリュームライセンスのお客様のみが利用できます。

最初に、Azure Active Directory 管理センターでグループを作成し、そのグループにデバイスを割り当てます。 デバイスの要件、使用できるグループの種類、Office 365 ProPlus を使用してデバイスライセンスを使用するように構成する方法など、デバイスのライセンスの詳細については、「 [device licensing For office 365 ProPlus For 教育のお客様](https://go.microsoft.com/fwlink/p/?linkid=2094216)」を参照してください。

> [!IMPORTANT]
> この記事のタスクを完了するには、グローバル管理者である必要があります。

## <a name="assign-licenses-to-devices"></a>デバイスへのライセンスの割り当て

グループにライセンスを割り当てるときは、グループ内のすべてのデバイスにライセンスを割り当てます。 1つのグループに割り当てることができるサブスクリプションは1つだけです。

1. Microsoft 365 管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。
2. [**ライセンス**] ページで、[ **Office 365 ProPlus for 教育 (デバイス)**] を選択します。
3. [ **Office 365 ProPlus (デバイス)** ] ページで、サブスクリプションを選択し、[**ライセンスの割り当て**] を選択します。
4. [**グループへのライセンスの割り当て**] ウィンドウで、グループ名の入力を開始し、結果からそれを選択して一覧に追加します。
6. [**割り当て**] を選択し、[**閉じる**] を選択します。

## <a name="unassign-licenses-from-devices"></a>デバイスからライセンスを割り当て解除する

グループからライセンスを割り当てを解除するときは、グループ内のすべてのデバイスからライセンスを削除します。 すべてのアプリとそれに関連付けられたデータは、読み取り専用になります。

1. 管理センターで、[**課金** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。
2. [**ライセンス**] ページで、[ **Office 365 ProPlus for 教育 (デバイス)**] を選択します。
3. [ **Office 365 ProPlus (デバイス)** ] ページで、サブスクリプションを選択し、[**その他のアクション**] を選択して、[**ライセンスの割り当て解除**] を選択します。
5. [**ライセンスの割り当ての解除**] ダイアログボックスで、[**割り当て**の解除] を選択します。