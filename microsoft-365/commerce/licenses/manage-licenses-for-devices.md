---
title: デバイスのライセンスを管理する
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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: ce3c8f7d669f2fe5d19c48d7a1fb1f224aaec7f4
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402872"
---
# <a name="manage-licenses-for-devices"></a>デバイスのライセンスを管理する

Microsoft 365 for enterprise (デバイス) または Microsoft 365 Apps for エデュケーション (デバイス) を使用している場合は、Azure AD グループを使用して、デバイスにライセンスを割り当てることができます。 デバイスにライセンスがある場合、そのデバイスを使用するすべてのユーザーは、エンタープライズ向けの Microsoft 365 Apps (以前の Office 365 ProPlus) を使用できます。 たとえば、組織内のユーザーによって使用される20個のラップトップおよびタブレットがあるとします。 各デバイスにライセンスを割り当てると、いずれかのデバイスにログインする各ユーザーは、独自のライセンスを必要とせずにエンタープライズ向けの Microsoft 365 アプリを使用します。

> [!IMPORTANT]
> Microsoft 365 用アプリのデバイスベースライセンスは、市販のお客様や教育機関のお客様のためのアドオンライセンスとしてのみ利用できます。 商用のお客様の場合、ライセンスは*Microsoft 365 enterprise 用アプリ (デバイス)* で、エンタープライズアグリーメント/エンタープライズアグリーメントのサブスクリプションを通じてのみ利用可能です。 教育機関のお客様の場合、ライセンスは*Microsoft 365 の教育機関向けアプリ (デバイス)* で、教育機関向けの登録 (EES) によってのみ利用できます。 詳細については、「教育の[利用可能性](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)」のブログ投稿を参照してください。 市販の可用性については、Microsoft アカウント担当者にお問い合わせください。

最初に、Azure Active Directory 管理センターでグループを作成し、そのグループにデバイスを割り当てます。 デバイスライセンスの詳細については、デバイスの要件、使用できるグループの種類、およびデバイスライセンスを使用するように Microsoft 365 Apps for enterprise を構成する方法について説明します。「 [microsoft 365 アプリ用のデバイスベースライセンス](https://go.microsoft.com/fwlink/p/?linkid=2094216)」を参照してください。

> [!IMPORTANT]
> この記事のタスクを完了するには、グローバル管理者である必要があります。

## <a name="assign-licenses-to-devices"></a>デバイスへのライセンスの割り当て

グループにライセンスを割り当てるときは、グループ内のすべてのデバイスにライセンスを割り当てます。 1つのグループに割り当てることができるサブスクリプションは1つだけです。

1. Microsoft 365 管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。
2. [**ライセンス**] ページで、[ **microsoft 365 apps for エデュケーション (デバイス)** ] または [ **microsoft 365 apps for enterprise (デバイス)**] を選択します。
3. 次のページでサブスクリプションを選択し、[**ライセンスの割り当て**] を選択します。
4. [**グループへのライセンスの割り当て**] ウィンドウで、グループ名の入力を開始し、結果からそれを選択して一覧に追加します。
5. [**割り当て**] を選択し、[**閉じる**] を選択します。

## <a name="unassign-licenses-from-devices"></a>デバイスからライセンスを割り当て解除する

グループからライセンスを割り当てを解除するときは、グループ内のすべてのデバイスからライセンスを削除します。 すべてのアプリとそれに関連付けられたデータは、読み取り専用になります。

1. 管理センターで、[**課金**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">ライセンス</a>] ページに移動します。
2. [**ライセンス**] ページで、[ **microsoft 365 apps for エデュケーション (デバイス)** ] または [ **microsoft 365 apps for enterprise (デバイス)**] を選択します。
3. 次のページで、サブスクリプションを選択し、[**その他のアクション**] を選択して、[**ライセンスの割り当て解除**] を選択します。
4. [**ライセンスの割り当ての解除**] ダイアログボックスで、[**割り当て**の解除] を選択します。