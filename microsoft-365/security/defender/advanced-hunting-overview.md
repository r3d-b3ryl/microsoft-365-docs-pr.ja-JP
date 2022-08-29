---
title: 概要 - 高度なハンティング
description: Microsoft 365 の高度な捜索クエリと、それらを使用してネットワーク内の脅威と弱点を積極的に発見する方法について学習する
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, kusto
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: fe5138ad12932acd8458303c631ae737fdcb4531
ms.sourcegitcommit: 7374c7b013890744d74e5214f7f8d69ca7874466
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2022
ms.locfileid: "67406192"
---
# <a name="proactively-hunt-for-threats-with-advanced-hunting-in-microsoft-365-defender"></a>Microsoft 365 Defender の高度な捜索により、脅威を積極的に捜索する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

高度なハンティングは、最大 30 日間の生データを探索できるクエリベースの脅威検出ツールです。 ネットワーク内のイベントを事前に検査して、脅威インジケーターとエンティティを見つけることができます。 データへの柔軟なアクセスにより、既知の脅威と潜在的な脅威の両方に対する制約のない捜索が可能になります。

高度なハンティングでは、ガイド付きモードと高度モードの 2 つのモードがサポートされています。 Kusto 照会言語 (KQL) にまだ慣れていない場合や、クエリ ビルダーの利便性を優先する場合は、[ガイド モード](advanced-hunting-query-builder.md)を使用します。 KQL を使用して最初からクエリを作成する場合は [、高度なモード](advanced-hunting-query-language.md) を使用します。 

**ハンティングを開始するには、「[Microsoft 365 Defenderでハントするガイドモードと高度なモードの選択」を](advanced-hunting-modes.md)参照してください。**
<br><br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4G6DO]

同じ脅威検出クエリを使用して、カスタム検出ルールを作成できます。 これらのルールは自動的に実行され、侵害の疑いのあるアクティビティ、不適切な構成されたマシン、およびその他の結果を確認して対応します。

この機能は、[Microsoft Defender for Endpointの高度なハンティング](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)に似ています。また、次のようなより広範なデータ セットをチェックするクエリがサポートされます。

- Microsoft Defender for Endpoint
- Microsoft Defender for Office 365
- Microsoft Defender for Cloud Apps
- Microsoft Defender for Identity

高度なハンティングを使用するには、[Microsoft 365 Defenderをオンにします](m365d-enable.md)。

Microsoft Defender for Cloud Apps データの高度な捜索の詳細については、[ビデオ](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa)を参照してください。 



## <a name="get-access"></a>アクセスを取得する
高度なハンティングやその他[のMicrosoft 365 Defender](microsoft-365-defender.md)機能を使用するには、Azure Active Directory で適切なロールが必要です。 [高度な捜索に必要なロールとアクセス許可について説明](custom-roles.md)します。

また、エンドポイント データへのアクセスは、Microsoft Defender for Endpointのロールベースのアクセス制御 (RBAC) 設定によって決まります。 [Microsoft 365 Defenderへのアクセスの管理について説明します](m365d-permissions.md)。


## <a name="data-freshness-and-update-frequency"></a>データの鮮度と更新頻度
高度な捜索データは、2 つの異なるタイプに分類され、それぞれが異なる形で集約されます。

- **イベントまたはアクティビティ データ**: アラート、セキュリティ イベント、システム イベント、ルーチン評価に関するテーブルを作成します。 高度な捜索は、このデータは、センサーが収集したデータを対応するクラウド サービスに転送した後、ほぼ瞬間的に受け取ります。 たとえば、ワークステーションまたはドメイン コントローラー上の正常なセンサーから、Microsoft Defender for EndpointとMicrosoft Defender for Identityで使用可能になった直後にイベント データに対してクエリを実行できます。
- **エンティティ データ** - ユーザーとデバイスに関する情報をテーブルに設定します。 このデータは、比較的静的なデータ ソースと、Active Directory エントリやイベント ログなどの動的なソースの両方から取得します。 新しいデータを提供するために、テーブルは 15 分ごとに新しい情報に更新され、十分に作成されていない可能性のある行が追加されます。 24 時間ごとにデータが統合され、各エンティティに関する最新かつ最も包括的なデータ セットを含むレコードが挿入されます。

## <a name="time-zone"></a>タイム ゾーン
高度なハンティングの時刻情報は、UTC (ユニバーサル タイム協定時刻) タイム ゾーンにあります。

## <a name="related-topics"></a>関連項目
- [ガイド付きモードと高度なハンティング モードの間で選択する](advanced-hunting-modes.md)
- [ガイド モードを使用してハンティング クエリを作成する](advanced-hunting-query-builder.md)
- [クエリ言語の説明](advanced-hunting-query-language.md)
- [スキーマを理解する](advanced-hunting-schema-tables.md)
- [カスタム検出の概要](custom-detections-overview.md)
