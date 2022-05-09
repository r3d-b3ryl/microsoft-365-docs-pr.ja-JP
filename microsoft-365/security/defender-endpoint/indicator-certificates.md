---
title: 証明書に基づいてインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義する証明書に基づいてインジケーターを作成します。
keywords: ioc, 証明書, 証明書, 管理, 許可, ブロック, ブロック, クリーン, 悪意のある, ファイル ハッシュ, IP アドレス, URL, ドメイン
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
ms.openlocfilehash: 7140b5714dd3660fe8dead37c3b6341d026fbb7c
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61166868"
---
# <a name="create-indicators-based-on-certificates"></a>証明書に基づいてインジケーターを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

証明書のインジケーターを作成できます。 一般的なユース ケースには、次のようなものがあります。

- [攻撃面の縮小ルール](attack-surface-reduction.md)や[フォルダー アクセスの制御](controlled-folders.md)など、ブロック テクノロジを展開する必要があるが、許可リストに証明書を追加して署名されたアプリケーションからの動作を許可する必要があるシナリオ。
- 組織全体で特定の署名済みアプリケーションの使用をブロックする。 アプリケーションの証明書をブロックするインジケーターを作成することで、WINDOWS DEFENDER AV はファイルの実行 (ブロックと修復) を防止し、自動調査と修復は同じように動作します。

## <a name="before-you-begin"></a>開始する前に

証明書のインジケーターを作成する前に、次の要件を理解しておくことが重要です。

- この機能は、組織がWindows Defender ウイルス対策を使用し、クラウドベースの保護が有効になっている場合に使用できます。 詳細については、「 [クラウドベースの保護を管理する](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)」を参照してください。
- マルウェア対策クライアントバージョンは、4.18.1901.x 以降である必要があります。
- Windows 10、バージョン 1703 以降、Windows Server 2019、Windows Server 2016、Windows Server 2012 R2、Windows Server 2022 のマシンでサポートされます。
    
    >[!NOTE]
    >この機能を機能させるには、「オンボード Windows サーバー」の手順に従って[、Windows Server 2016とWindows Server 2012](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) R2 をオンボードする必要があります。 

- ウイルスと脅威の保護の定義は最新の状態である必要があります。
- この機能は現在、入力をサポートしています。CER または .PEM ファイル拡張子。

> [!IMPORTANT]
>
> - 有効なリーフ証明書は、有効な証明書パスを持ち、Microsoft によって信頼されているルート証明機関 (CA) にチェーンされている必要がある署名証明書です。 または、カスタム (自己署名証明書) 証明書は、クライアントによって信頼されている限り使用できます (ルート CA 証明書は、ローカル コンピューターの "信頼されたルート証明機関" の下にインストールされます)。
> - 許可/ブロック証明書 IOC の子または親は、許可/ブロック IoC 機能には含まれず、リーフ証明書のみがサポートされます。
> - Microsoft 署名済み証明書はブロックできません。

## <a name="create-an-indicator-for-certificates-from-the-settings-page"></a>設定ページから証明書のインジケーターを作成します。

> [!IMPORTANT]
> 証明書 IoC の作成と削除には、最大で 3 時間かかる場合があります。

1. ナビゲーション ウィンドウで、([**ルール**] **で) 設定** \> **エンドポイント** \> **インジケーター** を選択します。

2. [ **インジケーターの追加]** を選択します。

3. 次の詳細を指定します。
   - インジケーター - エンティティの詳細を指定し、インジケーターの有効期限を定義します。
   - アクション - 実行するアクションを指定し、説明を入力します。
   - スコープ - マシン グループのスコープを定義します。

4. [概要] タブで詳細を確認し、[ **保存**] をクリックします。

## <a name="related-topics"></a>関連項目

- [インジケーターの作成](manage-indicators.md)
- [ファイルのインジケーターを作成 ](indicator-file.md)
- [IP および URL/ドメインのインジケーターを作成](indicator-ip-domain.md)
- [インジケーターの管理](indicator-manage.md)
