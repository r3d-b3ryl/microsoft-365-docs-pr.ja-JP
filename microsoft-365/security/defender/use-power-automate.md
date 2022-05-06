---
title: Power Automateを使用する
description: Microsoft 365 Defenderの power automate とその使用方法について説明します。
keywords: 高度な捜索, 脅威の捜索, サイバー脅威の捜索, Microsoft 365 Defender, microsoft 365, m365, 検索, クエリ, テレメトリ, カスタム検出, スキーマ, secops
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a707de259897080f8e726aed70618ea6505bdea6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717528"
---
# <a name="use-power-automate-in-microsoft-365-defender"></a>Microsoft 365 DefenderでPower Automateを使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender

> Microsoft 365 Defender を体験しますか? [ラボ環境で評価](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)、または[運用でパイロット プロジェクトを実行](m365d-pilot.md?ocid=cx-evalpilot)することができます。
>

最新のセキュリティ運用 (SecOps) チームは、効果的に動作するために自動化が必要です。 実際の脅威の捜索と調査に重点を置くために、SecOps チームはPower Automateを使用してアラートの一覧をトリアージし、脅威ではないアラートを排除します。  

## <a name="criteria-for-resolving-alerts"></a>アラートを解決するための条件

- ユーザーが不在時のメッセージを有効にしている

- ユーザーが高リスクとしてタグ付けされていない

両方が true の場合、SecOps はアラートを正当な移動としてマークし、解決します。 通知は、アラートが解決された後、Microsoft Teamsに投稿されます。 

## <a name="connect-power-automate-to-microsoft-cloud-app-security"></a>Microsoft Cloud App SecurityにConnect Power Automateする

自動化を作成するには、Microsoft Cloud App Security (MCAS) にPower Automateを接続する前に API トークンが必要です。 

1. **[設定**] をクリックし、[**セキュリティ拡張機能**] を選択し、[**API トークン**] タブで [**トークンの追加**] をクリックします。 

2. トークンの名前を指定し、[ **生成**] をクリックします。 後で必要になるので、トークンを保存します。

## <a name="create-an-automated-flow"></a>自動化されたフローを作成する

詳細なステップ バイ ステップ プロセスについては、 [ここ](https://www.microsoft.com/en-us/videoplayer/embed/RWFIRn)のビデオを参照してください。 

このビデオでは、power Automate をMCASに接続する方法についても説明します。 

## <a name="related-information"></a>関連情報

- [Power AutomateとMicrosoft Cloud App Securityを統合する](/cloud-app-security/flow-integration)

- [Microsoft Power Automate ドキュメント](/power-automate)
