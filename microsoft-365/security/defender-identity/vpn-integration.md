---
title: Microsoft Defender for Identity VPN integration in Microsoft 365 Defender
description: Microsoft Defender for Identity 用 VPN を統合して会計情報を収集する方法について説明します。Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: a5c45ecda43b32e37f7309b9a2de33810d60bd15
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64469165"
---
# <a name="defender-for-identity-vpn-integration-in-microsoft-365-defender"></a>Defender for Identity VPN の統合 (Microsoft 365 Defender

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、VPN を Microsoft [Defender for Identity](/defender-for-identity) に統合する方法について説明[します。Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center)。

>[!IMPORTANT]
>Id ポータルの Defender Microsoft 365 Defenderの場所<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"></a>から、一部のオプションと詳細が変更されました。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細をお読みください。

[!INCLUDE [Product long](includes/product-long.md)] VPN ソリューションから会計情報を収集できます。 構成されている場合、ユーザーのプロファイル ページには、接続の発信元の IP アドレスや場所など、VPN 接続からの情報が含まれます。 これにより、ユーザー アクティビティに関する追加情報と、異常な VPN 接続の新しい検出を提供することで、調査プロセスを補完します。 外部 IP アドレスを場所に解決するための呼び出しは匿名です。 この呼び出しでは、個人識別子は送信されません。

[!INCLUDE [Product short](includes/product-short.md)] センサーに転送される RADIUS アカウンティング イベントをリッスンして VPN ソリューションと統合 [!INCLUDE [Product short](includes/product-short.md)] します。 このメカニズムは、標準の RADIUS アカウンティング ([RFC 2866](https://tools.ietf.org/html/rfc2866)) に基づいており、次の VPN ベンダーがサポートされています。

- Microsoft
- F5
- チェック ポイント
- Cisco ASA

## <a name="prerequisites"></a>前提条件

VPN 統合を有効にするには、次のパラメーターを設定してください。

- センサーまたはスタンドアロン センサーでポート UDP 1813 [!INCLUDE [Product short](includes/product-short.md)] [!INCLUDE [Product short](includes/product-short.md)] を開きます。

> [!NOTE]
>
> - Radius **Accounting**[!INCLUDE [Product short](includes/product-short.md)] を有効にすると、センサーは事前にプロビジョニングされた Windows ファイアウォール ポリシー **[!INCLUDE [Product long](includes/product-long.md)]** Sensor を有効にして、ポート UDP 1813 で着信 RADIUS アカウンティングを許可します。
> - VPN 統合は、連邦情報処理標準 (FIPS) に準拠している環境ではサポートされません。

次の例では、Microsoft Routing および Remote Access Server (RRAS) を使用して VPN 構成プロセスを説明します。

サードパーティの VPN ソリューションを使用している場合は、RADIUS アカウンティングを有効にする方法の手順については、そのドキュメントを参照してください。

## <a name="configure-radius-accounting-on-the-vpn-system"></a>VPN システムで RADIUS アカウンティングを構成する

RRAS サーバーで次の手順を実行します。

1. [ルーティングと **リモート アクセス] コンソールを開** きます。
1. サーバー名を右クリックし、[プロパティ] を **選択します**。
1. [セキュリティ **] タブの** [アカウンティング プロバイダー **] で、[** RADIUS アカウンティング] **を選択し、[** 構成] を **選択します**。

   :::image type="content" source="../../media/defender-identity/radius-setup.png" alt-text="RADIUS セットアップ" lightbox="../../media/defender-identity/radius-setup.png":::

1. [**RADIUS サーバーの追加]** ウィンドウで、最[!INCLUDE [Product short](includes/product-short.md)]も近いセンサー (ネットワーク接続を持つ) のサーバー名を入力します。 高可用性を実現するには、RADIUS サーバーとして [!INCLUDE [Product short](includes/product-short.md)] 追加のセンサーを追加できます。 [ **ポート]** で、既定の 1813 が構成されていることを確認します。 [ **変更] を** 選択し、英数字の新しい共有シークレット文字列を入力します。 後で構成中に入力する必要がある場合は、新しい共有シークレット文字列に注意 [!INCLUDE [Product short](includes/product-short.md)] してください。 [ **RADIUS アカウントの送信] および [アカウンティング** オフ メッセージの送信] ボックスをオンにし、[開いているすべてのダイアログ ボックスで **[OK** ] を選択します。

   :::image type="content" source="../../media/defender-identity/vpn-set-accounting.png" alt-text="VPN セットアップ" lightbox="../../media/defender-identity/vpn-set-accounting.png":::

## <a name="configure-vpn-in-defender-for-identity"></a>Id の Defender で VPN を構成する

[!INCLUDE [Product short](includes/product-short.md)] コンピューターがネットワークに接続する場所をプロファイルし、疑わしい VPN 接続を検出するのに役立つ VPN データを収集します。

次の手順で [!INCLUDE [Product short](includes/product-short.md)] VPN データを構成Microsoft 365 Defender。

1. [<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>] で、[id **] 設定** に **移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[設定] メニュー項目の [Id] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

1. [ **VPN] を選択します**。
1. [**半径の会計を有効** にする]  を選択し、RRAS VPN Server で以前に構成した共有シークレットを入力します。 その後、**[保存]** を選択します。

   :::image type="content" source="../../media/defender-identity/vpn-integration.png" alt-text="VPN 統合" lightbox="../../media/defender-identity/vpn-integration.png":::

これを有効にすると、すべての Defender for Identity センサーがポート 1813 で RADIUS アカウンティング イベントをリッスンし、VPN のセットアップが完了します。

Defender for Identity センサーが VPN イベントを受信し、処理のために Defender for Identity クラウド サービスに送信した後、エンティティ プロファイルはアクセスされた VPN の場所を示し、プロファイル内のアクティビティは場所を示します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender でアラートを調査する](../defender/investigate-alerts.md)
