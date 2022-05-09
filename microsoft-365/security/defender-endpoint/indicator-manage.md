---
title: インジケーターの管理
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義するファイル ハッシュ、IP アドレス、URL、またはドメインのインジケーターを管理します。
keywords: import, インジケーター, リスト, ioc, csv, 管理, 許可, ブロック, クリーン, 悪意のある, ファイル ハッシュ, IP アドレス, URL, ドメイン
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2f66106dd39b9cd1f590148addfdd2cae89748c6
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61938482"
---
# <a name="manage-indicators"></a>インジケーターの管理

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

1. ナビゲーション ウィンドウで、([**ルール**] **で) 設定** \> **エンドポイント** \> **インジケーター** を選択します。

2. 管理するエンティティの種類のタブを選択します。

3. インジケーターの詳細を更新し、[ **保存]** をクリックするか、一覧からエンティティを削除する場合は [ **削除** ] ボタンをクリックします。

## <a name="import-a-list-of-iocs"></a>IoC の一覧をインポートする

インジケーターの属性、実行するアクション、その他の詳細を定義する CSV ファイルをアップロードすることもできます。

サポートされている列属性を把握するには、サンプル CSV をダウンロードします。

1. ナビゲーション ウィンドウで、([**ルール**] **で) 設定** \> **エンドポイント** \> **インジケーター** を選択します。

2. インジケーターをインポートするエンティティの種類のタブを選択します。

3. [ **インポート** \> **の選択] ファイルを選択します**。

4. **[インポート]** を選択します。 インポートするすべてのファイルに対してこれを行います。

5. **[完了]** を選択します。

> [!NOTE]
> バッチごとにアップロードできるインジケーターは 500 個のみです。

次の表に、サポートされているパラメーターを示します。

パラメーター|種類|説明
:---|:---|:---
indicatorType|列挙|インジケーターの種類。 指定できる値は、"FileSha1"、"FileSha256"、"IpAddress"、"DomainName"、"Url" です。 **必須**
indicatorValue|String|[インジケーター](ti-indicator.md) エンティティの ID。 **必須**
action|列挙|インジケーターが組織内で検出された場合に実行されるアクション。 指定できる値は、"Alert"、"AlertAndBlock"、"Allowed" です。 **必須**
title|String|インジケーター アラートのタイトル。 **必須**
説明|String| インジケーターの説明。 **必須**
expirationTime|DateTimeOffset|YYYY-MM-DDTHH:MM:SS.0Z 形式のインジケーターの有効期限。 このインジケーターは、有効期限が経過すると削除され、有効期限の時刻に何が起こるかは秒 (SS) の値で発生します。 **Optional**
severity|列挙|インジケーターの重大度。 指定できる値は、"Informational"、"Low"、"Medium"、"High" です。 **Optional**
recommendedActions|String|TI インジケーター アラート推奨アクション。 **Optional**
rbacGroupNames|String|インジケーターが適用される RBAC グループ名のコンマ区切りリスト。 **Optional**
category|String|アラートのカテゴリ。 例として、実行と資格情報へのアクセスがあります。 **Optional**
mitretechniques|String|MITRE 手法のコード/ID (コンマ区切り)。 詳細については、[Enterpriseの戦術に関する説明を](https://attack.mitre.org/tactics/enterprise/)参照してください。 **オプション** MITRE 手法の場合は、カテゴリに値を追加することをお勧めします。
GenerateAlert|String|アラートを生成するかどうかを指定します。 指定できる値は True または False です。 **Optional**



> [!NOTE]
> IP アドレスのクラスレス Inter-Domain ルーティング (CIDR) 表記はサポートされていません。
詳細については、「[MICROSOFT DEFENDER FOR ENDPOINTアラート カテゴリが MITRE ATT&CK!に揃った状態になった](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)」を参照してください。

## <a name="see-also"></a>関連項目

- [インジケーターの作成](manage-indicators.md)
- [ファイルのインジケーターを作成 ](indicator-file.md)
- [IP および URL/ドメインのインジケーターを作成](indicator-ip-domain.md)
- [証明書に基づいてインジケーターを作成する](indicator-certificates.md)
