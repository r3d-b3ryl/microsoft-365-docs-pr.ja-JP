---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 48ff6d6f5cac0991895c40cae90ca31657cfedff
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844884"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft セキュア スコアの新機能

Microsoft のセキュリティ[スコア](microsoft-secure-score.md)をより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。 お客様のスコアと最大可能スコアが新しくなります。 ただし、これによりセキュリティ体制が変わるわけではありません。

最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score.md#whats-new)」を参照してください。

## <a name="june-2020"></a>2020 年 6 月

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションを削除する

* Attack Surface Reduction ルールを有効にする

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection の改善アクションを追加する

* Adobe Reader が子プロセスを作成するのをブロックする
* ランサムウェアに対する高度な保護の使用
* すべての Office アプリケーションで子プロセスを作成することを禁止する
* Office アプリケーションで実行可能なコンテンツを作成することを禁止する
* JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする
* 難読化する可能性のあるスクリプトの実行をブロックする
* 電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする
* Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する
* USB から実行される信頼できないおよび署名されていないプロセスをブロックする
* WMI イベントサブスクリプション経由の永続化をブロックする
* Office アプリケーションが他のプロセスにコードを挿入するのをブロックする
* 実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する
* PSExec および WMI コマンドからのプロセス作成をブロックする
* Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)
* Office マクロからの Win32 API 呼び出しをブロックする
