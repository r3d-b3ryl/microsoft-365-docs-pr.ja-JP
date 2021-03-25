---
title: IPs と URL/ドメインのインジケーターを作成する
ms.reviewer: ''
description: エンティティの検出、防止、および除外を定義する、IPs および URL/ドメインのインジケーターを作成します。
keywords: IP、URL、ドメイン、管理、許可、ブロック、ブロック、クリーン、悪意のある、ファイル ハッシュ、IP アドレス、URL、ドメイン
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d468a77d2c1ab4f1b363e2e91b6e8507a5390d93
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198485"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>IPs と URL/ドメインのインジケーターを作成する 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender for Endpoint は、Microsoft が悪意のある IPS/URL と見なす動作、Windows Defender SmartScreen for Microsoft ブラウザー、および Microsoft 以外のブラウザーやブラウザー外で行われた呼び出しに対するネットワーク保護を通じてブロックできます。

このための脅威インテリジェンス データ セットは、Microsoft によって管理されています。

IP と URL またはドメインのインジケーターを作成することで、独自の脅威インテリジェンスに基づいて、IPs、URL、またはドメインを許可またはブロックできます。 特定のグループが他のグループよりも多かれ少なかれ危険にさらされている場合は、設定ページまたはコンピューター グループを使用してこれを行えます。

> [!NOTE]
> IP アドレスInter-Domainクラスレス ルーティング (CIDR) 表記はサポートされていません。 

### <a name="before-you-begin"></a>はじめに
IPS、URL、またはドメインのインジケーターを作成する前に、次の前提条件を理解することが重要です。
- URL/IP 許可とブロックは、Defender for Endpoint コンポーネントのネットワーク保護をブロック モードで有効にしています。 ネットワーク保護と構成手順の詳細については、「ネットワーク保護を有効 [にする」を参照してください](enable-network-protection.md)。
- マルウェア対策クライアントのバージョンは、4.18.1906.x 以降である必要があります。 
- Windows 10 バージョン 1709 以降のコンピューターでサポートされています。 
- Microsoft Defender Security Center **の [設定] ページ** で[カスタム ネットワーク インジケーター] が有効 **>高度>確認します**。 詳細については、「高度な機能 [」を参照してください](advanced-features.md)。
- iOS でのインジケーターのサポートについては、「カスタム インジケーターの [構成」を参照してください](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)。


> [!IMPORTANT]
> インジケーター リストに追加できるのは外部の AP のみです。 インジケーターは、内部の IPs に対して作成できません。
> Web 保護のシナリオでは、Microsoft Edge の組み込み機能を使用することをお勧めします。 Microsoft Edge はネットワーク保護 [を利用して](network-protection.md) ネットワーク トラフィックを検査し、TCP、HTTP、HTTPS (TLS) のブロックを許可します。 競合する URL インジケーター ポリシーがある場合は、長いパスが適用されます。 たとえば、URL インジケーター ポリシーは URL インジケーター `https:\\support.microsoft.com/en-us/office` ポリシーよりも優先されます `https:\\support.microsoft.com` 。

> [!NOTE]
> その他のすべてのプロセスでは、Web 保護シナリオでネットワーク保護を活用して検査と実施を行います。 
> - IP は 3 つのプロトコルすべてでサポートされています
> - サポートされている IP アドレスは 1 つのみです (CIDR ブロックまたは IP 範囲なし)
> - 暗号化された URL (フル パス) は、ファースト パーティのブラウザーでのみブロックできます (Internet Explorer エッジ)
> - 暗号化された URL (FQDN のみ) は、ファースト パーティブラウザーの外部でブロックできます (Internet Explorer エッジ)
> - 完全な URL パス ブロックは、ドメイン レベルと暗号化されていないすべての URL に適用できます。
 
> [!NOTE]
> アクションが実行され、URL と IP がブロックされる時間の間に最大 2 時間の待機時間 (通常は少ない) が発生する場合があります。 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>設定ページから、IPs、URL、またはドメインのインジケーターを作成する

1. ナビゲーション ウィンドウで、[設定インジケーター]**を**  >  **選択します**。  

2. [IP アドレス **] タブまたは [URL/ドメイン] タブを選択** します。

3. [アイテム **の追加] を選択します**。

4. 次の詳細を指定します。
   - Indicator - エンティティの詳細を指定し、インジケーターの有効期限を定義します。
   - Action - 実行するアクションを指定し、説明を入力します。
   - Scope - コンピューター グループのスコープを定義します。

5. [概要] タブで詳細を確認し、[保存] を **クリックします**。

## <a name="related-topics"></a>関連項目
- [インジケーターの作成](manage-indicators.md)
- [ファイルのインジケーターを作成する](indicator-file.md)
- [証明書に基づいてインジケーターを作成する](indicator-certificates.md)
- [インジケーターの管理](indicator-manage.md)
