---
title: SharePoint Online モダン ポータル サイトの制限
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 10/9/2019
audience: Admin
ms.topic: interactive-tutorial
ms.service: o365-administration
ms.localizationpriority: medium
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
description: SharePointおよび外部エンドポイントへの呼び出しの制限など、SharePoint Online の最新サイトのパフォーマンスに関する推奨事項について説明します。
ms.openlocfilehash: a0163cd808ce3eb25da8d1c94fb27ed9d238d75a
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65091151"
---
# <a name="sharepoint-online-modern-portal-site-limits"></a>SharePoint Online モダン ポータル サイトの制限

この記事では、SharePoint Online のモダン ポータル サイトのパフォーマンスに関する推奨事項について説明します。 この記事のガイドラインを使用して、最新のポータル サイトのパフォーマンスを最適化し、一般的なパフォーマンスの問題を回避します。

## <a name="performance-considerations-for-modern-portal-sites"></a>モダン ポータル サイトのパフォーマンスに関する考慮事項

パフォーマンスの最適化の観点からは、最新のポータル サイトを一意にする特性がいくつかあります。 SharePoint Online のコラボレーション サイトとポータル サイトの主な違いはスケールです。 ポータル サイトは一般に、コラボレーション サイトよりも多くのユーザーに対してより多くのページ ビューを提供することが期待されており、静的コンテンツが多く、編集可能なリソースが少なくなる可能性があります。 さらに、モダン サイトのアーキテクチャは、ページのレンダリングとコードの実行に関連する処理の大部分がサーバーではなくクライアントで行われるという点で、従来のサイトとは異なります。

最新のポータル サイトのパフォーマンスの最適化は、主に、いくつかの全体的な目標に焦点を当てています。

- 各サイト ページのコンポーネントの合計サイズを小さくする
- イメージ、スタイルシート、スクリプトなどの一般的な静的ファイルのホスティングをCDNにオフロードする
- SharePointと外部エンドポイントへの呼び出しを必要なもののみに制限する
- 同じコンテンツに対する重複する要求を回避する

この記事のガイドラインの多くは、SharePoint Online への呼び出しを最小限に抑え、最適化することに重点を置きます。 ページが読み込まれるたびに繰り返し呼び出すと、変更されていない場合でも毎回サービスから情報が取得されるため、ユーザーのパフォーマンスに影響します。 そのため、SharePointに対する要求は、すべてのユーザーに共通の呼び出しまたは個々のユーザーに必要な呼び出しとして分類できます。 これら 2 つの呼び出しカテゴリの結果は、ユーザー エクスペリエンスを最適化するためにキャッシュする必要があります。

>[!NOTE]
>[SharePointのページ診断ツール](./page-diagnostics-for-spo.md)を開始点として使用して、SharePoint Online サイト ページの特定のパフォーマンス メトリックを分析します。

## <a name="modern-portal-site-limits-and-recommendations"></a>モダン ポータル サイトの制限と推奨事項

|**制限**|**推奨される最大値**|**注**|
|:-----|:-----|:-----|:-----|
|ページとニュース アイテム  <br/> |サイトごとに 5,000 件  <br/> |モダン ポータル サイトのページ数とニュース アイテム数を 5,000 未満に制限することをお勧めします。  <br/> |
|ページ上の Web パーツ  <br/> |1 ページあたり 20 個  <br/> |既定の Microsoft Web パーツとカスタム Web パーツの両方を含め、1 ページあたり 20 個以下の合計 Web パーツを使用することをお勧めします。 <br/> 詳細については、「[SharePoint Online モダン サイト ページで Web パーツのパフォーマンスを最適化](modern-web-part-optimization.md)する」を参照してください。  <br/> |
|ページ上の動的 Web パーツ  <br/> |ページあたり 4  <br/> |最新データをフェッチするためにSharePointする 1 つ以上のクエリを行う動的 Web パーツは、ページあたり 4 に制限する必要があります。 _ニュース_ Web パーツは、動的 Web パーツの例です。 <br/> 詳細については、「[SharePoint Online モダン サイト ページで Web パーツのパフォーマンスを最適化](modern-web-part-optimization.md)する」を参照してください。    <br/> |
|セキュリティ グループ  <br/> |サイトあたり 20 個  <br/> |セキュリティ グループの数は、最新のポータル サイトの多くのクエリのスケールに影響します。 セキュリティ グループの数をできるだけ小さいセットに制限し、サイトあたり 20 個以下にすることをお勧めします。  <br/> |
|サイト ナビゲーション内のアイテム  <br/> |サイトあたり 100 個  <br/> |サイト ナビゲーションには 100 個未満のアイテムを追加することをお勧めします。また、すぐに使用できるナビゲーション コントロールを使用することをお勧めします。  <br/> 詳細については、「[SharePoint Online モダン サイト ページでページの太さを最適化](modern-page-weight-optimization.md)する」を参照してください。 <br/> |
|最大イメージ サイズ  <br/> |イメージあたり 300 Kb  <br/> |イメージのサイズを 300 kb 以下に制限し、CDNを使用してイメージ、スタイルシート、スクリプトをホストすることをお勧めします。 <br/>詳細については、「[SharePoint Online のモダン サイト ページで画像を最適化](modern-image-optimization.md)する」と「[SharePoint Online でOffice 365 Content Delivery Network (CDN) を使用する」を参照](use-microsoft-365-cdn-with-spo.md)してください。  <br/> |
|編集権限を持つユーザー  <br/> |サイトあたり 200 ユーザー  <br/> |SharePoint ポータル サイトは、コンテンツを表示および使用するために最適化されています。 編集アクセス許可は追加のコントロールをダウンロードするため、それらのユーザーに対して実行速度が低下するため、ポータルの編集アクセス許可は制限されたユーザー グループに限定する必要があります。 そのため、編集アクセス許可を持つユーザーの数が多すぎると、全体的なエクスペリエンスに影響します。 <br/> |
|サード パーティ製の iFrame  <br/> |1 ページあたり 2  <br/> |iFrame は、javascript、CSS、フレームワーク要素など、関連付けられているすべてのコンテンツを含む個別の外部ページを読み込むため、予期しない速度が低下します。 iFrame を使用する必要がある場合は、ページあたりの数を 2 以下に制限します。<br/> 詳細については、「[SharePoint Online のモダンおよびクラシック発行サイト ページで iFrame を最適化](modern-iframe-optimization.md)する」を参照してください。 <br/> |
|UPA サービスへの呼び出し  <br/> |ユーザーあたり 1 時間あたり 1  <br/> |UPA (ユーザー プロファイル アプリケーション) サービスへの _要求_ ごとの呼び出しは行われないことをお勧めします。 [Microsoft Graph API](/graph/call-api)と [PageContext](/javascript/api/sp-page-context/pagecontext) を使用して、ユーザー情報のクエリを実行できます。  <br/> UPA サービス呼び出しが必要な場合は、必要に応じて 1 回の呼び出しを行い、同じセッションで再利用するために情報をキャッシュします。 |
|分類サービスへの呼び出し  <br/> |ユーザー 1 時間あたり 5 人  <br/> |Taxonomy サービスへの _要求ごとの_ 呼び出しは行われないことをお勧めします。 分類サービス呼び出しが必要な場合は、同じセッションで再利用するために情報をキャッシュします。 <br/> 詳細については、「[SharePoint Online のモダンおよびクラシック発行サイト ページでページ呼び出しを最適化](modern-page-call-optimization.md)する」を参照してください。 <br/> |

## <a name="related-topics"></a>関連項目

[正常なSharePoint ポータルの作成](/sharepoint/portal-health)

[SharePoint Online のパフォーマンスをチューニングする](tune-sharepoint-online-performance.md)

[Office 365 のパフォーマンスをチューニングする](tune-microsoft-365-performance.md)

[SharePoint Online の制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)

[SharePoint のモダン エクスペリエンスにおけるパフォーマンス](/sharepoint/modern-experience-performance)

[SharePoint Online ポータル パフォーマンス ガイダンス](/sharepoint/dev/solution-guidance/portal-performance)
