---
title: IP および URL/ドメインのインジケーターを作成
ms.reviewer: ''
description: エンティティの検出、防止、除外を定義する IP と URL/ドメインのインジケーターを作成します。
keywords: ip, URL, domain, manage, allowed, block, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: 955f11aa44bd0defb867c25124da7c5a3769c98d
ms.sourcegitcommit: a7cd723fd62b4b0aae9c2c2df04ead3c28180084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65840119"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>IP および URL/ドメインのインジケーターを作成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Defender for Endpoint は、Microsoft が悪意のある IP/URL と見なすもの、Microsoft ブラウザーの SmartScreen のWindows Defender、Microsoft 以外のブラウザーの Network Protection、またはブラウザーの外部で行われた呼び出しを通じてブロックできます。

この脅威インテリジェンス データ セットは、Microsoft によって管理されています。

IP と URL またはドメインのインジケーターを作成することで、独自の脅威インテリジェンスに基づいて IP、URL、またはドメインを許可またはブロックできるようになりました。 危険なアプリを開く場合は、プロンプトでユーザーに警告することもできます。 プロンプトによってアプリの使用が停止されることはありませんが、カスタム メッセージと、アプリの適切な使用方法を説明する会社のページへのリンクを指定できます。 ユーザーは引き続き警告をバイパスし、必要に応じてアプリを引き続き使用できます。

特定のグループが他のグループよりも多かれ少なかれ危険にさらされているとみなす場合は、設定ページまたはマシン グループを使用して行うことができます。

> [!NOTE]
> IP アドレスのクラスレス Inter-Domain ルーティング (CIDR) 表記はサポートされていません。

## <a name="before-you-begin"></a>開始する前に

IPS、URL、またはドメインのインジケーターを作成する前に、次の前提条件を理解しておくことが重要です。

- URL/IP の許可とブロックは、Defender for Endpoint コンポーネントの Network Protection をブロック モードで有効にする必要があります。 Network Protection と構成手順の詳細については、「 [ネットワーク保護を有効にする」を](enable-network-protection.md)参照してください。
- マルウェア対策クライアントバージョンは、4.18.1906.x 以降である必要があります。 
- Windows 10、バージョン 1709 以降、Windows 11、Windows Server 2016、Windows Server 2012 R2、Windows Server 2019、Windows Server 2022、Android およびデバイスをiOSします。

    > [!NOTE]
    > この機能を機能させるには、「オンボード Windows サーバー」の手順に従って[、Windows Server 2016とWindows Server 2012](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) R2 をオンボードする必要があります。

- Microsoft 365 Defender **設定** \> **Advanced 機能****で** \> **カスタム ネットワーク インジケーター** が有効になっていることを確認します。 詳細については、「 [高度な機能」を](advanced-features.md)参照してください。
- iOSに関するインジケーターのサポートについては、[iOSのMicrosoft Defender for Endpointを](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)参照してください。
- Androidのインジケーターのサポートについては、[AndroidのMicrosoft Defender for Endpointを](/microsoft-365/security/defender-endpoint/android-configure#configure-custom-indicators)参照してください。

> [!IMPORTANT]
> インジケーターの一覧に追加できるのは外部 IP のみです。 内部 IP に対してインジケーターを作成することはできません。
> Web 保護のシナリオでは、Microsoft Edgeに組み込まれている機能を使用することをお勧めします。 Microsoft Edge[ネットワーク保護](network-protection.md)を利用してネットワーク トラフィックを検査し、TCP、HTTP、HTTPS (TLS) のブロックを許可します。
> 競合する URL インジケーター ポリシーがある場合は、長いパスが適用されます。 たとえば、URL インジケーター ポリシーは URL インジケーター ポリシー `https://support.microsoft.com/office` `https://support.microsoft.com`よりも優先されます。

> [!NOTE]
> その他のすべてのプロセスでは、Web 保護のシナリオでは、Network Protection を利用して検査と実施を行います。
>
> - IP は、3 つのプロトコルすべてでサポートされています
> - 1 つの IP アドレスのみがサポートされます (CIDR ブロックまたは IP 範囲はありません)。
> - 暗号化された URL (フル パス) は、ファースト パーティのブラウザー (Internet Explorer、Edge) でのみブロックできます
> - 暗号化された URL (FQDN のみ) は、ファースト パーティのブラウザーの外部でブロックできます (Internet Explorer、Edge)
> - 完全な URL パス ブロックは、ドメイン レベルと暗号化されていないすべての URL に適用できます
>
> アクションが実行されてから、URL と IP がブロックされるまでの待機時間は最大 2 時間 (通常は短い) 場合があります。

警告モードを使用する場合は、次のコントロールを構成できます。

**バイパス機能**:

- Edge の [許可] ボタン
- トーストの [許可] ボタン (Microsoft 以外のブラウザー)
- インジケーターのバイパス期間パラメーター
- Microsoft ブラウザーと Microsoft 以外のブラウザー間で適用をバイパスする

**リダイレクト URL**:

- インジケーターのリダイレクト URL パラメーター
- Edge のリダイレクト URL
- トーストのリダイレクト URL (Microsoft 以外のブラウザー)

詳細については、「[Microsoft Defender for Endpointによって検出されたアプリを管理](/cloud-app-security/mde-govern)する」を参照してください。

## <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>設定ページから IP、URL、またはドメインのインジケーターを作成する

1. ナビゲーション ウィンドウで、([**ルール**] **で) 設定** \> **エンドポイント** \> **インジケーター** を選択します。

2. [ **IP アドレス] タブまたは [URL/ドメイン] タブを** 選択します。

3. [ **項目の追加]** を選択します。

4. 次の詳細を指定します。
   - インジケーター - エンティティの詳細を指定し、インジケーターの有効期限を定義します。
   - アクション - 実行するアクションを指定し、説明を入力します。
   - スコープ - マシン グループのスコープを定義します。

5. [概要] タブで詳細を確認し、[ **保存**] をクリックします。

## <a name="related-topics"></a>関連項目

- [インジケーターの作成](manage-indicators.md)
- [ファイルのインジケーターを作成 ](indicator-file.md)
- [証明書に基づいてインジケーターを作成する](indicator-certificates.md)
- [インジケーターの管理](indicator-manage.md)
