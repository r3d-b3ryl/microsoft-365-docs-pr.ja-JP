---
title: SharePointオンラインモダン ポータル サイトの制限
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_Enterprise
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
description: SharePoint Online のモダン サイトのパフォーマンスに関する推奨事項 (SharePointおよび外部エンドポイントへの呼び出しの制限など) について説明します。
ms.openlocfilehash: 3a7a25d4e14b1e38e28f0e6b6817be3f1b0d4791
ms.sourcegitcommit: a7b289b8cc3a2eb79d5e46f20f2968adc0237da1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "58394806"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePointオンラインモダン ポータル サイトの制限

この記事では、オンラインのモダン ポータル サイトのパフォーマンスSharePointします。 最新のポータル サイトのパフォーマンスを最適化し、一般的なパフォーマンスの問題を回避するには、この記事のガイドラインを使用します。

## <a name="performance-considerations-for-modern-portal-sites"></a>モダン ポータル サイトのパフォーマンスに関する考慮事項

パフォーマンスの最適化の観点から、最新のポータル サイトを一意にするいくつかの特性があります。 オンラインでのコラボレーション サイトとポータル サイトの主な違いはSharePointです。 通常、ポータル サイトは、コラボレーション サイトよりも多くのユーザーに多くのページ ビューを提供すると予想され、静的コンテンツが多く、編集可能なリソースが少ない可能性があります。 また、モダン サイトのアーキテクチャは、ページのレンダリングとコードの実行に関連するほとんどの処理がサーバーではなくクライアントで行うという点で、従来のサイトとは異なります。

最新のポータル サイトのパフォーマンスの最適化は、主にいくつかの全体的な目的に重点を置きます。

- 各サイト ページのコンポーネントの合計サイズを小さくする
- イメージ、スタイルシート、スクリプトなどの一般的な静的ファイルのホスティングを、ユーザーにCDN
- 呼び出しをSharePoint必要なエンドポイントにのみ制限する
- 同じコンテンツに対する重複する要求を回避する

この記事のガイドラインの多くは、オンラインへの呼び出しを最小限に抑え、最適化SharePointしています。 ページが読み込まれるごとに繰り返し呼び出しを行う場合、変更されていない場合でもサービスから情報が取得されるので、ユーザーのパフォーマンスに影響します。 そのため、ユーザーに対する要求SharePoint、すべてのユーザーに共通の呼び出しまたは個々のユーザーに必要な呼び出しとして分類できます。 ユーザー エクスペリエンスを最適化するには、これら 2 つの呼び出しカテゴリの結果をキャッシュする必要があります。

>[!NOTE]
>オンライン サイト[ページで特定](./page-diagnostics-for-spo.md)SharePointパフォーマンス 指標を分析するには、ページ診断ツールSharePoint使用します。

## <a name="modern-portal-site-limits-and-recommendations"></a>最新のポータル サイトの制限と推奨事項

|**制限**|**推奨される最大値**|**メモ**|
|:-----|:-----|:-----|:-----|
|ページとニュース アイテム  <br/> |サイトごとに 5,000 件  <br/> |モダン ポータル サイトのページとニュース アイテムの数を 5,000 以下に制限することをお勧めします。  <br/> |
|ページ上の Web パーツ  <br/> |1 ページあたり 20  <br/> |1 ページあたり 20 以下の Web パーツを使用することをお勧めします。その中には、Microsoft Web パーツとカスタム Web パーツの両方を含める必要があります。 <br/> 詳細については、「Web パーツの[パフォーマンスを最適化する」を参照SharePointモダン サイト ページを参照してください](modern-web-part-optimization.md)。  <br/> |
|ページ上の動的 Web パーツ  <br/> |1 ページあたり 4  <br/> |最新のデータを取得するために 1 つ以上のクエリSharePointする動的 Web パーツは、ページごとに 4 に制限する必要があります。 ニュース _Web_ パーツは、動的 Web パーツの例です。 <br/> 詳細については、「Web パーツの[パフォーマンスを最適化する」を参照SharePointモダン サイト ページを参照してください](modern-web-part-optimization.md)。    <br/> |
|セキュリティ グループ  <br/> |サイトごとに 20  <br/> |セキュリティ グループの数は、モダン ポータル サイトの多くのクエリの規模に影響します。 セキュリティ グループの数は、サイトごとに 20 を超え、可能な限り小さいセットに制限することをお勧めします。  <br/> |
|サイト ナビゲーション内のアイテム  <br/> |サイトごとに 100  <br/> |サイト ナビゲーションに追加するアイテムは 100 未満にし、使用できるナビゲーション コントロールを使用することをお勧めします。  <br/> 詳細については、「オンラインモダン サイト ページのページの重SharePoint[最適化する」を参照してください](modern-page-weight-optimization.md)。 <br/> |
|最大画像サイズ  <br/> |イメージあたり 300 Kb  <br/> |イメージのサイズを 300 kb 以下に制限し、CDN、スタイルシート、スクリプトをホストすることをお勧めします。 <br/>詳細については、「SharePoint [Online](modern-image-optimization.md)モダン サイト ページでイメージを最適化する」および「オンラインで Office 365 Content Delivery Network [(CDN)](use-microsoft-365-cdn-with-spo.md)をSharePointしてください。  <br/> |
|編集権限を持つユーザー  <br/> |サイトあたり 200 人のユーザー  <br/> |SharePointサイトは、コンテンツの表示と使用に最適化されています。 編集アクセス許可は追加のコントロールをダウンロードするため、それらのユーザーの実行速度が低下するため、ポータルの編集アクセス許可は制限されたユーザー グループに制限する必要があります。 したがって、編集権限を持つユーザーの数が多すぎると、全体的なエクスペリエンスに影響します。 <br/> |
|サード パーティ製の iFrames  <br/> |1 ページあたり 2  <br/> |iFrame は、javascript、CSS、フレームワーク要素などの関連付けられたコンテンツを含む別の外部ページを読み込むため、予期しない速度です。 iFrame を使用する必要がある場合は、ページごとにその数を 2 以下に制限します。<br/> 詳細については、「Optimize [iFrames in SharePointモダン](modern-iframe-optimization.md)およびクラシック発行サイト ページ」を参照してください。 <br/> |
|UPA サービスへの呼び出し  <br/> |ユーザー 1 人あたり 1 時間あたり 1  <br/> |UPA (User  Profile Application) サービスに対する要求呼び出しごとに行う必要はありません。 [Microsoft Graph API](/graph/call-api)と[PageContext](/javascript/api/sp-page-context/pagecontext)を使用して、ユーザー情報のクエリを実行できます。  <br/> UPA サービス呼び出しが必要な場合は、必要に応じて 1 回の呼び出しを行い、同じセッションで再利用するために情報をキャッシュします。 |
|分類サービスへの呼び出し  <br/> |1 時間あたりのユーザーあたり 5  <br/> |Taxonomy サービスに対する _要求呼び出し_ ごとに行う必要はありません。 分類サービス呼び出しが必要な場合は、同じセッションで再利用するために情報をキャッシュします。 <br/> 詳細については、「オンラインモダンおよびクラシック発行サイト ページ[でのページSharePointの最適化」を参照してください](modern-page-call-optimization.md)。 <br/> |

## <a name="related-topics"></a>関連項目

[正常なポータルSharePointする](/sharepoint/portal-health)

[SharePoint Online のパフォーマンスをチューニングする](tune-sharepoint-online-performance.md)

[Office 365 のパフォーマンスをチューニングする](tune-microsoft-365-performance.md)

[SharePoint Online の制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[SharePoint のモダン エクスペリエンスにおけるパフォーマンス](/sharepoint/modern-experience-performance)

[SharePoint Online ポータル パフォーマンス ガイダンス](/sharepoint/dev/solution-guidance/portal-performance)
