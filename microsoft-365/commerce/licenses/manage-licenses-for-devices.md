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
description: デバイスで使用するライセンスをグループに割り当てる方法について説明します。
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

教育機関 (デバイス) のMicrosoft 365 Apps for enterprise (デバイス) またはMicrosoft 365 Appsがある場合は、Azure AD グループを使用して、デバイスにライセンスを割り当てることができます。 デバイスにライセンスがある場合、そのデバイスを使用するすべてのユーザーがMicrosoft 365 Apps for enterpriseを使用できます (以前の名前Office 365 ProPlus)。 たとえば、組織内のユーザーが使用するノート PC とタブレットが 20 個あるとします。 各デバイスにライセンスを割り当てると、いずれかのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずにMicrosoft 365 Apps for enterpriseを使用します。

> [!IMPORTANT]
> Microsoft 365 Apps for enterpriseのデバイス ベースのライセンスは、一部の商用顧客および一部の教育機関のお客様向けのアドオン ライセンスとしてのみ使用できます。 商用顧客の場合、ライセンスは *Microsoft 365 Apps for enterprise (デバイス)* であり、Enterprise Agreement/Enterprise Agreement サブスクリプションでのみ使用できます。 教育機関のお客様の場合、このライセンスは *Education (デバイス) 用にMicrosoft 365 Apps* され、Education Solutions (EES) の登録でのみ使用できます。 詳細については、 [教育の可用性](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)に関するブログ投稿を参照してください。 商用の可用性については、Microsoft アカウント担当者にお問い合わせください。

まず、Azure Active Directory管理センターでグループを作成し、そのグループにデバイスを割り当てます。 デバイスの要件、使用できるグループの種類、デバイス ライセンスを使用するMicrosoft 365 Apps for enterpriseを構成する方法など、デバイス ライセンスの詳細については、「[Microsoft 365 Apps for enterpriseのデバイス ベースのライセンス」を](/deployoffice/device-based-licensing)参照してください。

> [!IMPORTANT]
> この記事のタスクを完了するには、グローバル管理者である必要があります。

## <a name="assign-licenses-to-devices"></a>デバイスにライセンスを割り当てる

グループにライセンスを割り当てると、グループ内のすべてのデバイスにライセンスが割り当てられます。 1 つのサブスクリプションを割り当てることができるのは、1 つのグループのみです。

1. Microsoft 365 管理センターで、<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  ページに移動します。
2. [**ライセンス**] ページで、**Education (デバイス) または Microsoft 365 Apps for enterprise (デバイス) の** Microsoft 365 Appsを選択 **します**。
3. 次のページでサブスクリプションを選択し、[ライセンスの **割り当て**] を選択します。
4. [ **グループにライセンスを割り当てる** ] ウィンドウで、グループ名の入力を開始し、結果から選択してリストに追加します。
5. **[割り当て]** を選択してから、**[閉じる]** を選択します。

## <a name="unassign-licenses-from-devices"></a>デバイスからライセンスを割り当て解除する

グループからライセンスの割り当てを解除すると、グループ内のすべてのデバイスからライセンスが削除されます。 その後、すべてのアプリとその関連データが読み取り専用になります。

1. 管理センターで、<a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">BillingLicenses</a>  >  ページに移動します。
2. [**ライセンス**] ページで、**Education (デバイス) または Microsoft 365 Apps for enterprise (デバイス) の** Microsoft 365 Appsを選択 **します**。
3. 次のページでサブスクリプションを選択し、3 つのドット (その他のアクション) を選択し、[ **ライセンスの割り当て解除**] を選択します。
4. [ **ライセンスの割り当て解除** ] ダイアログ ボックスで、[ **割り当て解除**] を選択します。
