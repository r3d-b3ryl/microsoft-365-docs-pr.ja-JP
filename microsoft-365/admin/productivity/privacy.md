---
title: Microsoft プロダクティビティスコア-プライバシー
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: 生産性スコアによるプライバシーの保護
ms.openlocfilehash: ceb19fcb7bbf2f6a58e38684604ed3b0dac2a5d4
ms.sourcegitcommit: d859ea36152c227699c1786ef08cda5805ecf7db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49604328"
---
# <a name="privacy-controls-for-productivity-score"></a>生産性スコアのプライバシー制御

生産性スコアは、Microsoft 365 とそれをサポートするテクノロジエクスペリエンスを利用して、組織のデジタル変換に関する洞察を提供します。  組織のスコアは、人とテクノロジの実績を反映しており、組織と同じようなベンチマークと比較できます。 詳細については、「 [生産性スコアの概要」](productivity-score.md)を参照してください。

お客様のプライバシーは Microsoft にとって重要です。 プライバシーを保護する方法については、「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。 生産性スコアを使用すると、組織の IT 管理者は、自分の組織が Microsoft にもたらす信頼を侵害するのではなく、表示する生産性スコア情報を確実に処理できるプライバシー設定にアクセスできます。

ユーザーエクスペリエンスエリア内では、指標は組織レベルでのみ利用可能です。 ここでは、コンテンツコラボレーション、モビリティ、会議、チームワーク、およびコミュニケーションのカテゴリについて、ユーザーが Microsoft 365 を使用する方法について説明します。 さまざまなレベルのコントロールを使用して、内部のプライバシーポリシーのニーズを満たすことができます。
次のようなコントロールがあります。

- 生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割。
- ユーザーエクスペリエンスエリアから脱退する機能。

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割

生産性スコア全体を表示するには、次の管理役割のいずれかが必要です。

- グローバル管理者
- Exchange の管理者
- SharePoint 管理者
- Skype for Business 管理者
- Teams 管理者
- グローバル閲覧者
- レポート閲覧者
- 利用状況の概要レポートの閲覧者

変更の管理と導入を担当し、必ずしも IT 管理者ではないすべてのユーザーに、レポートリーダーまたは利用状況の概要レポートの閲覧者の役割を割り当てます。 この役割により、Microsoft 365 管理センターでの完全な生産性スコアの効果にアクセスできます。

利用状況の概要レポートの閲覧者の役割は、PowerShell コマンドレットを介して割り当てる必要があります。これは、2020の後の Microsoft 365 管理センターから割り当てられるようになります。

PowerShell で利用状況の概要レポートの閲覧者の役割を割り当てるには、次のようにします。

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


## <a name="capability-to-opt-out-of-people-experiences"></a>ユーザーエクスペリエンスをオプトアウトする機能

また、生産性スコアの people エクスペリエンス領域をオプトアウトすることもできます。 脱退した場合、組織内のユーザーがこれらの指標を表示することはできません。また、コミュニケーション、会議、チームワーク、コンテンツコラボレーション、モビリティを含む計算から組織が削除されます。 ユーザーエクスペリエンスレポートから組織を脱退するには、グローバル管理者である必要があります。

Opt put:

1. 管理センターで、[設定] [ **Settings**   >   **組織設定**] に移動し、[**サービス**] タブの [**レポート**] を選択します。
2. [  **ユーザーエクスペリエンスの分析に Microsoft 365 usage data を使用できるように** する] チェックボックスをオフにします。 Intune 構成マネージャーでエンドポイント分析のデータ共有設定を変更する方法について理解するには、[ **詳細情報**] を選択します。
3. [  **保存**] を選択します。

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="ユーザーエクスペリエンスからオプトアウトできる [組織の設定] ページ":::