---
title: Web 脅威から組織を保護する
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 124abd254b8e8155ad60d400fede3419e754c83d
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53649841"
---
# <a name="protect-your-organization-against-web-threats"></a>Web 脅威から組織を保護する

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

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威への対応](web-protection-response.md)
- [ネットワーク保護](network-protection.md)
