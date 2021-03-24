---
title: サポートされている Microsoft Defender Advanced Threat Protection 応答 API
description: 特定の応答関連の Microsoft Defender Advanced Threat Protection API 呼び出しについて説明します。
keywords: 応答 API、グラフ API、サポートされている API、アクター、アラート、デバイス、ユーザー、ドメイン、IP、ファイル
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 93184cc82972a4b1c970b026ceff78adbc1fb7f8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062123"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>サポートされている Microsoft Defender for Endpoint クエリ API 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)

> [!TIP]
> Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

実行できるサポートされる応答関連 API 呼び出しと、必要な要求ヘッダー、呼び出しからの予期される応答などの詳細について説明します。

## <a name="in-this-section"></a>このセクションの内容
トピック | 説明
:---|:---
調査パッケージの収集 | この API を実行して、デバイスから調査パッケージを収集します。
デバイスの分離 | ネットワークからデバイスを分離するには、この API を実行します。
Unisolate デバイス | デバイスを分離から削除します。 
コードの実行を制限する | 悪意のあるプロセスを停止して攻撃を含めるには、この API を実行します。 デバイスをロックダウンして、悪意のある可能性のあるプログラムの後続の試行が実行されるのを防ぐことも可能です。
無制限のコード実行 | 侵害されたデバイスが修復されたと確認した後、アプリケーション ポリシーの制限を取り消す場合は、これを実行します。
ウイルス対策スキャンの実行 | ウイルス対策スキャンをリモートで開始して、侵害されたデバイスに存在する可能性のあるマルウェアを特定して修復します。
ファイルの停止と検疫 |  この呼び出しを実行して、プロセスの実行を停止し、ファイルを検疫し、レジストリ キーなどの永続性を削除します。
要求サンプル | この呼び出しを実行して、特定のデバイスからファイルのサンプルを要求します。 ファイルはデバイスから収集され、セキュリティで保護された記憶域にアップロードされます。
ブロック ファイル | この API を実行して、悪意のある可能性のあるファイルやマルウェアの疑いを禁止して、組織内の攻撃をさらに伝播防止します。 
ファイルのブロックを解除する | Microsoft Defender ウイルス対策を使用して組織内でファイルの実行を許可します。
パッケージ SAS URI の取得 | この API を実行して、調査パッケージのダウンロードを許可する URI を取得します。
MachineAction オブジェクトの取得 | この API を実行して MachineAction オブジェクトを取得します。
MachineActions コレクションの取得 | MachineAction コレクションを取得するには、これを実行します。
Get FileActions コレクション | FileActions コレクションを取得するには、この API を実行します。
Get FileMachineAction オブジェクト | FileMachineAction オブジェクトを取得するには、この API を実行します。
Get FileMachineActions コレクション | FileMachineAction コレクションを取得するには、この API を実行します。
