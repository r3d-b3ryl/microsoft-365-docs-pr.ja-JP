---
title: Office 365 Content Delivery Network (CDN) クイック スタート
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 01/13/2022
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network (CDN) クイック スタート
ms.openlocfilehash: b0684fdfd8583ae6780cb23d47dc697582ae133b
ms.sourcegitcommit: af73b93a904ce8604be319e8dc7cadaf65d50534
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/31/2022
ms.locfileid: "62281437"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Content Delivery Network (CDN) クイック スタート

組み込みの Office 365 Content Delivery Network **(CDN)** を使用して静的アセット (イメージ、JavaScript、スタイルシート、WOFF ファイル) をホストし、SharePoint Online ページのパフォーマンスを向上させることができます。 Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。 また、このOffice 365 CDN HTTP/2 プロトコルを使用して、圧縮と HTTP パイプライン処理を強化します。 Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

詳細な情報ガイダンスについては、「オンラインで Office 365 Content Delivery Network [(CDN) をSharePointしてください](use-microsoft-365-cdn-with-spo.md)。

>[!NOTE]
>このOffice 365 CDNは、(世界中の) 実稼働クラウドのテナントでのみ使用できます。 現在、米国政府、中国、ドイツのクラウドのテナントは Office 365 CDN をサポートしていません。

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>[ページ診断] ツールを使用SharePoint、ページに含CDN

SharePoint ツール ブラウザー拡張機能 **の** ページ診断を使用すると、SharePoint Online ページ内のアセットを簡単に一覧表示し、CDN オリジンに追加できます。

**SharePoint のページ** 診断ツールは、SharePoint Online モダン ポータルと従来の発行サイト ページの両方を分析する新しい Microsoft Edge (<https://www.microsoft.com/edge>) ブラウザーと Chrome ブラウザーのブラウザー拡張機能です。 このツールでは、定義されている一連のパフォーマンス条件に対するページのパフォーマンスを示す分析済みの各ページのレポートが作成されます。 SharePoint 用ページ診断ツールのインストール方法と詳細については、「[SharePoint Online 用ページ診断ツールを使用する](./page-diagnostics-for-spo.md)」を参照してください。

SharePoint Online ページで [SharePoint のページ診断] ツールを実行すると、[診断テスト] タブをクリックして、CDN でホストされていないアセットの一覧を表示できます。 これらのアセットは、下のスクリーンショットに示Content Delivery Network **(CDN) チェック** の下に表示されます。

![ページ診断。](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>ページ診断ツールは SharePoint Online でのみ機能し、SharePoint システム ページでは使用できません。

## <a name="cdn-overview"></a>CDN概要

Office 365 CDN は、画像や javascript ファイルなどの頻繁にアクセスするオブジェクトを高速グローバル ネットワーク上に分散し、ページの読み込み時間を短縮し、ホストされたオブジェクトへのアクセスをユーザーに可能な限り近く提供することで、ユーザーのパフォーマンスを最適化するように設計されています。 このCDN元と呼ばれる場所からアセットをフェッチ _します_。 オリジンには、URL SharePointアクセスできるサイト、ドキュメント ライブラリ、またはフォルダーを指定できます。

このOffice 365 CDNは、次の 2 つの基本的な型に分けらされています。

- **パブリック CDN** は、JS (JavaScript)、CSS (StyleSheets)、Web フォント ファイル (WOFF、WOFF2)、会社のロゴなどの非専有画像に使用するように設計されています。
- **プライベート CDN** 画像 (PNG、JPG、JPEG など) に使用するように設計されています。

組織のパブリックオリジンとプライベートオリジンの両方を選択できます。 ほとんどの組織では、2 つの組み合わせを実装します。 パブリック オプションとプライベート オプションの両方が同様のパフォーマンス向上を実現しますが、それぞれに固有の属性と利点があります。 パブリックおよびプライベート のオリジンのCDN詳細については、「各オリジンをパブリックまたはプライベートにするかどうかを選択する[」を参照してください](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>既定の構成でパブリック およびプライベート CDNを有効にする方法
テナントの設定を変更するCDN、組織のコンプライアンス、セキュリティ、およびプライバシー ポリシーを満たしている必要があります。

詳細な構成設定については、または CDN を既に有効にし、追加の場所 (発生元) を追加する場合は、「SharePoint Online 管理シェルを使用して Office 365 CDN を設定して構成する[」セクションを参照してください](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)。

Connect管理シェルを使用してテナントSharePointにアクセスします。

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

組織でパブリックオリジンとプライベート オリジンの両方を既定の構成で使用するには、次のコマンドを入力します。

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

これらのコマンドレットの出力は、次のようになります。

![Set-SPOTenantCdnEnabled の出力。](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>関連項目

[オンラインのページ診断ツールを使用SharePointする](./page-diagnostics-for-spo.md)

[SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)

[Content Delivery Network](./content-delivery-networks.md)

[Office 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[SharePoint パフォーマンス シリーズ - Office 365 CDN ビデオ シリーズ](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
