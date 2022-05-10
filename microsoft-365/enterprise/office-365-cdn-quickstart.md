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

組み込みの **Office 365 Content Delivery Network (CDN)** を使用して、静的アセット (イメージ、JavaScript、スタイルシート、WOFF ファイル) をホストして、SharePoint Online ページのパフォーマンスを向上させることができます。 Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。 また、Office 365 CDNでは、圧縮と HTTP パイプラインを強化するために HTTP/2 プロトコルを使用します。 Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

詳細なガイダンスについては、「[SharePoint Online でOffice 365 Content Delivery Network (CDN) を使用する](use-microsoft-365-cdn-with-spo.md)」を参照してください。

>[!NOTE]
>Office 365 CDNは、運用環境 (世界) クラウド内のテナントでのみ使用できます。 現在、米国政府、中国、ドイツのクラウドのテナントは Office 365 CDN をサポートしていません。

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>SharePoint ツールのページ診断を使用して、CDN内にない項目を識別する

SharePoint ツール ブラウザー拡張機能 **のページ診断** を使用すると、CDNの配信元に追加できるSharePoint Online ページのアセットを簡単に一覧表示できます。

**SharePoint用のページ診断ツール** は、新しいMicrosoft Edge (<https://www.microsoft.com/edge>) ブラウザーと Chrome ブラウザーのブラウザー拡張機能であり、SharePoint Online モダン ポータルページとクラシック発行サイト ページの両方を分析します。 このツールでは、定義されている一連のパフォーマンス条件に対するページのパフォーマンスを示す分析済みの各ページのレポートが作成されます。 SharePoint 用ページ診断ツールのインストール方法と詳細については、「[SharePoint Online 用ページ診断ツールを使用する](./page-diagnostics-for-spo.md)」を参照してください。

SharePoint Online ページで [SharePoint 用ページ診断] ツールを実行すると、[**診断テスト**] タブをクリックして、CDNによってホストされていない資産の一覧を表示できます。 これらのアセットは、次のスクリーンショットに示すように **、見出しContent Delivery Network (CDN) チェック** の下に一覧表示されます。

![ページ診断。](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>ページ診断ツールは SharePoint Online でのみ機能し、SharePoint システム ページでは使用できません。

## <a name="cdn-overview"></a>CDNの概要

Office 365 CDNは、イメージや javascript ファイルなどのアクセス頻度の高いオブジェクトを高速グローバル ネットワーク上に分散し、ページ読み込み時間を短縮し、ユーザーにできるだけ近いホストオブジェクトにアクセスできるようにすることで、ユーザーのパフォーマンスを最適化するように設計されています。 CDNは _、配信元_ と呼ばれる場所からアセットをフェッチします。 配信元には、URL でアクセスできるSharePoint サイト、ドキュメント ライブラリ、またはフォルダーを指定できます。

Office 365 CDNは、次の 2 つの基本的な型に分かれています。

- **パブリック CDN** は、JS (JavaScript)、CSS (スタイルシート)、Web フォント ファイル (WOFF、WOFF2)、および会社のロゴなどの非独自のイメージに使用するように設計されています。
- **プライベート CDN** は、画像 (PNG、JPG、JPEG など) に使用するように設計されています。

組織のパブリックオリジンとプライベート配信元の両方を選択できます。 ほとんどの組織では、2 つの組み合わせを実装することを選択します。 パブリック オプションとプライベート オプションはどちらも同様のパフォーマンス向上を提供しますが、それぞれに固有の属性と利点があります。 パブリックオリジンとプライベート CDN配信元の詳細については、「[各配信元をパブリックまたはプライベートにするかどうかを選択する」を](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)参照してください。

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>既定の構成でパブリックおよびプライベート CDNを有効にする方法
テナントCDN設定を変更する前に、組織のコンプライアンス、セキュリティ、およびプライバシー ポリシーが満たされていることを確認する必要があります。

詳細な構成設定、またはCDNを既に有効にしていて、別の場所 (配信元) を追加する場合は、「SharePoint [Online Management Shell を使用してOffice 365 CDNを設定して構成](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)する」セクションを参照してください。

SharePoint Online Management Shell を使用してテナントにConnectします。

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

組織で既定の構成でパブリック配信元とプライベート配信元の両方を使用できるようにするには、次のコマンドを入力します。

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

これらのコマンドレットの出力は、次のようになります。

![Set-SPOTenantCdnEnabled の出力。](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>関連項目

[SharePoint Online のページ診断ツールを使用する](./page-diagnostics-for-spo.md)

[SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用](use-microsoft-365-cdn-with-spo.md)

[Content Delivery Network](./content-delivery-networks.md)

[Office 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[SharePoint パフォーマンス シリーズ - Office 365 CDN ビデオ シリーズ](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
