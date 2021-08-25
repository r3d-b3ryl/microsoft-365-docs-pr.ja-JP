---
title: クライアント アナライザーの HTML レポートについて
description: Microsoft Defender for Endpoint Client Analyzer HTML レポートを分析する方法について説明します。
keywords: クライアント アナライザー レポート、HTML レポート、クライアント アナライザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.technology: m365d
ms.openlocfilehash: 4027d31cd66a783b6bb83742912f94a3a017c74a
ms.sourcegitcommit: f358e321f7e81eff425fe0f0db1be0f3348d2585
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2021
ms.locfileid: "58508072"
---
# <a name="understand-the-client-analyzer-html-report"></a>クライアント アナライザーの HTML レポートについて

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

クライアント アナライザーは、HTML 形式でレポートを生成します。 レポートを確認して潜在的なセンサーの問題を特定し、トラブルシューティングを行う方法について説明します。

レポートを理解するには、次の例を使用します。

 有効期限が切れた組織 ID にオンボードされ、必要な Microsoft Defender for Endpoint URL の 1 つに到達できなかったコンピューターのアナライザーからの出力例:

![クライアント アナライザーの結果のイメージ](images/147cbcf0f7b6f0ff65d200bf3e4674cb.png)

- スクリプトのバージョンとスクリプト ランタイムの一番上に参照用の一覧が表示されます
- [ **デバイス情報]** セクションには、アナライザーが実行されているデバイスを一意に識別するための基本的な OS とデバイス識別子が表示されます。
- エンドポイント **セキュリティの詳細は**、Microsoft Defender for Endpoint 関連のプロセスに関する一般的な情報を提供します(Microsoft Defender ウイルス対策センサー プロセスを含む)。 重要なプロセスが期待通りオンラインではない場合、色は赤に変わります。

  ![クライアント アナライザーの詳細な結果のイメージ](images/85f56004dc6bd1679c3d2c063e36cb80.png)

- [ **結果の確認の概要]** で、アナライザーによって検出されたエラー、警告、または情報イベントの集計カウントが表示されます。
- [詳細 **な結果] には** 、分析プログラムによって行われた観測値に基づいて、結果とガイダンスを含むリスト (重大度別に並べ替え) が表示されます。

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Microsoft へのサポート チケットを開き、Analyzer の結果を含める

サポート チケットを開く際 [に](contact-support.md#open-a-service-request)アナライザーの結果ファイルを含めるには、[添付ファイル] セクションを使用 **し、ファイル** を含 `MDEClientAnalyzerResult.zip` めます。

![添付ファイルプロンプトの画像](images/508c189656c3deb3b239daf811e33741.png)

> [!NOTE]
> ファイル サイズが 25 MB を超える場合、ケースに割り当てられたサポート エンジニアは、分析用に大きなファイルをアップロードするための専用の安全なワークスペースを提供します。
