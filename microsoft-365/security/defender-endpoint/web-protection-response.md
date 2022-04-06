---
title: Microsoft Defender for Endpoint の Web 脅威に対応する
description: 悪意のある Web サイトや望ましくない Web サイトに関連するアラートに応答します。 Web 脅威保護がエンド ユーザーに Web ブラウザーを介して通知し、通知を受け取る方法Windows理解する
keywords: Web 保護、Web 脅威保護、Web 閲覧、アラート、応答、セキュリティ、フィッシング、マルウェア、悪用、Web サイト、ネットワーク保護、エッジ、Internet Explorer、Chrome、Firefox、Web ブラウザー、通知、エンド ユーザー、Windows 通知、ブロック ページ、
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
ms.openlocfilehash: 3a7202c6e522441ecbbfd738d3533a242c966f8c
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64467535"
---
# <a name="respond-to-web-threats"></a>Web の脅威への対応

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Microsoft Defender for Endpoint の Web 保護を使用すると、カスタム インジケーター リスト内の悪意のある Web サイトや Web サイトに関連するアラートを効率的に調査して対応できます。

## <a name="view-web-threat-alerts"></a>Web 脅威アラートの表示

Microsoft Defender for Endpoint は、悪意のある Web アクティビティまたは疑 [わしい](manage-alerts.md) Web アクティビティに関する次のアラートを生成します。

- **ネットワーク保護によって** ブロックされる疑わしい接続: このアラートは、カスタム インジケーター リスト内の悪意のある Web サイトまたは Web サイトへのアクセスがブロック  モードでネットワーク保護によって停止された場合 *に生成* されます。
- **ネットワーク保護によって検出** された疑わしい接続: このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内の Web サイトにアクセスしようとした場合に、監査専用モードでネットワーク保護によって検出された場合 *に生成* されます。

各アラートは、次の情報を提供します。

- ブロックされた Web サイトにアクセスしようとしたデバイス
- Web 要求の送信に使用されるアプリケーションまたはプログラム
- カスタム インジケーター リスト内の悪意のある URL または URL
- レスポンダーに推奨されるアクション

:::image type="content" source="images/wtp-alert.png" alt-text="Web 脅威保護に関連するアラート" lightbox="images/wtp-alert.png":::

> [!NOTE]
> Microsoft Defender for Endpoint は、アラートの量を減らすために、同じデバイス上の同じドメインの Web 脅威検出を毎日 1 つのアラートに統合します。 1 つのアラートだけが生成され、 [Web 保護レポートにカウントされます](web-protection-monitoring.md)。

## <a name="inspect-website-details"></a>Web サイトの詳細を検査する

アラートで Web サイトの URL またはドメインを選択すると、より深く掘り下げできます。 これにより、次に示すさまざまな情報を含む特定の URL またはドメインに関するページが開きます。

- Web サイトにアクセスしようとしたデバイス
- Web サイトに関連するインシデントとアラート
- 組織のイベントで Web サイトが表示された頻度

  :::image type="content" source="images/wtp-website-details.png" alt-text="ドメインまたは URL エンティティの詳細ページ" lightbox="images/wtp-website-details.png":::

[URL またはドメイン エンティティ ページの詳細](investigate-domain.md)

## <a name="inspect-the-device"></a>デバイスを検査する

ブロックされた URL にアクセスしようとしたデバイスを確認することもできます。 アラート ページでデバイスの名前を選択すると、デバイスに関する包括的な情報を含むページが開きます。

[デバイス エンティティ ページの詳細](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>エンド ユーザー向Windows Web ブラウザーと通知

Microsoft Defender for Endpoint の Web 保護を使用すると、エンド ユーザーが悪意のある Web サイトや望ましくない web サイトにアクセスする場合は、Microsoft Edgeブラウザーを使用してアクセスできません。 ブロックはネットワーク保護によって実行 [されるの](network-protection.md)で、Web ブラウザーから一般的なエラーが表示されます。 また、ユーザーからの通知も表示Windows。

:::image type="content" source="images/wtp-browser-blocking-page.png" alt-text="403 Microsoft Edgeを示すメッセージと、エラー通知Windowsします。" lightbox="images/wtp-browser-blocking-page.png":::

*Web の脅威がブロックされているMicrosoft Edge*

:::image type="content" source="images/wtp-chrome-browser-blocking-page.png" alt-text="セキュリティで保護された接続の警告を示す Chrome web ブラウザーと、セキュリティで保護Windows通知" lightbox="images/wtp-chrome-browser-blocking-page.png":::
*Chrome でブロックされた Web の脅威*

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
