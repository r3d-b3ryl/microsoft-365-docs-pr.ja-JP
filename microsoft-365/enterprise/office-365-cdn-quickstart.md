---
title: Office 365 コンテンツ配信ネットワーク (CDN) クイック スタート
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Office 365 コンテンツ配信ネットワーク (CDN) クイック スタート
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921596"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 コンテンツ配信ネットワーク (CDN) クイック スタート

組み込みの Office **365** コンテンツ配信ネットワーク (CDN) を使用して静的アセット (イメージ、JavaScript、スタイルシート、WOFF ファイル) をホストし、SharePoint Online ページのパフォーマンスを向上させることができます。 Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。 また、365 CDN Officeは、圧縮と HTTP パイプライン処理を強化するために HTTP/2 プロトコルを使用します。 Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

詳細な情報ガイダンスについては [、「Use the Office 365 Content Delivery Network (CDN) with SharePoint Online 」を参照してください](use-microsoft-365-cdn-with-spo.md)。

>[!NOTE]
>このOffice 365 CDN は、実稼働 (世界規模) クラウドのテナントでのみ利用できます。 米国政府、中国、ドイツのクラウドのテナントは、現在、365 CDN Officeサポートされていません。

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>SharePoint のページ診断ツールを使用して CDN 内に含めてないアイテムを識別する

**SharePoint** ツール ブラウザー拡張機能のページ診断を使用すると、CDN 配信元に追加できる SharePoint Online ページのアセットを簡単に一覧表示できます。

**SharePoint のページ診断** ツールは、新しい Microsoft Edge (および SharePoint Online モダン ポータルと従来の発行サイト ページの両方を分析する Chrome ブラウザー) のブラウザー https://www.microsoft.com/edge) 拡張機能です。 このツールでは、定義されている一連のパフォーマンス条件に対するページのパフォーマンスを示す分析済みの各ページのレポートが作成されます。 SharePoint 用ページ診断ツールのインストール方法と詳細については、「[SharePoint Online 用ページ診断ツールを使用する](./page-diagnostics-for-spo.md)」を参照してください。

SharePoint Online ページで SharePoint 用ページ診断ツールを実行すると、[診断テスト]タブをクリックすると、CDN によってホストされていないアセットの一覧が表示されます。 これらのアセットは、下のスクリーンショットに示すように、コンテンツ配信 **ネットワーク (CDN) チェック** という見出しの下に表示されます。

![ページ診断](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>ページ診断ツールは SharePoint Online でのみ機能し、SharePoint システム ページでは使用できません。

## <a name="cdn-overview"></a>CDN の概要

Office 365 CDN は、画像や javascript ファイルなどの頻繁にアクセスするオブジェクトを高速グローバル ネットワーク上に分散し、ページの読み込み時間を短縮し、ホストされたオブジェクトへのアクセスをユーザーに可能な限り近く提供することで、ユーザーのパフォーマンスを最適化するように設計されています。 CDN は、配信元と呼ばれる場所からアセットをフェッチ _します_。 オリジンには、URL からアクセスできる SharePoint サイト、ドキュメント ライブラリ、またはフォルダーを指定できます。

365 cdn Officeは、次の 2 つの基本的な種類に分かされています。

- **パブリック CDN** は、JS (JavaScript)、CSS (StyleSheets)、Web フォント ファイル (WOFF、WOFF2)、会社のロゴなどの非専有画像に使用するように設計されています。
- **プライベート CDN** は、画像 (PNG、JPG、JPEG など) に使用するように設計されています。

組織のパブリックオリジンとプライベートオリジンの両方を選択できます。 ほとんどの組織では、2 つの組み合わせを実装します。 パブリック オプションとプライベート オプションの両方が同様のパフォーマンス向上を実現しますが、それぞれに固有の属性と利点があります。 パブリック CDN とプライベート CDN の配信元の詳細については、「各配信元をパブリックまたはプライベートにするかどうかを選択する [」を参照してください](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>既定の構成でパブリック CDN とプライベート CDN を有効にする方法
テナント CDN 設定を変更する前に、組織のコンプライアンス、セキュリティ、およびプライバシー ポリシーを満たしている必要があります。

詳細な構成設定については、または既に CDN を有効にし、追加の場所 (配信元) を追加する場合は、「SharePoint Online 管理シェルを使用して[Office 365 CDN](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)を設定して構成する」セクションを参照してください。

SharePoint Online 管理シェルを使用してテナントに接続します。

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

組織でパブリックオリジンとプライベート オリジンの両方を既定の構成で使用するには、次のコマンドを入力します。

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

これらのコマンドレットの出力は、次のようになります。

![データの出力Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>関連項目

[SharePoint Online のページ診断ツールを使用する](./page-diagnostics-for-spo.md)

[SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)

[Content Delivery Network](./content-delivery-networks.md)

[Office 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[SharePoint Performance Series - Office 365 CDN ビデオ シリーズ](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)