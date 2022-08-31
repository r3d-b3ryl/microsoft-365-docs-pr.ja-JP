---
title: クライアント アナライザー HTML レポートについて
description: Microsoft Defender for Endpoint Client Analyzer HTML レポートを分析する方法について説明します
keywords: クライアント アナライザー レポート、HTML レポート、クライアント アナライザー
ms.service: microsoft-365-security
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
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: b1b83200b9fd0f67d832b4dbb41352bebfa418bd
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470787"
---
# <a name="understand-the-client-analyzer-html-report"></a>クライアント アナライザー HTML レポートについて

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

クライアント アナライザーは、HTML 形式のレポートを生成します。 レポートを確認してセンサーの潜在的な問題を特定し、トラブルシューティングを行う方法について説明します。

レポートを理解するには、次の例を使用します。

 期限切れの組織 ID にオンボードされ、必要なMicrosoft Defender for Endpoint URL のいずれかに到達できないマシン上のアナライザーからの出力例を次に示します。

:::image type="content" source="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png" alt-text="MDE クライアント アナライザーの結果ページ" lightbox="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png":::

- 一番上に、スクリプト バージョンとスクリプト ランタイムが参照用に一覧表示されます
- [ **デバイス情報]** セクションには、アナライザーが実行されたデバイスを一意に識別するための基本的な OS とデバイス識別子が用意されています。
- **Endpoint Security Details** には、Microsoft Defender ウイルス対策やセンサー プロセスなど、Microsoft Defender for Endpoint関連のプロセスに関する一般的な情報が提供されます。 重要なプロセスが想定どおりにオンラインでない場合、色は赤に変わります。
  
-   **Endpoint Security Details** には、Microsoft Defender ウイルス対策やセンサー プロセスなど、Microsoft Defender for Endpoint関連のプロセスに関する一般的な情報が提供されます。 重要なプロセスが想定どおりにオンラインでない場合、色は赤に変わります。

    :::image type="content" source="images/85f56004dc6bd1679c3d2c063e36cb80.png" alt-text="[結果の確認の概要] ページ" lightbox="images/85f56004dc6bd1679c3d2c063e36cb80.png":::

-   **結果の確認の概要** では、アナライザーによって検出されたエラー、警告、または情報イベントの集計カウントが表示されます。

-   **詳細な結果** には、アナライザーによって行われた観察に基づく結果とガイダンスを含む一覧 (重大度別に並べ替え) が表示されます。

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Microsoft へのサポート チケットを開き、Analyzer の結果を含める

[サポート チケットを開くときに](contact-support.md#open-a-service-request)アナライザーの結果ファイルを含めるには、[**添付ファイル]** セクションを使用し、ファイルを`MDEClientAnalyzerResult.zip`含めてください。

:::image type="content" source="images/508c189656c3deb3b239daf811e33741.png" alt-text="添付ファイルプロンプト" lightbox="images/508c189656c3deb3b239daf811e33741.png":::

> [!NOTE]
> ファイル サイズが 25 MB を超える場合、ケースに割り当てられたサポート エンジニアは、分析用に大きなファイルをアップロードするための専用のセキュリティで保護されたワークスペースを提供します。
