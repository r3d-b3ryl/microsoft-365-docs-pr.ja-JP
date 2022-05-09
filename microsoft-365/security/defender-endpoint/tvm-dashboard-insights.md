---
title: ダッシュボードの分析情報 - 脅威と脆弱性の管理
description: 脅威と脆弱性の管理 ダッシュボードは、SecOps とセキュリティ管理者がサイバーセキュリティの脅威に対処し、組織のセキュリティ回復性を構築するのに役立ちます。
keywords: Microsoft Defender for Endpoint-tvm、Microsoft Defender for Endpoint-tvm ダッシュボード、脅威& 脆弱性の管理、脅威と脆弱性の管理、リスクベースの脅威& 脆弱性の管理、セキュリティ構成、デバイスの Microsoft セキュリティ スコア、公開スコア
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 76eedd78e6bc6a95450a50c04d4f85b0de46db8e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64472487"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>ダッシュボードの分析情報 - 脅威と脆弱性の管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**

- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [脅威と脆弱性の管理](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

脅威と脆弱性の管理は Defender for Endpoint のコンポーネントであり、セキュリティ管理者とセキュリティ運用チームの両方に次のような一意の価値を提供します。

- エンドポイントの脆弱性に関連したリアルタイムのエンドポイント検出と応答（EDR）の分析
- インシデント調査中の非常に貴重なデバイスの脆弱性コンテキスト
- Microsoft IntuneとMicrosoft Endpoint Configuration Managerによる組み込みの修復プロセス

Microsoft 365 Defender ポータルで脅威と脆弱性の管理機能を使用すると、<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">次のことができます</a>。

- デバイスの公開スコアと Microsoft Secure Score を、セキュリティに関する推奨事項、ソフトウェアの脆弱性、修復アクティビティ、公開されたデバイスと共に表示する
- EDR分析情報とエンドポイントの脆弱性を関連付けて処理する
- 修復オプションを選択して修復タスクをトリアージして追跡する
- 例外オプションを選択し、アクティブな例外を追跡する

> [!NOTE]
> 過去 30 日間にアクティブになっていないデバイスは、組織の脅威と脆弱性の管理公開スコアと Microsoft Secure Score for Devices を反映したデータには考慮されません。

このビデオでは、脅威と脆弱性の管理 ダッシュボードの概要を簡単に確認できます。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>脅威と脆弱性の管理ダッシュボード

:::image type="content" source="../../media/tvmdashboard.png" alt-text="デバイスの脅威と脆弱性の管理ダッシュボード" lightbox="../../media/tvmdashboard.png":::

<br>

****

|分野|説明|
|---|---|
|**選択したデバイス グループ (#/#)**|ダッシュボードに表示する脅威と脆弱性の管理 データとカードをデバイス グループでフィルター処理します。 フィルターで選択した内容は、脅威と脆弱性の管理 ページ全体に適用されます。|
|[**暴露スコア**](tvm-exposure-score.md)|組織のデバイスが脅威や脆弱性にさらされている現在の状態を確認します。 組織の露出スコアには、デバイスで検出された弱点、デバイスが侵害される可能性、組織に対するデバイスの価値、デバイスで検出された関連するアラートなど、いくつかの要因が影響します。 目標は、組織の公開スコアを低くして、より安全にすることです。 スコアを減らすには、セキュリティに関する推奨事項に記載されている関連するセキュリティ構成の問題を修復する必要があります。|
|[**デバイスの Microsoft セキュア スコア**](tvm-microsoft-secure-score-devices.md)|組織のオペレーティング システム、アプリケーション、ネットワーク、アカウント、セキュリティ制御のセキュリティ体制を確認します。 目標は、関連するセキュリティ構成の問題を修復して、デバイスのスコアを上げることです。 バーを選択すると、[ **セキュリティに関する推奨事項** ] ページに移動します。|
|**デバイスの露出分布**|露出レベルに基づいて公開されるデバイスの数を確認します。 ドーナツ グラフのセクションを選択して **[デバイス] リスト** ページに移動し、影響を受けるデバイス名、露出レベル、リスク レベル、その他の詳細 (ドメイン、オペレーティング システム プラットフォーム、正常性状態、最後に表示されたとき、タグなど) を表示します。|
|**セキュリティに関する推奨事項**|組織のリスクの露出と、それに必要な緊急度に基づいて並べ替えられ、優先順位が付けられた併置されたセキュリティに関する推奨事項を確認します。 [ **詳細を表示]** を選択して、一覧の残りのセキュリティに関する推奨事項を表示します。 例外がある推奨事項の一覧で [ **例外の表示** ] を選択します。|
|**脆弱なソフトウェアの上位**|ネットワークのデバイスにインストールされている脆弱なソフトウェアのスタック ランクの一覧と、組織の公開スコアに影響を与える方法を使用して、組織のソフトウェア インベントリをリアルタイムで確認できます。 詳細については項目を選択するか **、[詳細を表示]** を選択して、[ **ソフトウェア インベントリ** ] ページで脆弱なソフトウェアの残りの一覧を表示します。|
|**トップ 修復アクティビティ**|セキュリティに関する推奨事項から生成された修復アクティビティを追跡します。 一覧の各項目を選択して **、[修復]** ページで詳細を表示するか、[ **詳細の表示** ] を選択して、残りの修復アクティビティとアクティブな例外を表示できます。|
|**公開されている上位のデバイス**|公開されているデバイス名とその露出レベルを表示します。 一覧からデバイス名を選択すると、デバイス ページに移動し、公開されているデバイスに関連するアラート、リスク、インシデント、セキュリティに関する推奨事項、インストールされたソフトウェア、検出された脆弱性を表示できます。 [ **詳細を表示]** を選択して、公開されているデバイスの残りの一覧を表示します。 デバイスの一覧から、タグの管理、自動調査の開始、ライブ応答セッションの開始、調査パッケージの収集、ウイルス対策スキャンの実行、アプリの実行の制限、デバイスの分離を行うことができます。|
|

ポータル全体で使用されるアイコンの詳細については、「[Microsoft Defender for Endpoint アイコン](portal-overview.md#microsoft-defender-for-endpoint-icons)」を参照してください。

## <a name="related-topics"></a>関連項目

- [脅威と脆弱性の管理の概要](next-gen-threat-and-vuln-mgt.md)
- [暴露スコア](tvm-exposure-score.md)
- [デバイス向けの Microsoft セキュア スコア](tvm-microsoft-secure-score-devices.md)
- [セキュリティに関する推奨事項](tvm-security-recommendation.md)
- [ソフトウェア インベントリ](tvm-software-inventory.md)
- [イベントのタイムライン](threat-and-vuln-mgt-event-timeline.md)
