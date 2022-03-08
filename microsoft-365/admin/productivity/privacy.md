---
title: Microsoft 生産性スコア - プライバシー
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 生産性スコアでプライバシーを保護する方法。
ms.openlocfilehash: 94e0e1fb3190bc45fb0ad580cd823cb121fb60cf
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320733"
---
# <a name="privacy-controls-for-productivity-score"></a>生産性スコアのプライバシーコントロール

生産性スコアは、組織のデジタル変換の取り組みについて、Microsoft 365をサポートするテクノロジ エクスペリエンスに関する分析情報を提供します。  組織のスコアは、ユーザーとテクノロジ エクスペリエンスの測定値を反映し、類似した組織のベンチマークと比較できます。 詳細については、「生産性スコアの [概要」を参照してください](productivity-score.md)。

プライバシーは Microsoft にとって重要です。 プライバシーを保護する方法については、「Microsoft の [プライバシーに関する声明」をご覧ください](https://privacy.microsoft.com/privacystatement)。 生産性スコアを使用すると、組織の IT 管理者としてプライバシー設定にアクセスして、表示する生産性スコア情報を操作可能にし、組織が Microsoft で行う信頼を損なうのを助けることができます。

ユーザー エクスペリエンス領域内では、指標は組織レベルでのみ使用できます。 この領域では、コンテンツコラボレーション、モビリティMicrosoft 365会議、チームワーク、コミュニケーションのカテゴリを見て、ユーザーがコンテンツを使用する方法を確認します。 社内のプライバシー ポリシーのニーズを満たすのに役立つ、いくつかのレベルのコントロールを使用できます。
コントロールには、次の情報が表示されます。

- 生産性スコアで情報を表示できるユーザーを制御する柔軟な管理者ロール。
- ユーザー エクスペリエンス領域からオプトアウトする機能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>生産性スコアで情報を表示できるユーザーを制御する柔軟な管理者ロール

生産性スコア全体を表示するには、次のいずれかの管理者ロールが必要です。

- グローバル管理者
- Exchange 管理者
- SharePoint 管理者
- Skype for Business 管理者
- Teams 管理者
- グローバル閲覧者
- レポート閲覧者
- 使用状況の概要レポート閲覧者

変更管理と導入を担当しているが、必ずしも IT 管理者ではないすべてのユーザーに、レポート リーダーまたは利用状況概要レポート リーダーの役割を割り当てる。 この役割を使用すると、管理者センターで生産性スコアMicrosoft 365できます。

利用状況の概要レポート 閲覧者の役割は、2020 年後半にサーバーから割り当て可能になるまで、PowerShell コマンドレットを使用して割り当てるMicrosoft 365 管理センター必要があります。

PowerShell を使用して利用状況の概要レポート 閲覧者の役割を割り当てるには、次のコマンドを実行します。

- 次の PowerShell を実行します。

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>


## <a name="capability-to-opt-out-of-people-experiences"></a>ユーザー エクスペリエンスをオプトアウトする機能

また、生産性スコアの [ユーザー エクスペリエンス] 領域をオプトアウトできます。 オプトアウトすると、組織の誰もこれらの指標を表示できません。また、コミュニケーション、会議、チームワーク、コンテンツコラボレーション、モビリティを含む計算から組織が削除されます。 組織をユーザー エクスペリエンス レポートからオプトアウトするには、グローバル管理者である必要があります。

オプトアウトするには、次の方法を使用します。

1. 管理センターで、[**Org** 設定  >  製品設定 > **] に移動します**。
2. [ユーザーエクスペリエンスの分析情報に使用Microsoft 365を許可する] というボックス **をオフにします**。 Intune 構成マネージャーで Endpoint Analytics のデータ共有設定を変更する方法を理解するには、[詳細] **を選択します**。
3. [保存]  **を選択します**。

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="ユーザー エクスペリエンスからオプトアウトできる組織設定ページ。":::
