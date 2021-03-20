---
title: Microsoft 365 Defender のインシデントを調査する
description: デバイス、ユーザー、メールボックスに関連するインシデントを分析します。
keywords: インシデント、コンピューター、デバイス、ユーザー、ID、メール、電子メール、メールボックス、調査、グラフ、証拠
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 901f46f27c6c0e7b894288c015c74c7d3097ef23
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/08/2021
ms.locfileid: "50927254"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender のインシデントを調査する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**

- Microsoft 365 Defender

Microsoft 365 Defender は、デバイス、ユーザー、およびメールボックス全体からのすべての関連するアラート、資産、調査、および証拠を集計し、攻撃の幅広い全体を総合的に調査します。

効果的な修復計画を考案できるようにするために、ネットワークに影響するアラートを調査し、その意味を理解し、インシデントに関連する証拠を照合します。

## <a name="investigate-an-incident"></a>インシデントの調査

1. インシデント キューからインシデントを選択します。 <BR> サイド パネルが開き、ステータス、重大度、カテゴリ、影響を受け取ったエンティティなどの重要な情報のプレビューが表示されます。

    ![インシデント サイドパネルの画像](../../media/incident-side-panel.png)

2. [**インシデント ページを開く**] を選択します。 <BR> インシデント ページが開き、インシデントの詳細、コメント、アクション、タブ (概要、アラート、デバイス、ユーザー、調査、証拠) が表示されます。

3. インシデントに関連するアラート、デバイス、ユーザー、その他のエンティティを確認します。

## <a name="incident-overview"></a>インシデントの概要

概要ページでは、インシデントに関する主な情報がスナップショットで表示されます。

![インシデントの概要ページの画像](../../media/incidents-overview.png)

攻撃カテゴリを使用すると、キル チェーンに対する攻撃の進行状況を視覚的および数値的に確認できます。 他の Microsoft セキュリティ製品と同様に、Microsoft 365 Defender は[MITRE ATT &trade; ](https://attack.mitre.org/)と CK フレームワーク&揃っています。

範囲セクションでは、このインシデントの一部である最も影響を受ける資産の一覧が表示されます。 この資産に関する特定の情報 (リスク レベル、調査の優先順位、資産のタグ付けなど) がある場合は、その情報もこのセクションに表示されます。

アラートのタイムラインでは、アラートの発生順に時系列でプレビューすることができ、これらのアラートがインシデントに関連付けられた理由も表示されます。

最後に、証拠セクションでは、どれぐらいの数の成果物がインシデントに含まれるかや修復状況の概要が示されます。そのため、対応が必要かどうかをすぐに特定できます。

この概要は、注意が必要なインシデントの特徴の洞察を提供することで、インシデントの初回トリアージに役立ちます。

## <a name="alerts"></a>アラート

インシデントに関連するすべてのアラートと、重大度、アラートに関連したエンティティ、アラートのソース (Microsoft Defender for Identity、Microsoft Defender for Endpoint、Microsoft Defender for Office 365)、および関連付けされた理由など、インシデントに関連するその他の情報を表示できます。

![インシデント アラート ページの画像](../../media/incident-alerts.png)

既定では、アラートは発生順に並べ替えられています。これにより、発生した攻撃を時系列で確認できます。 各アラートをクリックすると、関連するアラート ページに移動し、そのアラートの詳細な調査を実行できます。 アラート の調査でアラート ページと統合アラート キューを使用する方法 [について説明します。](investigate-alerts.md)

## <a name="devices"></a>デバイス

[デバイス] タブには、インシデントに関連するアラートが表示されているすべてのデバイスが一覧表示されます。

攻撃が行われたコンピューターの名前をクリックすると、そのコンピューターのページが表示されます。調査を簡単にするために、トリガーされたアラートや関連イベントが表示されます。

![インシデントの [コンピューター] タブの画像](../../media/incident-machines.png)

[タイムライン] タブを選択すると、コンピューターのタイムラインをスクロールして、コンピューター上で監視されているすべてのイベントおよび動作、発生したアラートを日付順に表示できます。

## <a name="users"></a>ユーザー

特定のインシデントに関連すると識別されたユーザーを表示します。

ユーザー名をクリックすると、ユーザーの Cloud App Security ページに移動します。ここで詳細な調査を行うことができます。

![インシデントの [ユーザー] タブの画像](../../media/incident-users.png)

## <a name="mailboxes"></a>メールボックス

インシデントに関連すると識別されたメールボックスを調査します。 さらに調査作業を行うには、メール関連のアラートを選択すると、Microsoft Defender for Office 365 が開き、修復アクションを実行できます。

![インシデントの [メールボックス] タブの画像](../../media/incident-mailboxes.png)

## <a name="investigations"></a>調査

[ **調査] を** 選択して、このインシデントのアラートによってトリガーされる自動調査を表示します。 調査は、Microsoft Defender for Endpoint および Defender for Office 365 で実行するように自動調査を構成した方法に応じて、修復アクションを実行するか、アナリストによるアクションの承認を待機します。

![インシデントの [調査] タブの画像](../../media/incident-investigations.png)

調査を選択して [調査の詳細] ページに移動すると、調査と修復状況に関する詳細情報が表示されます。 調査の一環として承認待ちアクションがある場合は、[保留中のアクション] タブに表示されます。インシデント修復の一環としてアクションを実行します。

## <a name="evidence"></a>証拠

Microsoft 365 Defender は、インシデントがサポートしているすべてのイベントと不審なエンティティを自動的にアラートで調査し、自動応答と重要なファイル、プロセス、サービス、電子メールなどの情報を提供します。 これにより、インシデントの潜在的な脅威をすばやく検出してブロックできます。

![インシデントの [証拠] タブの画像](../../media/incident-evidence.png)

分析された各エンティティには、判定 (悪質、不審、クリーン)、および修復状況が示されます。 これにより、インシデント全体の修復状況、および修復の次の手順について理解するのをサポートします。

## <a name="related-topics"></a>関連項目

- [インシデントの概要](incidents-overview.md)
- [インシデントの優先度設定](incident-queue.md)
- [インシデントの管理](manage-incidents.md)

