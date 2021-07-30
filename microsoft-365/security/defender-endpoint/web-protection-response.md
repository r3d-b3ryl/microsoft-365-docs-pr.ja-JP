---
title: Microsoft Defender for Endpoint の Web 脅威に対応する
description: 悪意のある Web サイトや望ましくない Web サイトに関連するアラートに応答します。 Web 脅威保護がエンド ユーザーに Web ブラウザーを介して通知し、通知を受け取Windows理解する
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
ms.openlocfilehash: 6439088073b9b6cfd86988a395028d64a8981a99
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53651665"
---
# <a name="respond-to-web-threats"></a>Web の脅威への対応

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Microsoft Defender for Endpoint の Web 保護を使用すると、カスタム インジケーター リスト内の悪意のある Web サイトや Web サイトに関連するアラートを効率的に調査して対応できます。

## <a name="view-web-threat-alerts"></a>Web 脅威アラートの表示

Microsoft Defender for Endpoint は、悪意のある Web アクティビティまたは疑 [わしい](manage-alerts.md) Web アクティビティに関する次のアラートを生成します。

- **ネットワーク保護によって** ブロックされる疑わしい接続 : このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内のWeb サイトへのアクセスがブロック モードでネットワーク保護によって停止された場合 *に生成* されます。
- **ネットワーク保護によって検出** された疑わしい接続 : このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内の Web サイトにアクセスしようとした場合に、監査専用モードでネットワーク保護によって検出 *された場合に生成* されます。

各アラートは、次の情報を提供します。

- ブロックされた Web サイトにアクセスしようとしたデバイス
- Web 要求の送信に使用されるアプリケーションまたはプログラム
- カスタム インジケーター リスト内の悪意のある URL または URL
- レスポンダーに推奨されるアクション

![Web 脅威保護に関連するアラートのイメージ](images/wtp-alert.png)

> [!NOTE]
> Microsoft Defender for Endpoint は、アラートの量を減らすために、同じデバイス上の同じドメインの Web 脅威検出を毎日 1 つのアラートに統合します。 1 つのアラートだけが生成され [、Web 保護レポートにカウントされます](web-protection-monitoring.md)。

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

## <a name="web-browser-and-windows-notifications-for-end-users"></a>エンド ユーザー向Windows Web ブラウザーと通知

Microsoft Defender for Endpoint の Web 保護を使用すると、エンド ユーザーが悪意のある Web サイトや望ましくない web サイトにアクセスする場合、Microsoft Edgeブラウザーを使用してアクセスできません。 ブロックはネットワーク保護によって実行されます [の](network-protection.md)で、Web ブラウザーから一般的なエラーが表示されます。 また、ユーザーからの通知も表示Windows。

![403 Microsoft Edgeを示すエラーの画像と、Windowsでブロックされた通知 Web の脅威 ](images/wtp-browser-blocking-page.png)
 *Microsoft Edge*

![Chrome でセキュリティで保護された接続の警告とブロックされた通知 Web Windowsを示す ](images/wtp-chrome-browser-blocking-page.png)
 *Chrome Web ブラウザーの画像*

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
