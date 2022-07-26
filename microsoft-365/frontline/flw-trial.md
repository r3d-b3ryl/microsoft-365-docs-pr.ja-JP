---
title: Teams でフロントライン試用版を管理する
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: 組織のデスクフリー ワーカー向けの 90 日間の Teams 試用版を設定する方法について説明します。
ms.localizationpriority: high
ms.collection:
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 311d0a5b1204f022a993bbef24ea4bc1edda324c
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66994849"
---
# <a name="manage-the-frontline-trial-in-teams"></a>Teams でフロントライン試用版を管理する

> [!NOTE]
> この試用版のエクスペリエンスは近日公開予定です。 Microsoft 365 管理センターの[メッセージ センター](https://go.microsoft.com/fwlink/p/?linkid=2070717)でメッセージを探すことで、組織がいつこれを利用できるようになるかを確認できます。

Microsoft Teams フロントライン試用版エクスペリエンスでは、Teams にいる組織内のユーザーは、他のメンバーが Azure Active Directory (Azure AD) にいる限り、デスクフリー ワーカーチーム全体の Teams エクスペリエンスを開始できます。 [AllowSelfServicePurchase PowerShell モジュール](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)を使用して、組織内のユーザーに対してこの機能を無効にすることができます。

## <a name="what-services-are-included"></a>含まれるサービス

試用版には、次の例外を除き [Microsoft 365 F3 ライセンス](https://www.microsoft.com/microsoft-365/enterprise/f3)に含まれるものがすべて含まれています。

- フロントライン試用版には、Exchange キオスクではなく Exchange Foundation が含まれています。 この変更により、他の Teams 機能がユーザーに不足している可能性があります。

## <a name="eligibility"></a>対象

> [!NOTE]
> 組織が試用版パイロットの一部であるかどうかを確認するには、Microsoft 365 管理センターの[メッセージ センター](https://go.microsoft.com/fwlink/p/?linkid=2070717)でお知らせを探します。 ユーザーが試用版を開始または参加するには、組織が試用版パイロットに参加している必要があります。 このプランは、GCC、GCC High、DoD、EDU のお客様はご利用いただけません。

フロントライン試用版は、試用版あたり最大 300 人のユーザーに対応できます。

ユーザーは、次の場合にチームのフロントライン試用版を開始できます:

- Teams へのアクセス権を付与するアクティブなライセンスを持っている。
- デスクフリー ワーカー試用版をまだ開始していない。

> [!IMPORTANT]
> 試用版が終了する前に試用版を開始したユーザーが組織を離れた場合、管理者は試用版を監視し、チームにチェックインして、これらの機能の恩恵を受けているユーザーを確認し、有料ライセンスにアップグレードする必要があるユーザーを決定する必要があります。

ユーザーは、マネージド Azure Active Directory ドメインのメール アドレスを持っている場合、デスクフリー ワーカー試用版に参加できます。

ユーザーは、以前に試用版を開始したが、別の試用版を開始できない場合は参加できます。

> [!NOTE]
> Teams に既存のアクセス権を持たないユーザーは、チームの作成時にのみ試用版チームに追加できます。 チームの作成後も、既存の Teams ユーザーを試用版に追加できます。

## <a name="set-up-the-trial"></a>試用版を設定する

対象ユーザーは、デスクトップアプリまたは [Web アプリ](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks)から Teams のタスク アプリにサインインすることで、フロントライン試用版を開始できます。 現時点では、モバイル経由でのフロントライン試用版の開始はサポートされていません。 試用版が開始されると、チーム全体にフロントライン試用版ライセンスが自動的に割り当てられます。 Teams にアクセスできる既存の有料ライセンスを持つユーザーには、試用版ライセンスも割り当てられますが、試用版全体を通じて既存のライセンスの機能を維持し、試用版の終了後も既存の有料ライセンスを保持します。 試用版を開始したユーザーは、試用版の途中でメール通知を受け取ります。

## <a name="manage-the-frontline-trials-experience"></a>最前線のフロントライン試用版エクスペリエンスを管理する

管理者は、**AllowSelfServicePurchase** PowerShell モジュールを使用して、エンド ユーザーが組織内でフロントライン試用版を開始できないようにすることができます。 これは試用版ライセンス専用です。 [AllowSelfServicePurchase PowerShell モジュールを使用する方法について説明します](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)。

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>フロントライン試用版ライセンスを持つユーザーの Teams を管理する

通常の有料ライセンスを持つユーザーを管理する場合と同様に、フロントライン試用版ライセンスを持つユーザーを管理できます。 詳細については、「[組織の Teams 設定を管理する](/microsoftteams/manage-teams-overview)」を参照してください。

### <a name="remove-a-trial-license"></a>試用版ライセンスを削除する

PowerShell またはMicrosoft 365 管理センターを使用して、フロントライン試用版ライセンスを削除できます。

[PowerShell を使用して削除する方法について説明します](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)。

[管理センターで削除する方法について説明します](/microsoft-365/admin/add-users/delete-a-user)。

## <a name="upgrade-users-from-frontline-trial"></a>フロントライン試用版からユーザーをアップグレードする

ユーザーは、試用期間が終了したときにライセンスを要求するようにユーザーから連絡を受ける場合があります。 ユーザーをアップグレードするには、管理者特権が必要です。

### <a name="when-to-upgrade"></a>アップグレードするタイミング

90 日間の試用版の終了間近に、有料ライセンスを継続する必要があるユーザーを、ユーザーに共に確認する必要があります。 フロントライン試用版サブスクリプションの有効期限が切れる前に、ユーザーのエクスペリエンスが中断されないようにしてください。

> [!IMPORTANT]
> フロントライン試用版ライセンスが終了し、ユーザーに Teams を含むライセンスが直ちに割り当てられていない場合は、Teams にアクセスできなくなります。 30 日後、データ (ファイル、メッセージなど) が削除されます。 ユーザーは引き続き Azure Active Directory に残ります。 30 日以内に Teams 機能を有効にするために新しいライセンスがユーザーに割り当てられれば、Teams 内のすべてのコンテンツが残されます。

### <a name="choose-an-upgrade-path"></a>アップグレード パスを選択する

> [!TIP]
> フロントライン試用版は、[Microsoft 365 F3 ライセンス](https://www.microsoft.com/microsoft-365/enterprise/f3)に基づいています。

組織が現在持っているサブスクリプションに応じて、フロントライン試用版から有料ライセンスにアップグレードするには、次の 3 つの方法があります。

- **既存の Microsoft 365 サブスクリプションをアップグレードします。** 組織に Teams を含まない他の Office 製品のサブスクリプションがある場合は、このオプションを使用します。 詳細については、「[別のプランにアップグレードする](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan)」を参照してください。 既存のサブスクリプションのアクティブなユーザーを表示するには、Microsoft 365 管理センターの **[ユーザー] >** [[アクティブなユーザー]](https://go.microsoft.com/fwlink/p/?linkid=834822) に移動します。

- **既存の Microsoft 365 サブスクリプションを追加します。** 組織に、デスクフリー ワーカー チームをカバーするのに十分な有料 Teams ライセンスがない場合は、このオプションを使用してください。 詳細については、「[ライセンスの購入/削除](/microsoft-365/commerce/licenses/buy-licenses)」をご覧ください。 すでに十分な使用可能なライセンスがある既存のサブスクリプションにユーザーを追加するには、「[ユーザーを別のサブスクリプションに移動する](/microsoft-365/commerce/subscriptions/move-users-different-subscription)」を参照してください。 既存のサブスクリプションのアクティブなユーザーを表示するには、Microsoft 365 管理センターの **[ユーザー] >** [[アクティブなユーザー]](https://go.microsoft.com/fwlink/p/?linkid=834822) に移動します。

- **新しい Microsoft 365 サブスクリプションを購入する** 組織に Office 製品の既存のサブスクリプションがない場合、または組織がTeams Exploratory ユーザーを対象とするために既存のサブスクリプションとは異なるサブスクリプションを購入したい場合は、このオプションを使用してください。 詳細については、「[デスクフリー ワーカー向け Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/frontline)」を参照してください。

どの Microsoft 365 サブスクリプションにアップグレードすればいいかがわからない場合は、「[デスクフリー ワーカー向け Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise/frontline)」を参照してください。 サブスクリプションの選択についてさらにサポートが必要な場合、または組織で 300 を超えるライセンスが必要な場合は、[Microsoft パートナー](https://www.microsoft.com/solution-providers/home)または Microsoft アカウント担当者にお問い合わせください。

### <a name="assign-paid-licenses"></a>有料ライセンスを割り当てる

新しく取得したライセンスを割り当てるには、「[ユーザーにライセンスを割り当てる](/microsoft-365/admin/manage/assign-licenses-to-users)」をご覧ください。  

新しいライセンスを割り当てたら、Teams Exploratory ライセンスの割り当てを解除します。 詳細については、「[ユーザーからライセンスの割り当てを解除する](/microsoft-365/admin/manage/remove-licenses-from-users)」を参照してください。

## <a name="faq"></a>FAQ

**試用版の有効期間** <br>
フロントライン試用版の有効期限は 90 日です。

**90 日間のフロントライン試用版エクスペリエンスの終了時に管理者が行うべきこと** <br>
90 日間の試用版の終了時に、有料ライセンスを継続する必要があるユーザーを、ユーザーと共に確認する必要があります。 その後、[ユーザーをアップグレード](#upgrade-users-from-frontline-trial)する必要があります。

**試用版を開始したユーザーが組織を離れた場合** <br>
管理者は、残りの 90 日間試用版を監視し、試用版の終了時に、有料ライセンスの必要なユーザーをアップグレードする必要があります。

**データ保持ポリシーとは?** <br>
データ保持期間については、[Microsoft 365 サブスクリプション情報](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?)から確認できます。

**フロントライン試用版の開始時にユーザーにエラーが発生した場合** <br>
組織、試用版を開始するユーザー、試用版に追加されるユーザーが[適格性の条件](#eligibility)を満たしていることを確認してください。