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
ROBOTS: NOINDEX, NOFOLLOW
description: 生産性スコアによるプライバシーの保護
ms.openlocfilehash: 62ff3a9f0434421cbe1115f13376e92bd9f3cac9
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794979"
---
# <a name="privacy-controls-for-productivity-score"></a>生産性スコアのプライバシー制御

生産性スコアを使用すると、組織は、ユーザーやテクノロジのエクスペリエンスを測定して改善するのに役立つ指標を使用して作業を行う方法を変革することができます。 お客様の組織がどのように機能するかを把握するのに役立ちます。向上したエクスペリエンスを実現することに重点を置いた指標を提供します。  また、スキルとシステムを更新してすべてのユーザーが最善の作業を行えるようにするために、測定値をアクションに接続することもできます。 スコアは、組織のパフォーマンスを反映しており、自分のスコアを他の組織と安全に比較することができます。  詳細については、「 [生産性スコアの概要」](productivity-score.md)をご覧ください。

お客様のプライバシーは我々にとって重要です。 プライバシーを保護する方法については、「 [Microsoft のプライバシー](https://privacy.microsoft.com/privacystatement)に関する声明」を参照してください。 「生産性スコア」では、組織内のユーザーがコントロールを使用して、Microsoft での信頼を侵害せずに情報を確実に処理できるようにする方法に関する重要な情報を提供します。

ユーザーエクスペリエンスの分野では、測定基準が組織レベルで利用可能であり、Microsoft 365 テナント内のすべてのユーザーが含まれています。 ここでは、コンテンツコラボレーション、モビリティ、会議、チームワーク、およびコミュニケーションのカテゴリについて、ユーザーが Microsoft 365 を使用する方法について説明します。 製品のサポートが必要になる可能性がある、適切な一連のユーザーに対するトレーニングと認識を促進するために、個々のレベルに関する情報も提供しています。 このレベルの透明性を提供していますが、お客様の内部プライバシーポリシーのニーズを満たすために役立ついくつかのレベルの制御も可能にします。
次のコントロールが提供されます。

- 生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割。
- ユーザーレベルの指標の識別を解除する機能。
- ユーザーエクスペリエンスをオプトアウトする機能。
- ユーザーエクスペリエンスの分野をオプトアウトする機能

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-productivity-score"></a>生産性スコアに情報を表示できるユーザーを制御するための柔軟な管理者の役割

テナントレベルの指標やユーザーごとの詳細を含む生産性スコア全体を表示するには、次のいずれかの管理者ロールを割り当てる必要があります。

- グローバル管理者
- Exchange の管理者
- SharePoint 管理者
- Skype for Business 管理者
- Teams 管理者
- グローバル閲覧者
- レポート閲覧者

変更の管理と採用を担当するすべてのユーザーにレポート閲覧者の役割を割り当てます。 この役割により、テナントレベルの指標とユーザーごとのレベルの詳細を含む完全な環境にアクセスできるようになります。

ユーザーエクスペリエンスレポートには、カテゴリ詳細ページごとのユーザーごとのアクティビティの詳細が含まれています。 ユーザーエクスペリエンスの集約指標のみにアクセスできるようにするには、利用状況の概要レポート閲覧者 (2020 年10月10日開始) と呼ばれるカスタムロールを割り当てます。 この役割は、11/15/2020 の Microsoft 管理センターから割り当てが可能になるまで、PowerShell コマンドレットを通じて割り当てる必要があります。

PowerShell で利用状況の概要レポートの閲覧者の役割を割り当てるには、次のようにします。

- 次の PowerShell を実行します。

```powershell
Connect-AzureAD
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

</br>

:::image type="content" source="../../media/communicationspage.jpg" alt-text="生産性レポートの [通信] ページ":::

## <a name="de-identification-of-user-level-metrics"></a>ユーザーレベルの指標の識別を解除する

すべてのレポートで匿名で収集されるデータを作成するには、全体管理者である必要があります。 この操作を行うと、生産性のスコアや Microsoft 365 の使用状況を含む、すべてのレポートのユーザー、グループ、サイト名など、識別可能な情報が表示されなくなります。

1. 管理センターで、[設定] [ **Settings**   >   **組織設定** ] に移動し、[ **サービス** ] タブの [ **レポート** ] を選択します。
2. [  **レポート** ] を選択し、[  **生産性スコアと利用状況レポート] にユーザー、グループ、およびサイト名の匿名識別子を表示** するように選択します。 この設定は、利用状況レポートとテンプレートアプリの両方に適用されます。
3. [  **Save changes** ] を選びます。

:::image type="content" source="../../media/orgsettings_anonymous.jpg" alt-text="生産性レポートの [通信] ページ":::

## <a name="capability-to-opt-out-of-people-experiences"></a>ユーザーエクスペリエンスをオプトアウトする機能

生産性スコアが一般公開されている場合は、生産性スコアの people エクスペリエンス領域をオプトアウトすることもできます。 オプトインした場合、組織からこれらの指標を表示することはできません。また、コミュニケーション、会議、チームワーク、コンテンツコラボレーション、モビリティを含む計算から組織が削除されることはありません。

1. 管理センターで、[設定] [ **Settings**   >   **組織設定** ] に移動し、[ **サービス** ] タブの [ **レポート** ] を選択します。
2. [  **レポート** ] を選択し、[  **Microsoft 365 の利用状況データをユーザーエクスペリエンスの分析に使用できるよう** にする] チェックボックスをオフにします。 Intune 構成マネージャーでエンドポイント分析のデータ共有設定を変更する方法について理解するには、[ **詳細情報** ] をクリックします。
3. [  **Save changes** ] を選びます。

:::image type="content" source="../../media/orgsettingspageoptout.jpg" alt-text="生産性レポートの [通信] ページ":::