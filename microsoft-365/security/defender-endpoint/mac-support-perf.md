---
title: Microsoft Defender for Endpoint for Mac のパフォーマンスの問題のトラブルシューティング
description: Microsoft Defender for Endpoint for Mac のパフォーマンスの問題をトラブルシューティングします。
keywords: microsoft, defender, atp, mac, performance
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 87190d9e0bb62d42642374bd7c9f6f3acad3c80a
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379388"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Microsoft Defender for Endpoint for Mac のパフォーマンスの問題のトラブルシューティング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint for Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

このトピックでは、Microsoft Defender for Endpoint for Mac に関連するパフォーマンスの問題を絞り込む一般的な手順について説明します。

リアルタイム保護 (RTP) は、Microsoft Defender for Endpoint for Mac の機能であり、デバイスを継続的に監視し、脅威から保護します。 ファイルとプロセスの監視、その他のヒューリスティックで構成されます。

実行中のアプリケーションとデバイスの特性によっては、Microsoft Defender for Endpoint for Mac を実行するときに最適でないパフォーマンスが発生する場合があります。 特に、短時間で多くのリソースにアクセスするアプリケーションまたはシステム プロセスは、Microsoft Defender for Endpoint for Mac のパフォーマンスの問題につながる可能性があります。

次の手順を使用して、これらの問題のトラブルシューティングと軽減を行います。

1. 次のいずれかの方法を使用してリアルタイム保護を無効にし、パフォーマンスが向上するかどうかを確認します。 この方法は、Microsoft Defender for Endpoint for Mac がパフォーマンスの問題に貢献するかどうかを絞り込むのに役立ちます。

    デバイスが組織によって管理されていない場合は、次のいずれかのオプションを使用してリアルタイム保護を無効にすることができます。

    - ユーザー インターフェイスから。 Microsoft Defender for Endpoint for Mac を開き、[設定の管理] **に移動します**。

      ![リアルタイム保護のスクリーンショットを管理する](images/mdatp-36-rtp.png)

    - ターミナルから。 セキュリティ上の目的で、この操作には昇格が必要です。

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    デバイスが組織によって管理されている場合は [、「Microsoft Defender for Endpoint for Mac](mac-preferences.md)の設定」の手順に従って、管理者がリアルタイム保護を無効にすることができます。

2. Finder を開き、[アプリケーション ユーティリティ **]**  >  **に移動します**。 [ **アクティビティ モニター] を** 開き、システムでリソースを使用しているアプリケーションを分析します。 一般的な例としては、ソフトウェアアップデータとコンパイラが含まれます。

3. パフォーマンスの問題に寄与するプロセスまたはディスクの場所の除外を使用して Microsoft Defender for Endpoint for Mac を構成し、リアルタイム保護を再び有効にしてください。

    詳細 [については、「Configure and validate exclusions for Microsoft Defender for Endpoint for Mac」](mac-exclusions.md) を参照してください。
