---
title: ネットワーク保護を評価する
description: ネットワーク保護が保護する一般的なシナリオをテストして、ネットワーク保護のしくみを確認します。
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、評価、テスト、デモ
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f32e6be475ad61b83220a76527b625f2aa06580d6a181cdd8f8133eba2d27211
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898416"
---
# <a name="evaluate-network-protection"></a>ネットワーク保護を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- - [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[ネットワーク保護](network-protection.md) は、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐのに役立ちます。

この記事は、機能を有効にし、テスト サイトに案内することで、ネットワーク保護を評価するのに役立ちます。 この評価記事のサイトは悪意のあるものではない。 悪意のあるふりをする特別に作成された Web サイトです。 サイトは、ユーザーが悪意のあるサイトまたはドメインにアクセスした場合に発生する動作をレプリケートします。

> [!TIP]
> また、Microsoft Defender Testground の Web サイトを demo.wd.microsoft.com 他 [の保護](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 機能がどのように機能するのか確認できます。

## <a name="enable-network-protection-in-audit-mode"></a>監査モードでネットワーク保護を有効にする

監査モードでネットワーク保護を有効にして、ブロックされた IP アドレスとドメインを確認します。 業務用アプリに影響を与えなかったり、ブロックが発生する頻度を確認できます。

1. **[powershell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**
2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>(偽の) 悪意のあるドメインにアクセスする

1. ユーザー Internet Explorer、Google Chrome、または任意の他のブラウザーを開きます。

1. [https://smartscreentestratings2.net](https://smartscreentestratings2.net) に移動します。

ネットワーク接続が許可され、テスト メッセージが表示されます。

![[接続がブロックされました] という通知の例: IT 管理者が、このネットワークWindows セキュリティをブロックする原因になります。 IT ヘルプ デスクにお問い合わせください。](images/np-notif.png)

## <a name="review-network-protection-events-in-windows-event-viewer"></a>イベント ビューアーでネットワーク保護イベントWindows確認する

ブロックされているアプリを確認するには、Microsoft-Windows-Windows-Defender/Operational ログでイベント ビューアーを開き、イベント ID 1125 をフィルター処理します。 次の表に、すべてのネットワーク保護イベントを示します。

| イベント ID | 提供/ソース | Description |
|-|-|-|
|5007 | Windows Defender (運用) | 設定が変更された場合のイベント |
|1125 | Windows Defender (運用) | ネットワーク接続が監査された場合のイベント |
|1126 | Windows Defender (運用) | ネットワーク接続がブロックされた場合のイベント |

## <a name="see-also"></a>関連項目

* [ネットワーク保護](network-protection.md)
* [ネットワーク保護を有効にする](enable-network-protection.md)
* [ネットワーク保護のトラブルシューティング](troubleshoot-np.md)
