---
title: ネットワーク保護を評価する
description: 保護対象の一般的なシナリオをテストして、ネットワーク保護がどのように機能するかを確認します。
keywords: ネットワーク保護、悪用、悪意のある Web サイト、IP、ドメイン、ドメイン、評価、テスト、デモ
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
ms.collection:
- M365-security-compliance
ms.date: ''
ms.openlocfilehash: 2826c623437760d86aad54e4aa36900bdad68082
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66603948"
---
# <a name="evaluate-network-protection"></a>ネットワーク保護を評価する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[ネットワーク保護](network-protection.md) は、従業員がアプリケーションを使用して、フィッシング詐欺、悪用、その他の悪意のあるコンテンツをインターネット上でホストする可能性のある危険なドメインにアクセスできないようにするのに役立ちます。

この記事は、この機能を有効にしてテスト サイトに誘導することで、ネットワーク保護を評価するのに役立ちます。 この評価記事のサイトは悪意はありません。 これらは、悪意のあるふりをする特別に作成された Web サイトです。 サイトは、ユーザーが悪意のあるサイトまたはドメインにアクセスした場合に発生する動作をレプリケートします。

> [!TIP]
> また、 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) の Microsoft Defender デモ シナリオ Web サイトにアクセスして、他の保護機能の動作を確認することもできます。

> [!NOTE]
> demo.wd.microsoft.com の Defender for Endpoint デモ サイトは非推奨であり、将来削除される予定です。

## <a name="enable-network-protection-in-audit-mode"></a>監査モードでネットワーク保護を有効にする

監査モードでネットワーク保護を有効にして、ブロックされた IP アドレスとドメインを確認します。 基幹業務アプリに影響しないようにしたり、ブロックが発生する頻度を把握したりできます。

1. [スタート] メニューに **「powershell**」と入力し、**Windows PowerShell** 右クリックして **[管理者として実行**] を選択します
2. 次のコマンドレットを入力します。

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

### <a name="visit-a-fake-malicious-domain"></a>(偽の) 悪意のあるドメインにアクセスする

1. Internet Explorer、Google Chrome、または任意の他のブラウザーを開きます。

2. [https://smartscreentestratings2.net](https://smartscreentestratings2.net) に移動します。

    ネットワーク接続が許可され、テスト メッセージが表示されます。
    
    :::image type="content" source="images/np-notif.png" alt-text="接続のブロック通知" lightbox="images/np-notif.png":::

> [!NOTE]
> サイトがネットワーク保護によってブロックされている場合でも、ネットワーク接続は成功する可能性があります。 詳細については、「 [ネットワーク保護と TCP の 3 方向ハンドシェイク](network-protection.md#network-protection-and-the-tcp-three-way-handshake)」を参照してください。

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Windows イベント ビューアーでネットワーク保護イベントを確認する

ブロックされたアプリを確認するには、イベント ビューアーを開き、Microsoft-Windows-Windows Defender/運用ログでイベント ID 1125 をフィルター処理します。 次の表に、すべてのネットワーク保護イベントを示します。

| イベント ID | 提供/ソース | 説明 |
|---|---|---|
| 5007 | Windows Defender (運用) | 設定が変更された場合のイベント |
| 1125 | Windows Defender (運用) | ネットワーク接続が監査されたときのイベント |
| 1126 | Windows Defender (運用) | ネットワーク接続がブロックされたときのイベント |

## <a name="see-also"></a>関連項目

- [ネットワーク保護](network-protection.md)

- [ネットワーク保護と TCP の 3 方向ハンドシェイク](network-protection.md#network-protection-and-the-tcp-three-way-handshake)

- [ネットワーク保護を有効にする](enable-network-protection.md)

- [ネットワーク保護のトラブルシューティング](troubleshoot-np.md)
