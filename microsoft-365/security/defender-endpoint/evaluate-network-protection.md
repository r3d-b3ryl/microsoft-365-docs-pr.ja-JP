---
title: ネットワーク保護を評価する
description: ネットワーク保護が保護する一般的なシナリオをテストして、ネットワーク保護のしくみを確認します。
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、評価、テスト、デモ
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 2db9df56a858bd069141c2c9389cf232b7feee7c
ms.sourcegitcommit: 6b24f65c987e5ca06e6d5f4fc10804cdbe68b034
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2021
ms.locfileid: "61320745"
---
# <a name="evaluate-network-protection"></a>ネットワーク保護を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[ネットワーク保護](network-protection.md) は、従業員がアプリケーションを使用して、インターネット上でフィッシング詐欺、悪用、その他の悪意のあるコンテンツをホストする可能性のある危険なドメインにアクセスするのを防ぐのに役立ちます。

この記事は、機能を有効にし、テスト サイトに案内することで、ネットワーク保護を評価するのに役立ちます。 この評価記事のサイトは悪意のあるものではない。 悪意のあるふりをする特別に作成された Web サイトです。 サイトは、ユーザーが悪意のあるサイトまたはドメインにアクセスした場合に発生する動作をレプリケートします。

> [!TIP]
> また、Microsoft Defender のデモ シナリオ Web サイトを [参照して](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 、demo.wd.microsoft.com の保護機能がどのように機能するのか確認することもできます。

## <a name="enable-network-protection-in-audit-mode"></a>監査モードでネットワーク保護を有効にする

監査モードでネットワーク保護を有効にして、ブロックされた IP アドレスとドメインを確認します。 業務用アプリに影響を与えなかったり、ブロックが発生する頻度を確認できます。

1. **[powershell]** と入力スタート メニューを **右クリックし**、[管理者Windows PowerShell **実行] を選択します。**
2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>(偽の) 悪意のあるドメインにアクセスする

1. ユーザー Internet Explorer、Google Chrome、または任意の他のブラウザーを開きます。

2. [https://smartscreentestratings2.net](https://smartscreentestratings2.net) に移動します。

    ネットワーク接続が許可され、テスト メッセージが表示されます。
    
    ![[接続がブロックされました] という通知の例: IT 管理者が、このネットワークWindows セキュリティをブロックする原因になります。 IT ヘルプ デスクにお問い合わせください。](images/np-notif.png)

> [!NOTE]
> ネットワーク保護によってサイトがブロックされている場合でも、ネットワーク接続は成功する可能性があります。 詳細については、「ネットワーク保護 [」および「TCP 3 ウェイ ハンドシェイク」を参照してください](network-protection.md#network-protection-and-the-tcp-three-way-handshake)。

## <a name="review-network-protection-events-in-windows-event-viewer"></a>イベント ビューアーでネットワーク保護イベントWindows確認する

ブロックされたアプリを確認するには、Microsoft-Windows-Windows Defender/運用ログでイベント ビューアーを開き、イベント ID 1125 をフィルター処理します。 次の表に、すべてのネットワーク保護イベントを示します。

| イベント ID | 提供/ソース | 説明 |
|---|---|---|
| 5007 | Windows Defender (運用) | 設定が変更された場合のイベント |
| 1125 | Windows Defender (運用) | ネットワーク接続が監査された場合のイベント |
| 1126 | Windows Defender (運用) | ネットワーク接続がブロックされた場合のイベント |

## <a name="see-also"></a>関連項目

- [ネットワーク保護](network-protection.md)

- [ネットワーク保護と TCP 3 ウェイ ハンドシェイク](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [ネットワーク保護を有効にする](enable-network-protection.md)

- [ネットワーク保護のトラブルシューティング](troubleshoot-np.md)
