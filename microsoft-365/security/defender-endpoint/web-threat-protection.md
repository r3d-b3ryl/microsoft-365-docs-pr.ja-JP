---
title: Web 驚異から組織を保護する
description: Microsoft Defender for Endpointでの Web 保護と、組織を保護する方法について説明します。
keywords: Web 保護, Web 脅威保護, Web 閲覧, セキュリティ, フィッシング, マルウェア, エクスプロイト, Web サイト, ネットワーク保護, Edge, Internet Explorer, Chrome, Firefox, Web ブラウザー
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 398fdb8bbfb5bba59fce83e24e7d6cdd496e90bd
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/24/2021
ms.locfileid: "61168344"
---
# <a name="protect-your-organization-against-web-threats"></a>Web 驚異から組織を保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 脅威保護は、Defender for Endpoint の [Web 保護](web-protection-overview.md) の一部です。 [ネットワーク保護](network-protection.md)を使用して、Web の脅威からデバイスを保護します。 Microsoft Edgeや Chrome や Firefox などの一般的なサード パーティのブラウザーと統合することで、Web 脅威保護は Web プロキシなしで Web の脅威を停止し、離れている間やオンプレミスにいる間にデバイスを保護できます。 Web 脅威保護により、フィッシング サイト、マルウェア ベクトル、悪用サイト、信頼されていないサイトまたは低評価サイト、 [カスタム インジケーター リスト](manage-indicators.md)でブロックしたサイトへのアクセスが停止されます。

> [!NOTE]
> デバイスが新しいカスタム インジケーターを受信するには、最大で 1 時間かかる場合があります。

## <a name="prerequisites"></a>前提条件

Web 保護では、ネットワーク保護を使用して、Microsoft Edgeおよびサードパーティの Web ブラウザーで Web 閲覧のセキュリティを提供します。

デバイスでネットワーク保護を有効にするには、

- **Web & Network Protection** で Defender for Endpoint セキュリティ ベースラインを編集し、デプロイまたは再デプロイする前にネットワーク保護を有効にします。 [Defender for Endpoint セキュリティ ベースラインの確認と割り当ての詳細](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- デバイス構成、SCCM、グループ ポリシー、または MDM ソリューションIntune使用してネットワーク保護を有効にします。 [ネットワーク保護を有効にする方法の詳細](enable-network-protection.md)

> [!NOTE]
> ネットワーク保護を **監査のみに** 設定した場合、ブロックは使用できません。 また、悪意のある Web サイトや不要な Web サイトへのアクセス試行を検出してログに記録できるのは、Microsoft Edgeのみです。

## <a name="configure-web-threat-protection"></a>Web 脅威保護を構成する

次の手順では、Microsoft エンドポイント マネージャー管理センターを使用して Web 脅威保護を構成する方法について説明します。

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。
 
2. [ **エンドポイント セキュリティ** \> **攻撃の軽減**] を選択し、[ **+ ポリシーの作成**] を選択します。

3. **Windows 10などの** プラットフォームを選択し、**Web 保護** プロファイルを選択して、[**作成**] を選択します。 

4. [ **基本]** タブで、名前と説明を指定し、[ **次へ**] を選択します。

5. [ **構成設定** ] タブで[ **Web Protection**] を展開し、設定を指定して、[ **次へ**] を選択します。

   - [ **ネットワーク保護を有効にする]** を **[有効] に** 設定して、Web 保護を有効にします。 または、ネットワーク保護を **監査モード** に設定して、環境内での動作を確認することもできます。 監査モードでは、ネットワーク保護によってユーザーがサイトまたはドメインにアクセスすることは禁止されませんが、検出はイベントとして追跡されます。 
   - 潜在的なフィッシング詐欺や悪意のあるソフトウェアからユーザーを保護するには、[**Microsoft Edge 従来版の SmartScreen を必須** にする] を **[はい**] に切り替えます。
   - ユーザーが悪意のある可能性のあるサイトに関する警告をバイパスできないようにするには、[ **悪意のあるサイトへのアクセスをブロックする]** を **[はい**] に設定します。
   - ユーザーが警告をバイパスして未検証ファイルをダウンロードできないようにするには、[ **未検証ファイルのダウンロードをブロックする** ] tl **[はい**] を設定します。 

6. [ **スコープ タグ** ] タブで、組織でスコープ タグを使用している場合は、[ **+ スコープ タグの選択]** を選択し、[ **次へ**] を選択します。 (スコープ タグを使用していない場合は、[ **次へ**] を選択します)。スコープ タグの詳細については、「 [分散 IT にロールベースのアクセス制御 (RBAC) とスコープ タグを使用する」を](/mem/intune/fundamentals/scope-tags)参照してください。

7. [ **割り当て** ] タブで、Web 保護ポリシーを受け取るユーザーとデバイスを指定し、[ **次へ**] を選択します。

8. [ **確認と作成** ] タブで、ポリシー設定を確認し、[ **作成**] を選択します。

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威への対応](web-protection-response.md)
- [ネットワーク保護](network-protection.md)
