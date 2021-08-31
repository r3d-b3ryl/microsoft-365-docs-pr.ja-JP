---
title: デバイスのライセンスを管理する
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: デバイスで使用するグループにライセンスを割り当てる方法について学習します。
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 08/27/2021
ms.openlocfilehash: b3d5e5cd3aa6c2531d515d665d10ad01298d0a23
ms.sourcegitcommit: 6a73f0f0c0360fc015d9c0d0af26fb6926d9477d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58747457"
---
# <a name="manage-licenses-for-devices"></a>デバイスのライセンスを管理する

Education (デバイス) Microsoft 365 Apps for enterprise (デバイス) または Microsoft 365 Appsがある場合は、Azure AD グループを使用してデバイスにライセンスを割りADできます。 デバイスにライセンスがある場合、そのデバイスを使用するユーザーは、Microsoft 365 Apps for enterpriseを使用Office 365 ProPlus。 たとえば、組織内のユーザーが使用する 20 台のノート PC とタブレットがあるとします。 各デバイスにライセンスを割り当てると、1 つのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずにMicrosoft 365 Apps for enterpriseを使用します。

> [!IMPORTANT]
> 一部の商用Microsoft 365 Apps for enterprise一部の教育顧客向けアドオン ライセンスとしてのみ利用できます。 商用のお客様の場合、ライセンスは Microsoft 365 Apps for enterprise *(デバイス)* であり、サブスクリプションのEnterprise Agreement/Enterprise Agreement利用できます。 教育のお客様の場合、ライセンスはMicrosoft 365 Apps (デバイス) であり、Education ソリューションの登録 *(EES)* を通じてのみ利用できます。 詳細については、教育の可用性に関するブログ投稿 [を参照してください](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)。 商用利用の場合は、Microsoft アカウント担当者にお問い合わせください。

まず、管理センターでグループをAzure Active Directoryし、そのグループにデバイスを割り当てる必要があります。 デバイスの要件、使用できるグループの種類、デバイス ライセンスを使用する Microsoft 365 Apps for enterprise を構成する方法など、デバイス ライセンスの詳細については、「Microsoft 365 Apps for enterprise のデバイス ベースのライセンス」[を参照してください](/deployoffice/device-based-licensing)。

> [!IMPORTANT]
> この記事のタスクを完了するには、グローバル管理者である必要があります。

## <a name="assign-licenses-to-devices"></a>デバイスへのライセンスの割り当て

グループにライセンスを割り当てると、グループ内のすべてのデバイスにライセンスが割り当てされます。 割り当て可能なサブスクリプションは、1 つのグループに 1 つのみです。

1. [請求Microsoft 365 管理センター] ページ **に**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">移動</a>します。
2. [ライセンス **] ページで**、[教育Microsoft 365 Apps **(デバイス)** または Microsoft 365 Apps for enterprise **(デバイス) を選択します**。
3. 次のページで、サブスクリプションを選択し、[ライセンスの割り当て **] を選択します**。
4. [グループに **ライセンスを割り当** てる] ウィンドウで、グループ名の入力を開始し、結果から選択してリストに追加します。
5. [割り **当て] を** 選択し、[閉じる] **を選択します**。

## <a name="unassign-licenses-from-devices"></a>デバイスからのライセンスの割り当てを解除する

グループからライセンスの割り当てを解除すると、グループ内のすべてのデバイスからライセンスを削除します。 その後、すべてのアプリとその関連データが読み取り専用です。

1. 管理センターで、[課金ライセンス]**ページ**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">に移動</a>します。
2. [ライセンス **] ページで**、[教育Microsoft 365 Apps **(デバイス)** または Microsoft 365 Apps for enterprise **(デバイス) を選択します**。
3. 次のページで、サブスクリプションを選択し、3 つのドット (その他のアクション) を選択し、[ライセンスの割り当て解除] **を選択します**。
4. [ライセンスの **割り当て解除] ダイアログ** ボックスで、[割り当 **て解除] を選択します**。
