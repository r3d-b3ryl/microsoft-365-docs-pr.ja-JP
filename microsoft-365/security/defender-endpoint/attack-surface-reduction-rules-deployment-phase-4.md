---
title: ASR ルール 展開フェーズ 4 - 運用化
description: 攻撃対象の縮小ルールの展開を運用化するためのガイダンスを提供します。
keywords: 攻撃表面の縮小ルールの展開、ASR 展開、ASR の有効化、ASR の構成、ホスト侵入防止システム、保護規則、悪用防止ルール、悪用防止ルール、悪用防止ルール、感染防止ルール、Microsoft Defender for Endpoint、ASR 規則の構成
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: m365solution-scenario
ms.date: 1/18/2022
ms.openlocfilehash: b668519b84037000610fa3fe76ec5462b9657b3d
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322875"
---
# <a name="asr-rules-deployment-phase-4-operationalize"></a>ASR ルールのデプロイ フェーズ 4: 運用化

ASR ルールを完全にデプロイしたら、ASR 関連のアクティビティを監視して対応するためのプロセスを用意することが重要です。

## <a name="manage-false-positives"></a>誤検知を管理する

False positives/negatives は、任意の脅威保護ソリューションで発生する可能性があります。 False positives は、エンティティ (ファイルやプロセスなど) が検出され、悪意のあるものとして識別されるケースですが、エンティティは実際には脅威ではありません。 これに対し、偽陰性は、脅威として検出されなかったが悪意のあるエンティティです。 誤検知と偽陰性の詳細については、「Microsoft Defender for Endpoint[の誤検知/否定に対処する](defender-endpoint-false-positives-negatives.md)」を参照してください。

## <a name="keeping-up-with-reports"></a>レポートに追いつく

レポートの一貫性のある定期的なレビューは、ASR ルールのデプロイを維持し、新たに出現する脅威を維持するうえで不可欠な側面です。 組織には、ASR ルールで報告されたイベントを最新の状態に保つ、定期的な ASR ルール イベントのレビューがスケジュールされている必要があります。 組織の規模によっては、レビューは毎日、毎時、または継続的に監視される場合があります。

## <a name="hunting"></a>検索

[Microsoft 365 Defender](https://security.microsoft.com)の最も強力な機能の 1 つは、高度な捜索です。 高度な捜索に慣れていない場合は、「高度な捜索 [で脅威をプロアクティブに検索](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)する」を参照してください。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高度なハンティング](images/asr-defender365-advanced-hunting2.png)

高度な捜索は、Microsoft Defender ATP エンドポイント検出と応答 (EDR) がすべてのマシンから収集するキャプチャされた (未加工) データの最大 30 日間を探索できる、クエリベースの (Kusto 照会言語) 脅威検出ツールです。 高度な捜索を通じて、イベントを事前に検査して、興味深いインジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対して、無制限な捜索が容易になります。

高度な捜索を通じて、ASR ルール情報を抽出し、レポートを作成し、特定の ASR ルール監査またはブロック イベントのコンテキストに関する詳細な情報を取得できます。

 Microsoft 365 Defender ポータルの高度なハンティング セクションの DeviceEvents テーブルから ASR ルール イベントに対してクエリを実行できます。 たとえば、次のような単純なクエリでは、過去 30 日間のデータ ソースとして ASR ルールを持つすべてのイベントを報告でき、ActionType カウントで集計されます。この場合は ASR ルールの実際のコード名になります。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高度なハンティング クエリコマンド ライン](images/asr-defender365-advanced-hunting3.png)

> [!div class="mx-imgBorder"]
> ![高度な検索クエリの結果をMicrosoft 365 Defenderする](images/asr-defender365-advanced-hunting4.png)

上記は、AsrLsassCredentialTheft に 187 個のイベントが登録されたことを示しています。

- 102 for Blocked
- 監査対象の 85
- AsrOfficeChildProcess の 2 つのイベント (監査対象は 1、ブロックの場合は 1)
- AsrPsexecWmiChildProcessAudited の 8 つのイベント

AsrOfficeChildProcess ルールに重点を置き、関連する実際のファイルとプロセスの詳細を取得する場合は、ActionType のフィルターを変更し、集計行を必要なフィールドのプロジェクション (この場合は DeviceName、FileName、FolderPath など) に置き換えます。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高度なハンティング クエリに焦点を当てた](images/asr-defender365-advanced-hunting4b.png)

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高度なハンティング クエリのフォーカスされた結果](images/asr-defender365-advanced-hunting5b.png)

高度な捜索の真の利点は、クエリを好みに合わせて整形できることです。 クエリを整形すると、個々のマシンで何かを特定したいかどうかや、環境全体から分析情報を抽出する場合に関係なく、何が起きているのかを正確に把握できます。

ハンティング オプションの詳細については、「 [Demystifying 攻撃表面の縮小ルール - パート 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)」を参照してください。

## <a name="topics-in-this-deployment-collection"></a>このデプロイ コレクションのトピック

[ASR ルールの展開の概要](attack-surface-reduction-rules-deployment.md)

[フェーズ 1: 計画](attack-surface-reduction-rules-deployment-phase-1.md)

[フェーズ 2: テスト](attack-surface-reduction-rules-deployment-phase-2.md)

[フェーズ 4: 運用化](attack-surface-reduction-rules-deployment-phase-4.md)
