---
title: Web の脅威から組織を保護する
description: Microsoft Defender ATP の Web 保護と、組織を保護する方法について説明します。
keywords: Web 保護、Web 脅威保護、Web 閲覧、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3376308988213b84bc7badb96ebacdf706d1ca5f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51063635"
---
# <a name="protect-your-organization-against-web-threats"></a>Web の脅威から組織を保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Web 脅威保護は [、Defender](web-protection-overview.md) for Endpoint の Web 保護の一部です。 ネットワーク保護 [を使用して](network-protection.md) 、Web の脅威からデバイスを保護します。 Microsoft Edge や Chrome や Firefox のような一般的なサード パーティ製ブラウザーと統合することで、Web 脅威保護は Web プロキシなしで Web の脅威を停止し、離れた場所やオンプレミスの間にデバイスを保護できます。 Web 脅威保護は、フィッシング サイト、マルウェア ベクター、悪用サイト、信頼されていないサイトまたは低評価サイト、カスタム インジケーター リストでブロックしたサイトへのアクセスを [停止します](manage-indicators.md)。

>[!Note]
>デバイスが新しい顧客インジケーターを受信するには、最大で 1 時間かかる場合があります。

## <a name="prerequisites"></a>前提条件
Web 保護は、ネットワーク保護を使用して、Microsoft Edge およびサードパーティの Web ブラウザーで Web 閲覧のセキュリティを提供します。

デバイスでネットワーク保護を有効にする方法:
- 展開または再展開する前に **、ネットワーク保護を有効&、Web** ネットワーク保護の下で Defender for Endpoint セキュリティ ベースラインを編集します。 [Defender for Endpoint セキュリティ ベースラインの確認と割り当てについて説明します。](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Intune デバイス構成、SCCM、グループ ポリシー、または MDM ソリューションを使用してネットワーク保護を有効にします。 [ネットワーク保護の有効化の詳細](enable-network-protection.md)  

>[!Note]
>ネットワーク保護を [監査のみ] **に設定すると**、ブロックは使用できません。 また、悪意のある Web サイトや望ましくない Web サイトへのアクセスを検出してログに記録できるのは、Microsoft Edge のみです。

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web 脅威保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
- [Web の脅威に対応する](web-protection-response.md)
- [ネットワーク保護](network-protection.md)
