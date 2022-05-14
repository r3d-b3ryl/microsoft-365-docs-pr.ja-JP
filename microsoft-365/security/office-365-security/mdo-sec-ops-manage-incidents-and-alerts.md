---
title: Microsoft 365 Defender で Defender for Office 365 からのインシデントとアラートを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: SecOps 担当者は、Microsoft 365 Defenderのインシデント キューを使用してMicrosoft Defender for Office 365のインシデントを管理する方法を学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 05525ac8ac10f8702db4e25d4163fed03b899bc9
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416990"
---
# <a name="manage-incidents-and-alerts-from-microsoft-defender-for-office-365-in-microsoft-365-defender"></a>Microsoft 365 DefenderのMicrosoft Defender for Office 365からインシデントとアラートを管理する

Microsoft 365 Defenderの[インシデント](/microsoft-365/security/defender/incidents-overview)は、攻撃の完全なストーリーを定義する相関アラートと関連データのコレクションです。 Defender for Office 365 [アラート](/microsoft-365/compliance/alert-policies#default-alert-policies)、[自動調査と対応 (AIR)](office-365-air.md#the-overall-flow-of-air)、および調査の結果は、Microsoft 365 Defenderの [**インシデント]** ページで<https://security.microsoft.com/incidents-queue>ネイティブに統合され、関連付けられます。 このページを _インシデント キュー_ と呼びます。

アラートは、悪意のあるアクティビティや疑わしいアクティビティがエンティティ (電子メール、ユーザー、メールボックスなど) に影響を与える場合に作成されます。 アラートは、進行中または完了した攻撃に関する貴重な分析情報を提供します。 ただし、継続的な攻撃は複数のエンティティに影響を与える可能性があり、その結果、異なるソースから複数のアラートが発生します。 一部の組み込みアラートでは、AIR プレイブックが自動的にトリガーされます。 これらのプレイブックでは、影響を受ける他のエンティティや疑わしいアクティビティを探すために、一連の調査手順を実行します。

Microsoft 365 DefenderでMicrosoft Defender for Office 365アラートを管理する方法については、この短いビデオをご覧ください。  
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGrL2]

Defender for Office 365アラート、調査、およびそのデータは自動的に関連付けられます。 リレーションシップが決定されると、システムによってインシデントが作成され、セキュリティ チームが攻撃全体を把握できるようになります。

SecOps チームは、インシデントキュー<https://security.microsoft.com/incidents-queue>のDefender for Office 365からのインシデントとアラートを管理することを強くお勧めします。 この方法には、次の利点があります。

- [管理](/microsoft-365/security/defender/manage-incidents)のための複数のオプション:
  - 優先 順位 付け
  - フィルター処理
  - 分類
  - タグ管理

  キューから直接インシデントを受け取るか、他のユーザーに割り当てることができます。 コメントとコメントの履歴は、進行状況を追跡するのに役立ちます。

- 攻撃が Microsoft Defender<sup>\*</sup> によって保護されている他のワークロードに影響を与える場合、関連するアラート、調査、およびそのデータも同じインシデントに関連付けられます。

  <sup>\*</sup>Microsoft Defender for Endpoint、Microsoft Defender for Identity、およびMicrosoft Defender for Cloud Apps。

- 複雑な関連付けロジックは必要ありません。これは、ロジックがシステムによって提供されるためです。

- 関連付けロジックがニーズを完全に満たしていない場合は、既存のインシデントにアラートを追加したり、新しいインシデントを作成したりできます。

- 関連するDefender for Office 365アラート、AIR 調査、および調査からの保留中のアクションは、インシデントに自動的に追加されます。

- AIR 調査で脅威が見つからない場合、関連するアラートはシステムによって自動的に解決されます。 インシデント内のすべてのアラートが解決されると、インシデントの状態も **解決済み** に変わります。

- 関連する証拠と応答アクションは、インシデントの [ **証拠と応答** ] タブで自動的に集計されます。

- セキュリティ チーム のメンバーは、インシデントから直接対応アクションを実行できます。 たとえば、メールボックス内のメールを論理的に削除したり、メールボックスから不審な受信トレイ ルールを削除したりできます。

- 推奨される電子メール アクションは、悪意のあるメールの最新の配信場所がクラウド メールボックスである場合にのみ作成されます。

- 保留中の電子メール アクションは、最新の配信場所に基づいて更新されます。 電子メールが手動アクションによって既に修復されている場合は、その状態が反映されます。

- 推奨されるアクションは、最も重大な脅威であると判断された電子メール クラスターと電子メール クラスターに対してのみ作成されます。
  - マルウェア
  - 高確度のフィッシング
  - 悪意のある URL
  - 悪意のあるファイル

> [!NOTE]
> インシデントは、静的イベントを表すだけではありません。 また、時間の経過と共に発生する攻撃ストーリーも表します。 攻撃が進行すると、新しいDefender for Office 365アラート、AIR 調査、およびそのデータが既存のインシデントに継続的に追加されます。

Microsoft 365 Defender ポータル<https://security.microsoft.com/incidents-queue>の [**インシデント**] ページでインシデントを管理する

![Microsoft 365 Defender ポータルの [インシデント] ページ。](../../media/mdo-sec-ops-incidents.png)

![Microsoft 365 Defender ポータルの [インシデント] ページの詳細ポップアップ。](../../media/mdo-sec-ops-incident-details.png)

![Microsoft 365 Defender ポータルの [インシデント] ページでポップアップをフィルター処理します。](../../media/mdo-sec-ops-incident-filters.png)

![Microsoft 365 Defender ポータルのインシデントの詳細の [概要] タブ。](../../media/mdo-sec-ops-incident-summary-tab.png)

![Microsoft 365 Defender ポータルのインシデントの詳細の [証拠とアラート] タブ。](../../media/mdo-sec-ops-incident-evidence-and-response-tab.png)

Microsoft Sentinel <https://portal.azure.com/#blade/HubsExtension/BrowseResource/resourceType/microsoft.securityinsightsarg%2Fsentinel>の [インシデント] ページでインシデントを管理 **する**

![Microsoft Sentinel の [インシデント] ページ。](../../media/mdo-sec-ops-microsoft-sentinel-incidents.png)

![Microsoft Sentinel の [インシデントの詳細] ページ。](../../media/mdo-sec-ops-microsoft-sentinel-incident-details.png)

## <a name="response-actions-to-take"></a>実行する応答アクション

セキュリティ チームは、Defender for Office 365 ツールを使用して、電子メールに対してさまざまな応答アクションを実行できます。

- メッセージは削除できますが、電子メールで次の操作を実行することもできます。
  - 受信トレイに移動する
  - 迷惑メールに移動する
  - 削除済みアイテムに移動する
  - 論理的な削除
  - ハード削除。

  これらのアクションは、次の場所から実行できます。

  - [インシデント **] ページ**** <https://security.microsoft.com/incidents-queue> のインシデントの詳細の [**証拠と応答**] タブ (推奨)。
  - **脅威エクスプローラー** at <https://security.microsoft.com/threatexplorer>.
  - 統合 **アクション センター** (.<https://security.microsoft.com/action-center/pending>

- 脅威エクスプローラーの **[トリガー調査** ] アクションを使用して、任意の電子メール メッセージで AIR プレイブックを手動で開始できます。

- [脅威エクスプローラー](threat-explorer.md)または[管理者の提出](admin-submission.md)を使用して、誤検知または誤検知の検出を Microsoft に直接報告できます。

- [テナント許可/ブロック リスト](tenant-allow-block-list.md)を使用して、検出されない悪意のあるファイル、URL、または送信者をブロックできます。

Defender for Office 365アクションはハンティング エクスペリエンスにシームレスに統合され、アクションの履歴は統合 **アクション センター** の [**履歴**] タブに<https://security.microsoft.com/action-center/history>表示されます。

アクションを実行する最も効果的な方法は、組み込みのインシデントとMicrosoft 365 Defenderの統合を使用することです。 Microsoft 365 Defenderのインシデントの [[証拠と応答](/microsoft-365/security/defender/investigate-incidents#evidence-and-response)] タブのDefender for Office 365で AIR によって推奨されたアクションを承認するだけです。 この取り付けアクションの方法は、次の理由から推奨されます。

- 完全な攻撃ストーリーを調査します。
- 他のワークロード (Microsoft Defender for Endpoint、Microsoft Defender for Identity、Microsoft Defender for Cloud Apps) との組み込みの相関関係を利用できます。
- 1 か所からメールに対してアクションを実行します。

手動調査または捜索アクティビティの結果に基づいて、電子メールに対してアクションを実行します。 [Threat Explorer を](threat-explorer.md) 使用すると、セキュリティ チーム メンバーは、クラウド メールボックスにまだ存在する可能性がある電子メール メッセージに対してアクションを実行できます。 組織内のユーザー間で送信された組織内のメッセージに対してアクションを実行できます。 脅威エクスプローラーのデータは、過去 30 日間利用できます。

この短いビデオでは、Defender for Office 365などのさまざまな検出ソースからのアラートをインシデントに結合Microsoft 365 Defender方法について説明します。 
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWGpcs]
