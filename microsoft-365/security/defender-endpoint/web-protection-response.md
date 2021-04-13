---
title: Microsoft Defender for Endpoint の Web 脅威に対応する
description: 悪意のある Web サイトや望ましくない Web サイトに関連するアラートに応答します。 Web 脅威保護が Web ブラウザーと Windows 通知を通じてエンド ユーザーに通知する方法を理解する
keywords: Web 保護、Web 脅威保護、Web 閲覧、アラート、応答、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー、通知、エンド ユーザー、Windows 通知、ブロック ページ、
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
ms.openlocfilehash: 110b379863b4c6e23c947c56faf831e136231237
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688479"
---
# <a name="respond-to-web-threats"></a>Web の脅威への対応

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Microsoft Defender for Endpoint の Web 保護を使用すると、カスタム インジケーター リスト内の悪意のある Web サイトや Web サイトに関連するアラートを効率的に調査して対応できます。

## <a name="view-web-threat-alerts"></a>Web 脅威アラートの表示
Microsoft Defender for Endpoint は、悪意のある Web アクティビティまたは疑 [わしい](manage-alerts.md) Web アクティビティに関する次のアラートを生成します。
- **ネットワーク保護によって** ブロックされる疑わしい接続 - このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内のWeb サイトへのアクセスがブロック モードでネットワーク保護によって停止された場合 *に生成* されます。
- **ネットワーク保護によって検出** された疑わしい接続 - このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内の Web サイトにアクセスしようとした場合に、監査専用モードでネットワーク保護によって *検出された場合に生成* されます。

各アラートは、次の情報を提供します。 
- ブロックされた Web サイトにアクセスしようとしたデバイス
- Web 要求の送信に使用されるアプリケーションまたはプログラム
- カスタム インジケーター リスト内の悪意のある URL または URL
- レスポンダーに推奨されるアクション

![Web 脅威保護に関連するアラートのイメージ](images/wtp-alert.png)

>[!Note]
>Microsoft Defender for Endpoint は、アラートの量を減らすために、同じデバイス上の同じドメインの Web 脅威検出を毎日 1 つのアラートに統合します。 1 つのアラートだけが生成され [、Web 保護レポートにカウントされます](web-protection-monitoring.md)。

## <a name="inspect-website-details"></a>Web サイトの詳細を検査する
アラートで Web サイトの URL またはドメインを選択すると、より深く掘り下げできます。 これにより、次に示すさまざまな情報を含む特定の URL またはドメインに関するページが開きます。
- Web サイトにアクセスしようとしたデバイス
- Web サイトに関連するインシデントとアラート
- 組織のイベントで Web サイトが表示された頻度

    ![ドメインまたは URL エンティティの詳細ページのイメージ](images/wtp-website-details.png)

[URL またはドメイン エンティティ ページの詳細](investigate-domain.md)

## <a name="inspect-the-device"></a>デバイスを検査する
ブロックされた URL にアクセスしようとしたデバイスを確認することもできます。 アラート ページでデバイスの名前を選択すると、デバイスに関する包括的な情報を含むページが開きます。

[デバイス エンティティ ページの詳細](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>エンド ユーザー向け Web ブラウザーと Windows 通知

Microsoft Defender for Endpoint の Web 保護を使用すると、エンド ユーザーが Microsoft Edge や他のブラウザーを使用して悪意のある Web サイトや望ましくない Web サイトにアクセスすることを防止できます。 ブロックはネットワーク保護によって実行されます [の](network-protection.md)で、Web ブラウザーから一般的なエラーが表示されます。 また、Windows からの通知も表示されます。

![403 エラーと Microsoft Edge でブロックされている Windows 通知 Web の脅威を示す ](images/wtp-browser-blocking-page.png)
 *Microsoft Edge の画像*

![Chrome でセキュリティで保護された接続警告と Windows 通知 Web の脅威がブロックされている ](images/wtp-chrome-browser-blocking-page.png)
 *Chrome Web ブラウザーの画像*

## <a name="related-topics"></a>関連項目
- [Web 保護の概要](web-protection-overview.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
