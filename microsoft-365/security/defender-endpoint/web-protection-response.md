---
title: Microsoft Defender for Endpointで Web の脅威に対応する
description: 悪意のある Web サイトや不要な Web サイトに関連するアラートに応答します。 Web 脅威保護が Web ブラウザーとWindows通知を通じてエンド ユーザーに通知する方法を理解する
keywords: Web 保護, Web 脅威保護, Web 閲覧, アラート, 応答, セキュリティ, フィッシング, マルウェア, エクスプロイト, Web サイト, ネットワーク保護, Edge, Internet Explorer, Chrome, Firefox, Web ブラウザー, 通知, エンド ユーザー, Windows通知, ブロック ページ,
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

Microsoft Defender for Endpointの Web 保護を使用すると、カスタム インジケーター リスト内の悪意のある Web サイトや Web サイトに関連するアラートを効率的に調査して対応できます。

## <a name="view-web-threat-alerts"></a>Web 脅威アラートを表示する

Microsoft Defender for Endpoint、悪意のある Web アクティビティまたは疑わしい Web アクティビティに対して次の[アラート](manage-alerts.md)が生成されます。

- **ネットワーク保護によってブロックされた疑わしい接続**: このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内の Web サイトへのアクセス試行が *ブロック* モードでネットワーク保護によって *停止* されたときに生成されます
- **ネットワーク保護によって検出された疑わしい接続**: このアラートは、悪意のある Web サイトまたはカスタム インジケーター リスト内の Web サイトへのアクセス試行が *、監査専用* モードのネットワーク保護によって検出されたときに生成されます。

各アラートには、次の情報が提供されます。

- ブロックされた Web サイトにアクセスしようとしたデバイス
- Web 要求の送信に使用されるアプリケーションまたはプログラム
- カスタム インジケーター リスト内の悪意のある URL または URL
- レスポンダーに推奨されるアクション

:::image type="content" source="images/wtp-alert.png" alt-text="Web 脅威保護に関連するアラート" lightbox="images/wtp-alert.png":::

> [!NOTE]
> アラートの量を減らすために、Microsoft Defender for Endpointは、同じデバイス上の同じドメインの Web 脅威検出を毎日 1 つのアラートに統合します。 1 つのアラートのみが生成され、 [Web 保護レポート](web-protection-monitoring.md)にカウントされます。

## <a name="inspect-website-details"></a>Web サイトの詳細を調べる

アラートで Web サイトの URL またはドメインを選択することで、詳細を確認できます。 これにより、次のようなさまざまな情報を含む特定の URL またはドメインに関するページが開きます。

- Web サイトにアクセスしようとしたデバイス
- Web サイトに関連するインシデントとアラート
- 組織内のイベントで Web サイトが表示された頻度

  :::image type="content" source="images/wtp-website-details.png" alt-text="ドメインまたは URL エンティティの詳細ページ" lightbox="images/wtp-website-details.png":::

[URL またはドメイン エンティティのページの詳細](investigate-domain.md)

## <a name="inspect-the-device"></a>デバイスを調べる

ブロックされた URL にアクセスしようとしたデバイスを確認することもできます。 アラート ページでデバイスの名前を選択すると、デバイスに関する包括的な情報を含むページが開きます。

[デバイス エンティティ ページの詳細](investigate-machines.md)

## <a name="web-browser-and-windows-notifications-for-end-users"></a>エンド ユーザーの Web ブラウザーとWindows通知

Microsoft Defender for Endpointの Web 保護により、エンド ユーザーは、Microsoft Edgeやその他のブラウザーを使用して悪意のある Web サイトや望ましくない Web サイトにアクセスできなくなります。 ブロックは [ネットワーク保護](network-protection.md)によって実行されるため、Web ブラウザーから一般的なエラーが表示されます。 また、Windowsからの通知も表示されます。

:::image type="content" source="images/wtp-browser-blocking-page.png" alt-text="403 エラーを示すMicrosoft EdgeとWindows通知" lightbox="images/wtp-browser-blocking-page.png":::

*Microsoft Edgeでブロックされた Web 脅威*

:::image type="content" source="images/wtp-chrome-browser-blocking-page.png" alt-text="セキュリティで保護された接続の警告とWindows通知を示す Chrome Web ブラウザー" lightbox="images/wtp-chrome-browser-blocking-page.png":::
*Chrome でブロックされた Web 脅威*

## <a name="related-topics"></a>関連項目

- [Web 保護の概要](web-protection-overview.md)
- [Web コンテンツ フィルタリング](web-content-filtering.md)
- [Web の脅威に対する保護](web-threat-protection.md)
- [Web セキュリティの監視](web-protection-monitoring.md)
