---
title: Web 驚異から組織を保護する
description: Microsoft Defender for Endpoint の Web 保護と、組織を保護する方法について説明します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 90775af14d78092159d2b92736abce56a961416e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159176"
---
# <a name="protect-your-organization-against-web-threats"></a>Web 驚異から組織を保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 脅威保護は [、Defender](web-protection-overview.md) for Endpoint の Web 保護の一部です。 ネットワーク保護 [を使用して](network-protection.md) 、Web の脅威からデバイスを保護します。 Chrome や Firefox Microsoft Edge や人気のあるサード パーティ製ブラウザーと統合することで、Web 脅威保護は Web プロキシなしで Web 脅威を停止し、離れた場所やオンプレミスの間にデバイスを保護できます。 Web 脅威保護は、フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、カスタム インジケーター リストでブロックしたサイトへのアクセスを [停止します](manage-indicators.md)。

> [!NOTE]
> デバイスが新しいカスタム インジケーターを受信するには、最大で 1 時間かかる場合があります。

## <a name="prerequisites"></a>前提条件

Web 保護は、ネットワーク保護を使用して、ブラウザーおよびサード パーティMicrosoft Edge Web ブラウザーで Web 閲覧のセキュリティを提供します。

デバイスでネットワーク保護を有効にする方法:

- 展開または再展開する前に **、ネットワーク保護を有効&、Web** ネットワーク保護の下で Defender for Endpoint セキュリティ ベースラインを編集します。 [Defender for Endpoint セキュリティ ベースラインの確認と割り当てについて説明します。](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Intune デバイス構成、SCCM、グループ ポリシー、または MDM ソリューションを使用してネットワーク保護を有効にします。 [ネットワーク保護の有効化の詳細](enable-network-protection.md)

> [!NOTE]
> ネットワーク保護を [監査のみ] **に設定すると**、ブロックは使用できません。 また、悪意のある Web サイトや望ましくない Web サイトにアクセスしようとする試みを検出してログに記録できるのは、Microsoft Edgeのみです。

## <a name="configure-web-threat-protection"></a>Web 脅威保護の構成

次の手順では、管理者センターを使用して Web 脅威保護を構成Microsoft エンドポイント マネージャー説明します。

1. 管理センター ( ) Microsoft エンドポイント マネージャーに [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 移動し、サインインします。
 
2. [ **エンドポイント セキュリティ攻撃** \> **の表面縮小] を** 選択し、[+ **ポリシーの作成] を選択します**。

3. プラットフォームを選択します(Windows 10 **など)、Web** 保護プロファイルを選択し、[**作成**] を **選択します**。 

4. [基本] **タブで** 、名前と説明を指定し、[次へ] を **選択します**。

5. [構成設定 **] タブで****、[Web Protection] を展開** し、設定を指定し、[次へ] を **選択します**。

   - [ネットワーク **保護を有効にする]** **を [有効] に設定** して、Web 保護を有効にします。 または、ネットワーク保護を監査モード **に設定** して、環境での動作を確認することもできます。 監査モードでは、ネットワーク保護によってユーザーがサイトやドメインにアクセスできませんが、検出はイベントとして追跡されます。 
   - 潜在的なフィッシング詐欺や悪意のあるソフトウェアからユーザーを保護するには、[ユーザーに SmartScreen を要求する] を **[はいMicrosoft Edge 従来版** する] を **オンにします**。
   - 悪意のある可能性のあるサイトに関する警告をユーザーがバイパスするのを防ぐには、[悪意のあるサイトへのアクセスをブロックする] を [は **い** ] に **設定します**。
   - ユーザーが警告をバイパスして未確認のファイルをダウンロードできない場合は、[未確認ファイルのダウンロードをブロック **する]** を [はい] に設定 **します**。 

6. [スコープ **タグ] タブ** で、組織でスコープ タグを使用している場合は、[+ スコープ タグの選択] を選択し、[次へ] を **選択します**。 (スコープ タグを使用していない場合は、[次へ] を **選択** します。スコープ タグの詳細については [、「Use role-based access control (RBAC)](/mem/intune/fundamentals/scope-tags)and scope tags for distributed IT」を参照してください。

7. [割 **り当て] タブ** で、Web 保護ポリシーを受信するユーザーとデバイスを指定し、[次へ] を **選択します**。

8. [確認 **と作成] タブで** 、ポリシー設定を確認し、[作成] を **選択します**。

## <a name="related-topics"></a>関連トピック

- [Web 保護の概要](web-protection-overview.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威への対応](web-protection-response.md)
- [ネットワーク保護](network-protection.md)
