---
title: デバイスのライセンスを管理する
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: shegu, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
description: デバイスで使用するグループにライセンスを割り当てる方法について学習します。
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
- okr_SMB
search.appverid: MET150
ms.date: 08/27/2021
ms.openlocfilehash: fd452cb52a1c65a59e478fb80438ac95a57e8bf6
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311789"
---
# <a name="manage-licenses-for-devices"></a>デバイスのライセンスを管理する

Education (デバイス) Microsoft 365 Apps for enterprise (デバイス) または Microsoft 365 Appsがある場合は、ユーザーグループを使用してデバイスにライセンスAzure ADできます。 デバイスにライセンスがある場合、そのデバイスを使用するユーザーは、Microsoft 365 Apps for enterprise (以前の名前Office 365 ProPlus)。 たとえば、組織内のユーザーが使用する 20 台のノート PC とタブレットがあるとします。 各デバイスにライセンスを割り当てると、1 つのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずにMicrosoft 365 Apps for enterpriseを使用します。

> [!IMPORTANT]
> 一部の商用Microsoft 365 Apps for enterprise一部の教育顧客向けアドオン ライセンスとしてのみ利用できます。 商用のお客様の場合、ライセンスは Microsoft 365 Apps for enterprise *(デバイス)* であり、サブスクリプションのEnterprise Agreement/Enterprise Agreement利用できます。 教育のお客様の場合、ライセンスはMicrosoft 365 Apps *(デバイス)* であり、Education ソリューションの登録 (EES) を通じてのみ利用できます。 詳細については、教育の可用性に関するブログ投稿 [を参照してください](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)。 商用利用の場合は、Microsoft アカウント担当者にお問い合わせください。

まず、管理センターでグループをAzure Active Directoryし、そのグループにデバイスを割り当てる必要があります。 デバイスの要件、使用できるグループの種類、デバイス ライセンスを使用する Microsoft 365 Apps for enterprise を構成する方法など、デバイス ライセンスの詳細については、「Microsoft 365 Apps for enterprise のデバイス ベースのライセンス」[を参照してください](/deployoffice/device-based-licensing)。

> [!IMPORTANT]
> この記事のタスクを完了するには、グローバル管理者である必要があります。

## <a name="assign-licenses-to-devices"></a>デバイスへのライセンスの割り当て

グループにライセンスを割り当てると、グループ内のすべてのデバイスにライセンスが割り当てされます。 割り当て可能なサブスクリプションは、1 つのグループに 1 つのみです。

1. [アカウント] Microsoft 365 管理センター[**BillingLicenses** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">] ページに移動</a>します。
2. [ライセンス **] ページで**、[教育 **Microsoft 365 Apps ( デバイス)** または [Microsoft 365 Apps for enterprise **] (デバイス) を選択します**。
3. 次のページで、サブスクリプションを選択し、[ライセンスの割り当て **] を選択します**。
4. [グループに **ライセンスを割り当** てる] ウィンドウで、グループ名の入力を開始し、結果から選択してリストに追加します。
5. **[割り当て]** を選択してから、**[閉じる]** を選択します。

## <a name="unassign-licenses-from-devices"></a>デバイスからのライセンスの割り当てを解除する

グループからライセンスの割り当てを解除すると、グループ内のすべてのデバイスからライセンスを削除します。 その後、すべてのアプリとその関連データが読み取り専用です。

1. 管理センターで、[<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a> > ] ページに移動します。
2. [ライセンス **] ページで**、[教育 **Microsoft 365 Apps ( デバイス)** または [Microsoft 365 Apps for enterprise **] (デバイス) を選択します**。
3. 次のページで、サブスクリプションを選択し、3 つのドット (その他のアクション) を選択し、[ライセンスの割り当て解除 **] を選択します**。
4. [ライセンスの **割り当て解除] ダイアログ** ボックスで、[割り当 **て解除] を選択します**。
