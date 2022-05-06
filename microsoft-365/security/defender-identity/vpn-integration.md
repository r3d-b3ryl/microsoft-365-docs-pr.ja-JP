---
title: Microsoft 365 Defenderでの VPN の統合をMicrosoft Defender for Identityする
description: Microsoft 365 DefenderでMicrosoft Defender for Identity用の VPN を統合して会計情報を収集する方法について説明します
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
# <a name="defender-for-identity-vpn-integration-in-microsoft-365-defender"></a>Microsoft 365 Defenderでの Defender for Identity VPN の統合

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、Microsoft 365 Defenderで VPN と [Microsoft Defender for Identity](/defender-for-identity)を統合する方法について説明[します](/microsoft-365/security/defender/overview-security-center)。

>[!IMPORTANT]
><a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>との統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

[!INCLUDE [Product long](includes/product-long.md)] は、VPN ソリューションから会計情報を収集できます。 構成すると、ユーザーのプロファイル ページには、VPN 接続からの情報 (IP アドレスや接続の発信場所など) が含まれます。 これにより、ユーザー アクティビティに関する追加情報と、異常な VPN 接続の新しい検出が提供され、調査プロセスが補完されます。 外部 IP アドレスを場所に解決する呼び出しは匿名です。 この呼び出しでは、個人識別子は送信されません。

[!INCLUDE [Product short](includes/product-short.md)] は、センサーに転送された RADIUS アカウンティング イベントをリッスンすることで、VPN ソリューションと統合されます [!INCLUDE [Product short](includes/product-short.md)] 。 このメカニズムは標準 RADIUS アカウンティング ([RFC 2866](https://tools.ietf.org/html/rfc2866)) に基づいており、次の VPN ベンダーがサポートされています。

- Microsoft
- F5
- Check Point
- Cisco ASA

## <a name="prerequisites"></a>前提条件

VPN 統合を有効にするには、次のパラメーターを設定してください。

- センサーまたは[!INCLUDE [Product short](includes/product-short.md)]スタンドアロン センサーで[!INCLUDE [Product short](includes/product-short.md)]ポート UDP 1813 を開きます。

> [!NOTE]
>
> - **Radius Accounting** を有効にすると、[!INCLUDE [Product short](includes/product-short.md)]センサーは、ポート UDP 1813 で着信 RADIUS アカウンティングを許可するように **、センサーと呼ばれる[!INCLUDE [Product long](includes/product-long.md)]** 事前プロビジョニングされたWindowsファイアウォール ポリシーを有効にします。
> - VPN 統合は、連邦情報処理標準 (FIPS) に準拠している環境ではサポートされていません

次の例では、Microsoft ルーティングとリモート アクセス サーバー (RRAS) を使用して、VPN 構成プロセスを説明します。

サード パーティの VPN ソリューションを使用している場合は、RADIUS アカウンティングを有効にする方法の手順については、そのドキュメントを参照してください。

## <a name="configure-radius-accounting-on-the-vpn-system"></a>VPN システムで RADIUS アカウンティングを構成する

RRAS サーバーで次の手順を実行します。

1. **ルーティングコンソールとリモート アクセス** コンソールを開きます。
1. サーバー名を右クリックし、[ **プロパティ**] を選択します。
1. [ **セキュリティ** ] タブの [ **会計プロバイダー**] で[ **RADIUS 会計** ] を選択し、[構成] を選択 **します**。

   :::image type="content" source="../../media/defender-identity/radius-setup.png" alt-text="RADIUS セットアップ" lightbox="../../media/defender-identity/radius-setup.png":::

1. [**RADIUS サーバーの追加]** ウィンドウで、最も[!INCLUDE [Product short](includes/product-short.md)]近いセンサー (ネットワーク接続を持つ) の **サーバー名** を入力します。 高可用性を実現するために、RADIUS サーバーとしてセンサーを追加 [!INCLUDE [Product short](includes/product-short.md)] できます。 [ **ポート**] で、既定値の 1813 が構成されていることを確認します。 [ **変更** ] を選択し、英数字の新しい共有シークレット文字列を入力します。 新しい共有シークレット文字列は、後で構成中 [!INCLUDE [Product short](includes/product-short.md)] に入力する必要があるため、メモしておきます。 **[RADIUS アカウントの送信] および [会計オフ] メッセージ** ボックスをオンにし、開いているすべてのダイアログ ボックスで **[OK] を選択します**。

   :::image type="content" source="../../media/defender-identity/vpn-set-accounting.png" alt-text="VPN のセットアップ" lightbox="../../media/defender-identity/vpn-set-accounting.png":::

## <a name="configure-vpn-in-defender-for-identity"></a>Defender for Identity で VPN を構成する

[!INCLUDE [Product short](includes/product-short.md)] は、コンピューターがネットワークに接続する場所をプロファイリングし、疑わしい VPN 接続を検出するのに役立つ VPN データを収集します。

Microsoft 365 Defenderで [!INCLUDE [Product short](includes/product-short.md)] VPN データを構成するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**設定**] に移動し、[**ID] に移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[設定] メニュー項目の下にある [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

1. [ **VPN**] を選択します。
1. [ **RADIUS アカウンティングを有効にする]** を選択し、RRAS VPN Server で以前に構成した **共有シークレット** を入力します。 その後、**[保存]** を選択します。

   :::image type="content" source="../../media/defender-identity/vpn-integration.png" alt-text="VPN 統合" lightbox="../../media/defender-identity/vpn-integration.png":::

これが有効になると、すべての Defender for Identity センサーがポート 1813 で RADIUS アカウンティング イベントをリッスンし、VPN のセットアップが完了します。

Defender for Identity センサーが VPN イベントを受信し、処理のために Defender for Identity クラウド サービスに送信すると、エンティティ プロファイルは個別のアクセスされた VPN の場所を示し、プロファイル内のアクティビティは場所を示します。

## <a name="see-also"></a>関連項目

- [Microsoft 365 Defender でアラートを調査する](../defender/investigate-alerts.md)
