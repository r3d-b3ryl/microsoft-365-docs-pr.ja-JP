---
title: Microsoft Productivity Score と privacy insights
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
description: 生産性スコアを使用してプライバシーを保護する方法。
ms.openlocfilehash: 823e2cc087d3f0e9c486d8c0c4eca92ba42aee21
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65467934"
---
# <a name="privacy-controls-for-productivity-score"></a>生産性スコアのプライバシー 制御

生産性スコアは、Microsoft 365とそれをサポートするテクノロジ エクスペリエンスを使用することで、組織のデジタル変革の過程に関する分析情報を提供します。  組織のスコアは、ユーザーとテクノロジエクスペリエンスの測定値を反映し、自分に似た組織のベンチマークと比較できます。 詳細については、 [生産性スコアの概要を](productivity-score.md)参照してください。

お客様のプライバシーは Microsoft にとって重要です。 お客様のプライバシーを保護する方法については、 [Microsoft のプライバシーに関する声明](https://privacy.microsoft.com/privacystatement)を参照してください。 生産性スコアは、組織の IT 管理者として、プライバシー設定にアクセスして、表示する生産性スコア情報が実行可能であることを確認するのに役立ちますが、組織が Microsoft に置く信頼を損なうことがないようにします。

ユーザー エクスペリエンス領域内では、メトリックは組織レベルでのみ使用できます。 この領域では、コンテンツ コラボレーション、モビリティ、会議、チームワーク、コミュニケーションのカテゴリを見て、ユーザーがMicrosoft 365を使用する方法を確認します。 内部プライバシー ポリシーのニーズを満たすのに役立つ、いくつかのレベルのコントロールを使用できます。
コントロールは次の機能を提供します。

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

変更管理と導入を担当するが、必ずしも IT 管理者であるとは限らないすべてのユーザーに、レポート リーダーまたは使用状況サマリー レポート閲覧者ロールを割り当てます。 このロールを使用すると、Microsoft 365管理センターで生産性スコアの完全なエクスペリエンスにアクセスできます。

利用状況の概要レポートリーダー ロールは、2020 年後半にMicrosoft 365 管理センターから割り当て可能になるまで、PowerShell コマンドレットを使用して割り当てる必要があります。

PowerShell を使用して利用状況の概要レポート閲覧者ロールを割り当てるには:

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

また、生産性スコアのユーザー エクスペリエンス領域をオプトアウトすることもできます。 オプトアウトすると、組織の誰もこれらのメトリックを表示できず、コミュニケーション、会議、チームワーク、コンテンツ コラボレーション、モビリティを含む計算から組織が削除されます。 ユーザー エクスペリエンス レポートから組織をオプトアウトするには、グローバル管理者である必要があります。

オプトアウトするには:

1. 管理センターで、**設定**  >  **Org 設定** > **Productivity Score に移動します**。
2. [**ユーザーエクスペリエンスの分析情報に使用するMicrosoft 365使用状況データを許可** する] チェック ボックスをオフにします。 Intune構成マネージャーで Endpoint Analytics のデータ共有設定を変更する方法を理解するには、[**詳細]** を選択します。
3. **[保存] を選択します**。

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="[組織の設定] ページでは、ユーザーエクスペリエンスからオプトアウトできます。":::
