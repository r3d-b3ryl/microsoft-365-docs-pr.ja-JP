---
title: Microsoft 365 Defenderでセンサーの正常性と設定をMicrosoft Defender for Identityする
description: Microsoft Defender for Identity センサーを構成し、Microsoft 365 Defenderで正常性を監視する方法について説明します
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: 246fd5ca880ca2d7e187283d06f19d071f5d7e0e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468525"
---
# <a name="microsoft-defender-for-identity-sensor-health-and-settings-in-microsoft-365-defender"></a>Microsoft 365 Defenderでセンサーの正常性と設定をMicrosoft Defender for Identityする

**適用対象:**

- Microsoft 365 Defender
- Defender for Identity

この記事では、[Microsoft 365 DefenderでMicrosoft Defender for Identityセンサーを](/defender-for-identity)構成および監視する方法について説明[します](/microsoft-365/security/defender/overview-security-center)。

>[!IMPORTANT]
>Microsoft 365 Defenderとの統合の一環として、一部のオプションと詳細は Defender for Identity ポータルの場所から変更されています。 使い慣れた機能と新機能の両方を見つける場所については、以下の詳細を参照してください。

## <a name="view-defender-for-identity-sensor-settings-and-status"></a>Defender for Identity センサーの設定と状態を表示する

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>で、[**設定**] に移動し、[**ID] に移動します**。

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="[設定] ページの [ID] オプション" lightbox="../../media/defender-identity/settings-identities.png":::

1. [ **センサー** ] ページを選択すると、Defender for Identity センサーがすべて表示されます。 各センサーには、その名前、ドメイン メンバーシップ、バージョン番号が表示されます。更新を遅延する必要がある場合は、サービスの状態、更新状態、正常性状態、正常性の問題の数、およびセンサーが作成されたタイミングが表示されます。

    [![[センサー] ページ。](../../media/defender-identity/sensor-page.png)](../../media/defender-identity/sensor-page.png#lightbox)

    >[!NOTE]
    >Defender for Identity ポータルでは、センサーの設定と正常性情報が別々の場所にありました。 Microsoft 365 Defenderでは、同じページに表示されることに注意してください。

1. **[フィルター**] を選択した場合は、使用可能なフィルターを選択できます。 その後、各フィルターで、表示するセンサーを選択できます。

    [![センサー フィルター。](../../media/defender-identity/sensor-filters.png)](../../media/defender-identity/sensor-filters.png#lightbox)

    :::image type="content" source="../../media/defender-identity/filtered-sensor.png" alt-text="フィルター処理されたセンサー" lightbox="../../media/defender-identity/filtered-sensor.png":::

1. いずれかのセンサーを選択すると、センサーとその正常性状態に関する情報が表示されるウィンドウが表示されます。

    [![センサーの詳細。](../../media/defender-identity/sensor-details.png)](../../media/defender-identity/sensor-details.png#lightbox)

1. いずれかの正常性の問題を選択すると、その詳細を示すウィンドウが表示されます。 終了した問題を選択した場合は、ここからもう一度開くことができます。

   :::image type="content" source="../../media/defender-identity/issue-details.png" alt-text="問題の詳細" lightbox="../../media/defender-identity/issue-details.png":::
    

1. [センサーの **管理**] を選択すると、センサーの詳細を構成できるウィンドウが開きます。

   :::image type="content" source="../../media/defender-identity/manage-sensor.png" alt-text="センサーの管理オプション" lightbox="../../media/defender-identity/manage-sensor.png":::

   :::image type="content" source="../../media/defender-identity/configure-sensor-details.png" alt-text="センサーの設定を構成するページ" lightbox="../../media/defender-identity/configure-sensor-details.png":::

1. [ **センサー** ] ページで、[エクスポート] を選択して、センサーの一覧を.csv ファイルに **エクスポート** できます。

   :::image type="content" source="../../media/defender-identity/export-sensors.png" alt-text="センサーのエクスポート リスト" lightbox="../../media/defender-identity/export-sensors.png":::

## <a name="add-a-sensor"></a>センサーを追加する

[ **センサー** ] ページから、新しいセンサーを追加できます。

1. [ **センサーの追加]** を選択します。

   :::image type="content" source="../../media/defender-identity/add-sensor.png" alt-text="センサーの追加オプション" lightbox="../../media/defender-identity/add-sensor.png":::

1. ウィンドウが開き、センサー インストーラーと生成されたアクセス キーをダウンロードするボタンが表示されます。

   :::image type="content" source="../../media/defender-identity/installer-access-key.png" alt-text="インストーラーをダウンロードしてキーを再生成するオプション" lightbox="../../media/defender-identity/installer-access-key.png":::

1. [ **インストーラーのダウンロード** ] を選択して、パッケージをローカルに保存します。 zip ファイルには、次のファイルが含まれています。

    - Defender for Identity センサー インストーラー

    - Defender for Identity クラウド サービスに接続するために必要な情報を含む構成設定ファイル

1. **アクセス キー** をコピーします。 Defender for Identity センサーが Defender for Identity インスタンスに接続するには、アクセス キーが必要です。 アクセス キーは、センサーの展開用のワンタイム パスワードです。その後、認証と TLS 暗号化に証明書を使用してすべての通信が実行されます。 新しいアクセス **キーを再生成** する必要がある場合は、[再生成キー] ボタンを使用します。 以前にデプロイされたセンサーには影響しません。これは、センサーの初期登録にのみ使用されるためです。

1. Defender for Identity センサーをインストールする専用サーバーまたはドメイン コントローラーにパッケージをコピーします。

## <a name="see-also"></a>関連項目

- [Defender for Identity セキュリティ アラートを管理する](manage-security-alerts.md)
