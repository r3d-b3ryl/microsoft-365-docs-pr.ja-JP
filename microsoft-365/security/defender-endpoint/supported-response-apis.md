---
title: サポートされているMicrosoft Defender for Endpoint応答 API
description: 特定の応答関連のMicrosoft Defender for Endpoint API 呼び出しについて説明します。
keywords: response apis, graph api, サポートされている API, アクター, アラート, デバイス, ユーザー, ドメイン, IP, ファイル
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 8dd36e06b90726a01168ccd3ebf12886c127b101
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2022
ms.locfileid: "67050966"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>サポートされているMicrosoft Defender for Endpointクエリ API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!TIP]
> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-supported-response-apis-abovefoldlink)

実行できるサポートされている応答関連の API 呼び出しと、必要な要求ヘッダー、呼び出しからの予想される応答などの詳細について説明します。

## <a name="in-this-section"></a>このセクションの内容

<br>

****

|トピック|説明|
|---|---|
|調査パッケージの収集|この API を実行して、デバイスから調査パッケージを収集します。|
|デバイスの分離|この API を実行して、デバイスをネットワークから分離します。|
|デバイスの表示を解除する|デバイスを分離から削除します。|
|コードの実行制限|悪意のあるプロセスを停止して攻撃を含めるには、この API を実行します。 また、デバイスをロックダウンし、悪意のある可能性のあるプログラムの後続の試行が実行されないようにすることもできます。|
|Unrestrict コードの実行|侵害されたデバイスが修復されたことを確認した後、これを実行してアプリケーション ポリシーの制限を元に戻します。|
|ウイルス対策スキャンの実行|ウイルス対策スキャンをリモートで開始して、侵害されたデバイスに存在する可能性のあるマルウェアを特定して修復します。|
|ファイルの停止と検疫|この呼び出しを実行して、プロセスの実行を停止し、ファイルを検疫し、レジストリ キーなどの永続化を削除します。|
|サンプルの要求|この呼び出しを実行して、特定のデバイスからファイルのサンプルを要求します。 ファイルはデバイスから収集され、セキュリティで保護されたストレージにアップロードされます。|
|ブロック ファイル|この API を実行して、悪意のある可能性のあるファイルや疑わしいマルウェアを禁止することで、組織内での攻撃の今後の伝播を防ぎます。|
|ファイルのブロックを解除する|Microsoft Defender ウイルス対策を使用して組織内でファイルを実行できるようにします。|
|パッケージ SAS URI を取得する|この API を実行して、調査パッケージをダウンロードできる URI を取得します。|
|MachineAction オブジェクトを取得する|MachineAction オブジェクトを取得するには、この API を実行します。|
|MachineActions コレクションを取得する|これを実行して MachineAction コレクションを取得します。|
|FileActions コレクションを取得する|この API を実行して FileActions コレクションを取得します。|
|FileMachineAction オブジェクトを取得する|この API を実行して FileMachineAction オブジェクトを取得します。|
|FileMachineActions コレクションを取得する|この API を実行して FileMachineAction コレクションを取得します。|
|
