---
title: オンラインでOffice 365 Content Delivery Network (CDN) をSharePointする
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/13/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: オンライン アセットの配信をOffice 365 Content Delivery Network (CDN) を使用する方法SharePointします。
ms.openlocfilehash: 494f0574707693f7d36fa2e1c61ee942e4c088a6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210513"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用

組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的資産をホストすることで、SharePoint Online ページのパフォーマンスを向上させることができます。 Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。 また、このOffice 365 CDN [HTTP/2 プロトコル](https://en.wikipedia.org/wiki/HTTP/2)を使用して、圧縮と HTTP パイプライン処理を強化します。 Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

> [!NOTE]
> Office 365 CDN は、**本番** (ワールドワイド) クラウドのテナントのみが利用できます。 現在、米国政府、中国、ドイツのクラウドのテナントは Office 365 CDN をサポートしていません。

Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。 Office 365 CDN でホストするコンテンツの種類に応じて、**公開**、**非公開**、またはその両方の元の場所を追加できます。 パブリック [オリジンとプライベートオリジン](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) の違いの詳細については、「各オリジンをパブリックまたはプライベートにするかどうかを選択する」を参照してください。

![Office 365 CDN概念図を参照してください。](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN の概念図")

既に CDN の動作方法に精通している場合は、テナントに対してユーザー設定を有効にするには、いくつかの手順Office 365 CDN必要があります。 このトピックでは、方法について説明します。 静的アセットのホスティングを開始する方法の詳細については、次の記事を参照してください。

> [!TIP]
> Office 365 と一緒に使用できる Microsoft ホスト型 CDN は、特殊な使用シナリオに使用できますが、Office 365 CDN の範囲を外れたため、このトピックでは説明しません。 詳細については、「その他の [Microsoft CDN」を参照してください](content-delivery-networks.md#other-microsoft-cdns)。

 **[ネットワークの計画 [とパフォーマンスの](./network-planning-and-performance.md)調整] に戻Office 365。**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>オンラインでのユーザーの操作Office 365 CDNのSharePoint概要

組織のOffice 365 CDNを設定するには、次の基本的な手順を実行します。

+ [アプリケーションの展開を計画Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [サーバーでホストする静的アセットを決定CDN。](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [アセットを格納する場所を決定します](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。 この場所は、サイト、SharePoint、またはフォルダーの 1 つであり、原点と呼 _ばれる場所です_。
  + [各オリジンをパブリックまたはプライベートにするかどうかを選択します](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。 パブリック型とプライベート型の両方の複数のオリジンを追加できます。

+ PowerShell またはオンライン CLI CDNを使用して、サーバーサーバーをSharePoint構成する

  + [オンライン管理シェルを使用してCDNを設定SharePoint構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [PnP PowerShell を使用してCDN設定および構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [CLI を使用してCDN設定および構成Office 365します。](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  この手順を完了すると、次の機能が実行されます。

  + 組織のCDNを有効にしました。
  + 各オリジンをパブリックまたはプライベートとして識別するオリジンを追加しました。

セットアップが完了したら、次の方法で時間の[Office 365 CDNを管理](use-microsoft-365-cdn-with-spo.md#CDNManage)できます。

+ アセットの追加、更新、および削除
+ 原点の追加と削除
+ ポリシー CDN構成する
+ 必要に応じて、サーバーを無効CDN

最後に[、「リソース](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)アセットCDN使用して、パブリックとプライベートの両方のCDNアセットにアクセスする方法について学習します。

一[般的な問題の解決Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)については、「トラブルシューティング」を参照してください。

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>アプリケーションの展開を計画Office 365 CDN

テナントのOffice 365 CDNをOffice 365前に、計画プロセスの一部として次の要素を考慮する必要があります。

  + [サーバーでホストする静的アセットを決定CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [アセットの保存場所を決定する](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [各オリジンをパブリックまたはプライベートにするかどうかを選択する](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>サーバーでホストする静的アセットを決定CDN

一般に、CDN は静的アセット、またはあまり頻繁に変更しないアセットをホストする場合に最も効果的です。 経験則として、次の条件の一部またはすべてが満たされているファイルを特定します。

+ ページに埋め込まれた静的ファイル (スクリプトや画像など) で、ページの読み込み時間に大きな増分影響を与える可能性がある
+ 実行可能ファイルやインストール ファイルのような大きなファイル
+ クライアント側コードをサポートするリソース ライブラリ

たとえば、サイト イメージやスクリプトのように繰り返し要求される小さなファイルは、サイトレンダリングのパフォーマンスを大幅に向上し、CDN オリジンに追加すると、SharePoint Online サイトの負荷を徐々に軽減できます。 インストール実行可能ファイルなどの大きなファイルは、CDN からダウンロードして、パフォーマンスにプラスの影響を与え、SharePoint Online サイトへの負荷を軽減できます。たとえアクセス頻度が高くなくてもです。

ファイル単位でのパフォーマンスの向上は、クライアントが最も近い CDN エンドポイントへの近接性、ローカル ネットワーク上の一時的な状態など、多くの要因に依存します。 多くの静的ファイルは非常に小さく、1 秒Office 365からダウンロードできます。 ただし、Web ページには、累積ダウンロード時間が数秒の埋め込みファイルが多数含まれている場合があります。 これらのファイルをサーバーから提供CDNページの読み込み時間を大幅に短縮できます。 例[については、「ユーザーが提供するパフォーマンスCDN」](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)を参照してください。

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>アセットの保存場所を決定する

このCDN元と呼ばれる場所からアセットをフェッチ _します_。 オリジンには、URL SharePointアクセスできるサイト、ドキュメント ライブラリ、またはフォルダーを指定できます。 組織の起点を指定する場合、柔軟性が高い。 たとえば、複数の原点または 1 つの原点を指定して、すべてのアセットをCDNできます。 組織のパブリックオリジンとプライベートオリジンの両方を選択できます。 ほとんどの組織では、2 つの組み合わせを実装します。

フォルダーやドキュメント ライブラリなど、オリジン用の新しいコンテナーを作成し、新しいフォルダーから使用できるファイルを追加CDN。 これは、CDN から利用できるアセットの特定のセットを持ち、CDN アセットのセットをコンテナー内のファイルにのみ制限する場合に便利な方法です。

また、既存のサイト コレクション、サイト、ライブラリ、またはフォルダーを起点として構成することもできます。コンテナー内のすべての適格なアセットは、CDN。 既存のコンテナーをオリジンとして追加する前に、コンテンツとアクセス許可を認識し、不注意でアセットを匿名アクセスや承認されていないユーザーに公開することが重要です。

作成元の _CDNコンテンツ_ を除外するポリシーを定義CDN。 CDNポリシーは、ファイルの種類やサイト分類などの属性によってパブリックまたはプライベートオリジンのアセットを除外し、ポリシーで指定した CdnType (プライベートまたはパブリック) のすべての配信元に適用されます。 たとえば、複数のサブサイトを含むサイトで構成されるプライベート オリジンを追加する場合は、機密としてマークされたサイトを除外するポリシーを定義して、その分類が適用されたサイトのコンテンツが CDN から提供されません。 ポリシーは、ユーザーに追加 _した_ すべてのプライベートオリジンのコンテンツに適用CDN。

発生元の数が多い場合、要求の処理に必要なサービスの時間に与える影響が大CDN念頭に置いておきます。 可能な限り原点の数を制限することをお勧めします。

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>各オリジンをパブリックまたはプライベートにするかどうかを選択する

発生元を特定する場合は、公開または非公開に _するかどうかを_ 指定 _します_。 パブリックオリジンCDNアセットへのアクセスは匿名であり、プライベートオリジンCDNコンテンツは動的に生成されたトークンによって保護され、セキュリティが強化されます。 選択したオプションに関係なく、Microsoft は、ユーザー自身の管理に関して、すべての重いCDNします。 また、後で、サイトをセットアップして原点を特定した後CDN変更できます。

パブリック オプションとプライベート オプションの両方が同様のパフォーマンス向上を実現しますが、それぞれに固有の属性と利点があります。

**サイト** 内の公開元Office 365 CDN匿名でアクセス可能であり、ホストされているアセットには、アセットの URL を持つユーザーがアクセスできます。 公開されている元の場所のコンテンツへのアクセスは匿名になるため、アクセスしたコンテンツは、機密データ以外の一般的なコンテンツ (JavaScript ファイル、スクリプト、アイコン、画像など) をキャッシュする場合にのみ使用するようにしてください。

Office 365 CDN 内の **非公開** の元の場所は、SharePoint Online ドキュメント ライブラリ、サイト、独自のイメージなど、ユーザー コンテンツへのプライベート アクセスを行う場合に使用します。 プライベート オリジンのコンテンツへのアクセスは、動的に生成されたトークンによって保護され、元のドキュメント ライブラリまたは保存場所へのアクセス許可を持つユーザーだけがアクセスできます。 Office 365 CDN のプライベートオリジンは SharePoint Online コンテンツにのみ使用できます。また、SharePoint Online テナントからのリダイレクトによってのみプライベートオリジンのアセットにアクセスできます。

プライベート オリジンのアセットへのアクセスCDNの詳細については、「プライベート オリジンでアセットを使用する」[を参照してください](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)。

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>パブリックオリジンでアセットをホストする属性と利点

+ パブリックの配信元で公開されている資産には、すべてのユーザーが匿名でアクセスできます。
    > [!IMPORTANT]
    > ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。

+ パブリックの配信元から資産を削除した場合、その資産は最大 30 日間はキャッシュから引き続き使用できます。ただし、CDN 内の資産へのリンクは 15 分以内に無効になります。

+ パブリックの配信元にスタイル シート (CSS ファイル) をホストする場合は、コード内で相対パスと URI を使用できます。 つまり、背景画像と他のオブジェクトの場所を、呼び出し元の資産の場所からの相対位置で参照することができます。

+ パブリック オリジンの URL を作成することもできますが、慎重に進み、ページ コンテキスト プロパティを使用し、そのガイダンスに従ってください。 CDN にアクセスできなくなった場合、SharePoint Online でその URL は自動的に組織に対して解決されず、結果としてリンクが壊れて他のエラーが発生する可能性があるためです。 URL も変更される可能性があります。これは、現在の値に対してハードコードされるだけではない理由です。

+ パブリックオリジンに含まれる既定のファイルの種類は、.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2 です。 追加のファイルの種類を指定できます。

+ 指定したサイト分類によって識別されたアセットを除外するポリシーを構成できます。 たとえば、許可されているファイルの種類のもので、パブリックの配信元にある資産であっても、"社外秘" または "制限付き" としてマークされている資産はすべて除外する、といったことができます。

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>プライベートオリジンでアセットをホストする属性と利点

+ プライベートオリジンは、オンラインアセットSharePoint使用できます。

+ ユーザーは、コンテナーにアクセスするためのアクセス許可を持っている場合にのみ、プライベートオリジンからアセットにアクセスできます。 これらの資産に匿名でアクセスすることはできません。

+ プライベートオリジンのアセットは、オンライン テナントから参照SharePoint必要があります。 プライベート アセットへの直接アクセスCDNは機能しません。

+ プライベートオリジンからアセットを削除した場合、アセットはキャッシュから最大 1 時間引き続き使用できます。ただし、削除後 15 分以内に、CDNへのリンクは無効になります。

+ プライベートの配信元用に含まれている既定のファイルの種類は、.gif、.ico、.jpeg、.jpg、.js、.png です。 追加のファイルの種類を指定できます。

+ パブリックオリジンと同様に、ワイルドカードを使用してフォルダーまたはドキュメント ライブラリ内のすべてのアセットを含める場合でも、指定したサイト分類によって識別されたアセットを除外するポリシーを構成できます。

Office 365 CDN テナントで使用できる Office 365 CDN、CDN の一般的な概念、その他の Microsoft CDN を使用する理由の詳細については、「Office 365 Content [Delivery Networks」](content-delivery-networks.md)を参照してください。

### <a name="default-cdn-origins"></a>既定CDN原点

指定しない限り、Office 365を有効にするときに既定の原点を設定Office 365 CDN。 最初にプロビジョニングしない場合は、セットアップの完了後にこれらのオリジンを追加できます。 既定の原点のセットアップをスキップした結果を理解し、その理由を特定しない限り、CDN を有効にするときに作成を許可する必要があります。

既定のプライベート CDN元:

+ \*/userphoto.aspx
+ \*/siteassets

既定のパブリック CDN元:

+ \*/masterpage
+ \*/style ライブラリ
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets は_、2017 年 12 月に Office 365 CDNに追加された既定のパブリック オリジンです。 このオリジンは、アプリケーション内のSharePoint Framework機能するためにCDN必要があります。 2017 年 12 月より前に Office 365 CDN を有効にした場合、または CDN を有効にするときに既定の原点のセットアップをスキップした場合は、手動でこの原点を追加できます。 詳細については、「My client-side Web パーツ」または「SharePoint Framework[が機能しない」を参照してください](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>オンライン管理シェルを使用してOffice 365 CDNを設定SharePoint構成する

このセクションの手順では、オンライン管理シェルの SharePointを使用してオンラインにSharePointします。 手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

次の手順を実行して、CDN管理シェルを使用して SharePoint Online でアセットをホストSharePoint構成します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>組織が組織でユーザー設定を使用Office 365 CDN

テナントの設定を変更する前CDN、テナント内のプライベート CDN構成の現在Office 365する必要があります。 Connect管理シェルを使用してテナントSharePointにアクセスします。

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

**Get-SPOTenantCdnEnabled** コマンドレットを使用して、テナントからCDN状態設定を取得します。

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

指定した CdnType のCDNの状態が画面に出力されます。

**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織でこのコマンドレットを使用Office 365 CDN。 組織でパブリックオリジン、プライベートオリジン、または両方を一度に使用できます。 また、既定の原点CDN有効にするときに、既定の原点のセットアップをスキップする方法を構成できます。 このトピックの説明に従って、これらの原点は後でいつでも追加できます。

[オンラインWindows PowerShellのSharePoint] で、次のSharePoint使用します。

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

たとえば、組織でパブリックオリジンとプライベート オリジンの両方を使用するには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

組織でパブリックオリジンとプライベート オリジンの両方を使用できますが、既定のオリジンの設定をスキップするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Office 365 CDN を有効にした場合に既定でプロビジョニングされる起点と、既定の原点のセットアップをスキップした場合の潜在的な影響については、「Default CDN [origins」](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)を参照してください。

組織でパブリックオリジンを使用するには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

組織でプライベートオリジンを使用するには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

このコマンドレットの詳細については [、「Set-SPOTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>ファイルに含めるファイルの種類の一覧を変更する (Office 365 CDN)

> [!TIP]
> **Set-SPOTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義すると、現在定義されているリストが上書きされます。 リストに追加のファイルの種類を追加する場合は、まずコマンドレットを使用して、既に許可されているファイルの種類を確認し、新しいファイルの種類と一緒にリストに含める必要があります。

**Set-SPOTenantCdnPolicy** コマンドレットを使用して、パブリックオリジンとプライベート オリジンでホストできる静的ファイルの種類を定義CDN。 既定では、一般的なアセットの種類 (.css、.gif、.jpg、および.js。

[オンラインWindows PowerShellのSharePoint] で、次のSharePoint使用します。

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

たとえば、.css ファイルとCDNファイルをホスト.pngするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

現在許可されているファイルの種類を確認するには、CDN **Get-SPOTenantCdnPolicies コマンドレットを使用** します。

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

これらのコマンドレットの詳細については [、「Set-SPOTenantCdnPolicy」](/powershell/module/sharepoint-online/) および [「Get-SPOTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-online/)。

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>サイトから除外するサイト分類の一覧を変更する (Office 365 CDN)

> [!TIP]
> **Set-SPOTenantCdnPolicy** コマンドレットを使用してサイトの分類を除外すると、現在定義されているリストが上書きされます。 追加のサイト分類を除外する場合は、まずコマンドレットを使用して、既に除外されている分類を確認し、新しい分類と共に追加します。


  **Set-SPOTenantCdnPolicy** コマンドレットを使用して、CDN で利用できるようにしないサイトの分類を除外します。 既定で除外されるサイトの分類はありません。

[オンラインWindows PowerShellのSharePoint] で、次のSharePoint使用します。

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

現在制限されているサイト分類を確認するには **、Get-SPOTenantCdnPolicies コマンドレットを使用** します。

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

返されるプロパティは IncludeFileExtensions、ExcludeRestrictedSiteClassifications、ExcludeIfNoScriptDisabled _です_。  

_IncludeFileExtensions_ プロパティには、アプリケーションから提供されるファイル拡張子の一覧がCDN。

> [!NOTE]
> 既定のファイル拡張子は、パブリックとプライベートの間で異なります。

_ExcludeRestrictedSiteClassifications_ プロパティには、サイトから除外するサイトのCDN。 たとえば、機密としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツがサイトから提供CDN。

_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性CDNに基づいてコンテンツを除外します。 既定では _、NoScript_ 属性は [モダンサイトに対して有効] および [クラシック サイト **では無効]** _に設定_ されています。 これは、テナントの設定によって異なります。

これらのコマンドレットの詳細については [、「Set-SPOTenantCdnPolicy」](/powershell/module/sharepoint-online/) および [「Get-SPOTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-online/)。

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>アセットのオリジンを追加する

発生元 **を定義するには、Add-SPOTenantCdnOrigin** コマンドレットを使用します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

> [!IMPORTANT]
> ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

path の値 _は_ 、アセットを含むライブラリまたはフォルダーへの相対パスです。 相対パスに加え、ワイルドカードも使用できます。 Origins は、URL の先頭に付加されたワイルドカードをサポートします。 これにより、複数のサイトにまたがるオリジンを作成できます。 たとえば、すべてのサイトの masterpages フォルダー内のすべてのアセットを、CDN 内のパブリック オリジンとして含めるには、次のコマンドを入力します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ ワイルドカード修飾子 * は、パスの先頭でのみ使用できます。指定した URL の下のすべての URL セグメント **/** と一致します。
+ パスは、ドキュメント ライブラリ、フォルダー、またはサイトを指します。 たとえば、パス _*/site1 は_ 、サイトの下のすべてのドキュメント ライブラリと一致します。

特定の相対パスを持つ原点を追加できます。 完全パスを使用して原点を追加することはできません。

次の使用例は、サイトアセッツ ライブラリのプライベートオリジンを特定のサイトに追加します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

次の使用例は、サイト コレクションのサイト アセット ライブラリに _folder1_ フォルダーのプライベートオリジンを追加します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換える方法があります。 次の例では、サイト コレクションのサイト アセット ライブラリにフォルダー _1_ フォルダーのプライベートオリジンを追加します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

> [!NOTE]
> プライベートオリジンでは、オリジンから共有されているアセットにメジャー バージョンが公開されている必要があります。そのアセットは、そのオリジンからアクセスCDN。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>例: マスター ページとオンライン用のスタイル ライブラリの公開元をSharePointする

通常、これらの原点は既定で設定されます。既定では、この設定を有効Office 365 CDN。 ただし、手動で有効にする場合は、次の手順を実行します。

+ スタイル ライブラリをパブリックオリジンとして定義するには **、Add-SPOTenantCdnOrigin** コマンドレットを使用します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ マスター ページをパブリックオリジンとして定義するには **、Add-SPOTenantCdnOrigin** コマンドレットを使用します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>例: サイトアセット、サイト ページ、および公開イメージのプライベート オリジンをオンライン用にSharePointする

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイトアセット フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ 発行イメージ **フォルダーをプライベートオリジンとして定義するには、Add-SPOTenantCdnOrigin** コマンドレットを使用します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>例: オンラインのサイト コレクションのプライベートオリジンをSharePointする

**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。 以下に例を示します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

このコマンドとその構文の詳細については [、「Add-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 構成保留中の _メッセージが_ 表示される場合があります。これは、オンライン テナントが SharePointサービスに接続CDNです。 これには最大 15 分かかる場合があります。

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>サーバーを管理Office 365 CDN

このセクションで説明するように、CDNを設定したら、コンテンツを更新したり、必要に応じて変更を加えたりして、構成を変更できます。

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>アセットを追加、更新、または削除Office 365 CDN

セットアップ手順が完了したら、新しいアセットを追加し、必要に従って既存のアセットを更新または削除できます。 作成元として識別したフォルダーまたはSharePointアセットに変更を加えるだけ。 新しいアセットを追加した場合は、すぐに新しいアセットをCDNできます。 ただし、アセットを更新した場合、新しいコピーが反映され、新しいコピーが使用できるまで最大で 15 分かかりますCDN。

オリジンの場所を取得する必要がある場合は **、Get-SPOTenantCdnOrigins コマンドレットを使用** できます。 このコマンドレットの使用方法については [、「Get-SPOTenantCdnOrigins」を参照してください](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>オブジェクトから原点を削除Office 365 CDN

作成元として識別したフォルダーまたはSharePointライブラリへのアクセスを削除できます。 これを行うには **、Remove-SPOTenantCdnOrigin コマンドレットを使用** します。

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

このコマンドレットの使用方法については [、「Remove-SPOTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>オブジェクトの原点を変更Office 365 CDN

作成した原点は変更できません。 代わりに、原点を削除し、新しい原点を追加します。 詳細については、「アセットから原点[を削除](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)するには」および「Office 365 CDNを追加するには」[を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>サーバーを無効Office 365 CDN

**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織のCDNを無効にします。 パブリック オリジンとプライベート オリジンの両方が CDNに対して有効になっている場合は、次の例に示すように、コマンドレットを 2 回実行する必要があります。

パブリック オリジンの使用を無効にするには、CDNコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

次のコマンドでプライベートオリジンCDN無効にするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

このコマンドレットの詳細については [、「Set-SPOTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>PnP PowerShell を使用してOffice 365 CDN設定および構成する

このセクションの手順では、PnP PowerShell を使用してオンラインに接続SharePointします。 手順については [、「PnP PowerShell の使用を開始する」を参照してください](https://github.com/SharePoint/PnP-PowerShell#getting-started)。

PnP PowerShell を使用して、CDNをオンラインでホストSharePoint構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>組織が組織でユーザー設定を使用Office 365 CDN

テナントの設定を変更する前CDN、テナント内のプライベート CDN構成の現在Office 365する必要があります。 Connect PnP PowerShell を使用してテナントにアクセスします。

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

**Get-PnPTenantCdnEnabled** コマンドレットを使用して、テナントからCDN状態設定を取得します。

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

指定した CdnType のCDNの状態が画面に出力されます。

**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織でこのコマンドレットを使用Office 365 CDN。 組織でパブリックオリジン、プライベートオリジン、または両方を同時に使用できます。 また、既定の原点CDN有効にするときに、既定の原点のセットアップをスキップする方法を構成できます。 このトピックの説明に従って、これらの原点は後でいつでも追加できます。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

たとえば、組織でパブリックオリジンとプライベート オリジンの両方を使用するには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

組織でパブリックオリジンとプライベート オリジンの両方を使用できますが、既定のオリジンの設定をスキップするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Office 365 CDN を有効にした場合に既定でプロビジョニングされる起点と、既定の原点のセットアップをスキップした場合の潜在的な影響については、「Default CDN [origins」](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)を参照してください。

組織でパブリックオリジンを使用するには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

組織でプライベートオリジンを使用するには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

このコマンドレットの詳細については [、「Set-PnPTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>ファイルに含めるファイルの種類の一覧を変更する (Office 365 CDN)

> [!TIP]
> **Set-PnPTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義すると、現在定義されているリストが上書きされます。 リストに追加のファイルの種類を追加する場合は、まずコマンドレットを使用して、既に許可されているファイルの種類を確認し、新しいファイルの種類と一緒にリストに含める必要があります。

**Set-PnPTenantCdnPolicy** コマンドレットを使用して、パブリックオリジンとプライベート オリジンでホストできる静的ファイルの種類を定義CDN。 既定では、一般的なアセットの種類 (.css、.gif、.jpg、および.js。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

たとえば、.css ファイルとCDNファイルをホスト.pngするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

現在許可されているファイルの種類を確認するには、CDN **Get-PnPTenantCdnPolicies コマンドレットを使用** します。

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

これらのコマンドレットの詳細については [、「Set-PnPTenantCdnPolicy」](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) および [「Get-PnPTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>サイトから除外するサイト分類の一覧を変更する (Office 365 CDN)

> [!TIP]
> **Set-PnPTenantCdnPolicy** コマンドレットを使用してサイトの分類を除外すると、現在定義されているリストが上書きされます。 追加のサイト分類を除外する場合は、まずコマンドレットを使用して、既に除外されている分類を確認し、新しい分類と共に追加します。

**Set-PnPTenantCdnPolicy** コマンドレットを使用して、サイトの分類を除外します。このコマンドレットを使用CDN。 既定で除外されるサイトの分類はありません。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

現在制限されているサイト分類を確認するには **、Get-PnPTenantCdnPolicies コマンドレットを使用** します。

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

返されるプロパティは IncludeFileExtensions、ExcludeRestrictedSiteClassifications、ExcludeIfNoScriptDisabled _です_。  

_IncludeFileExtensions_ プロパティには、アプリケーションから提供されるファイル拡張子の一覧がCDN。

> [!NOTE]
> 既定のファイル拡張子は、パブリックとプライベートの間で異なります。

_ExcludeRestrictedSiteClassifications_ プロパティには、サイトから除外するサイトのCDN。 たとえば、機密としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツがサイトから提供CDN。

_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性CDNに基づいてコンテンツを除外します。 既定では _、NoScript_ 属性は [モダンサイトに対して有効] および [クラシック サイト **では無効]** _に設定_ されています。 これは、テナントの設定によって異なります。

これらのコマンドレットの詳細については [、「Set-PnPTenantCdnPolicy」](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) および [「Get-PnPTenantCdnPolicies」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)。

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>アセットのオリジンを追加する

発生元 **を定義するには、Add-PnPTenantCdnOrigin** コマンドレットを使用します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

> [!IMPORTANT]
> ユーザー情報を含むリソースや、組織に機密性が高いと見なされるリソースは、パブリック オリジンに配置しなけれる必要があります。

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

path の値 _は_ 、アセットを含むライブラリまたはフォルダーへの相対パスです。 相対パスに加え、ワイルドカードも使用できます。 Origins は、URL の先頭に付加されたワイルドカードをサポートします。 これにより、複数のサイトにまたがるオリジンを作成できます。 たとえば、すべてのサイトの masterpages フォルダー内のすべてのアセットを、CDN 内のパブリック オリジンとして含めるには、次のコマンドを入力します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ ワイルドカード修飾子 * は、パスの先頭でのみ使用できます。指定した URL の下のすべての URL セグメント **/** と一致します。
+ パスは、ドキュメント ライブラリ、フォルダー、またはサイトを指します。 たとえば、パス _*/site1 は_ 、サイトの下のすべてのドキュメント ライブラリと一致します。

特定の相対パスを持つ原点を追加できます。 完全パスを使用して原点を追加することはできません。

次の使用例は、サイトアセット ライブラリのプライベートオリジンを特定のサイトに追加します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

次の使用例は、サイト コレクションのサイト アセット ライブラリに _folder1_ フォルダーのプライベートオリジンを追加します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換える方法があります。 次の例では、サイト コレクションのサイト アセット ライブラリにフォルダー _1_ フォルダーのプライベートオリジンを追加します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

> [!NOTE]
> プライベートオリジンでは、オリジンから共有されているアセットにメジャー バージョンが公開されている必要があります。そのアセットは、そのオリジンからアクセスCDN。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>例: マスター ページとオンライン用のスタイル ライブラリの公開元をSharePointする

通常、これらの原点は既定で設定されます。既定では、この設定を有効Office 365 CDN。 ただし、手動で有効にする場合は、次の手順を実行します。

+ スタイル ライブラリをパブリックオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ マスター ページをパブリックオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>例: サイトアセット、サイト ページ、および公開イメージのプライベート オリジンをオンライン用にSharePointする

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイトアセット フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ 発行イメージ フォルダーをプライベートオリジンとして定義するには **、Add-PnPTenantCdnOrigin** コマンドレットを使用します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>例: オンラインのサイト コレクションのプライベートオリジンをSharePointする

**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。 以下に例を示します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

このコマンドとその構文の詳細については [、「Add-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 構成保留中の _メッセージが_ 表示される場合があります。これは、オンライン テナントが SharePointサービスに接続CDNです。 これには最大 15 分かかる場合があります。

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>サーバーを管理Office 365 CDN

このセクションで説明するように、CDNを設定したら、コンテンツを更新したり、必要に応じて変更を加えたりして、構成を変更できます。

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>アセットを追加、更新、または削除Office 365 CDN

セットアップ手順が完了したら、新しいアセットを追加し、必要に従って既存のアセットを更新または削除できます。 作成元として識別したフォルダーまたはSharePointアセットに変更を加えるだけ。 新しいアセットを追加した場合は、すぐに新しいアセットをCDNできます。 ただし、アセットを更新した場合、新しいコピーが反映され、新しいコピーが使用できるまで最大で 15 分かかりますCDN。

オリジンの場所を取得する必要がある場合は **、Get-PnPTenantCdnOrigin コマンドレットを使用** できます。 このコマンドレットの使用方法については [、「Get-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>オブジェクトから原点を削除Office 365 CDN

作成元として識別したフォルダーまたはSharePointライブラリへのアクセスを削除できます。 これを行うには **、Remove-PnPTenantCdnOrigin コマンドレットを使用** します。

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

このコマンドレットの使用方法については [、「Remove-PnPTenantCdnOrigin」を参照してください](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>オブジェクトの原点を変更Office 365 CDN

作成した原点は変更できません。 代わりに、原点を削除し、新しい原点を追加します。 詳細については、「アセットから原点[を削除](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)するには」および「Office 365 CDNを追加するには」[を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>サーバーを無効Office 365 CDN

**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織のCDNを無効にします。 パブリック オリジンとプライベート オリジンの両方が CDNに対して有効になっている場合は、次の例に示すように、コマンドレットを 2 回実行する必要があります。

パブリック オリジンの使用を無効にするには、CDNコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

次のコマンドでプライベートオリジンCDN無効にするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

このコマンドレットの詳細については [、「Set-PnPTenantCdnEnabled」を参照してください](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Office 365 CLI を使用して Office 365 CDN をセットアップおよび構成する

このセクションの手順では、CLI をインストールしている必要Office 365[です](https://aka.ms/o365cli)。 次に、login コマンドをOffice 365テナントに[接続](https://pnp.github.io/office365-cli/cmd/login/)します。

次の手順を実行して、CDN CLI を使用して SharePointをホストするOffice 365します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-the-office-365-cdn"></a>サーバーを有効Office 365 CDN

テナントの Office 365 CDN の状態は [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) コマンドを使用して管理できます。

テナントで Office 365 パブリック CDN を有効にするには、次のように実行します。

```cli
spo cdn set --type Public --enabled true
```

アプリケーションを有効にするにはOffice 365 SharePoint CDN実行します。

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Office 365 CDN の現在の状況を確認する

特定の種類のファイルが有効または無効Office 365 CDN確認するには[、spo cdn get コマンドを使用](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)します。

Office 365 パブリック CDN が有効かどうかを確認するには、次のように実行します。

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>原点をOffice 365 CDNする

現在構成されている Office 365 パブリック CDN の配信元を確認するには、次のように実行します。

```cli
spo cdn origin list --type Public
```

既定[でCDNを](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)有効にした場合にプロビジョニングされるオリジンの詳細については、「Default Office 365 CDN」 を参照してください。

### <a name="add-an-office-365-cdn-origin"></a>原点をOffice 365 CDNする

> [!IMPORTANT]
> パブリック オリジンとして構成されたドキュメント ライブラリ内に、組織にSharePointと見なされるリソースを配置する必要はありません。

[spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) コマンドを使用して CDN の配信元を定義します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

ここで `path` 、アセットを含むフォルダーへの相対パスを指定します。 相対パスに加え、ワイルドカードも使用できます。

すべてのサイトのマスター ページギャラリーのすべてのアセットを公開元として含めるには、次のコマンドを実行します。

```cli
spo cdn origin add --type Public --origin */masterpage
```

特定のサイト コレクションのプライベートの配信元を構成するには、次のように実行します。

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> CDN の配信元の追加後、CDN サービス経由でファイルを取得できるようになるまで最大 15 分かかることがあります。 特定の配信元が既に有効かどうかは、[spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) コマンドを使用して検証できます。

### <a name="remove-an-office-365-cdn-origin"></a>原点をOffice 365 CDNする

[spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) コマンドを使用して、指定した種類の CDN の配信元を削除します。

パブリックオリジンを構成から削除するにはCDN実行します。

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> 元のCDN削除しても、その原点に一致するドキュメント ライブラリに格納されているファイルには影響を与えかねない。 これらのアセットが URL を使用して参照されているSharePoint、SharePointドキュメント ライブラリを指す元の URL に自動的に切り替えます。 ただし、アセットがパブリック CDN URL を使用して参照されている場合、原点を削除するとリンクが壊れ、手動で変更する必要があります。

### <a name="modify-an-office-365-cdn-origin"></a>原点をOffice 365 CDNする

既存の CDN の配信元を変更することはできません。 代わりに、`spo cdn origin remove` コマンドを使用して定義済みの CDN の配信元を削除して、`spo cdn origin add` コマンドで新しい配信元を作成する必要があります。

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>ファイルに含めるファイルの種類を変更Office 365 CDN

既定では、次のファイルの種類が CDN に含まれています _。.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2_ です。 CDN に他の種類のファイルを含める必要がある場合、[spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して CDN 構成を変更できます。

> [!NOTE]
> ファイルの種類のリストを変更する場合、現在定義されているリストを上書きします。 他のファイルの種類を追加する場合は、[spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) コマンドを最初に使用して現在構成されているファイルの種類を確認します。

JSON ファイルの種類 _を_ パブリック ファイルに含まれるファイルの既定の一覧に追加するには、次CDN実行します。

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Office 365 CDN から除外するサイトの分類のリストを変更する

[spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して、CDN で利用できるようにしないサイトの分類を除外します。 既定で除外されるサイトの分類はありません。

> [!NOTE]
> 除外するサイトの分類のリストを変更する場合、現在定義されているリストを上書きします。 他の分類を除外する場合は、[spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) コマンドを最初に使用して現在構成されている分類を確認します。

HBI として分類された _サイトを_ パブリック サイトから除外するには、CDN実行します。

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>サーバーを無効Office 365 CDN

Office 365 CDN を無効にするには、`spo cdn set` コマンドを使用します。たとえば、次のように実行します。

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>アセットCDN使用する

作成元と構成済みのCDNを有効にしたので、アセットの使用CDNできます。

このセクションでは、SharePoint ページとコンテンツで CDN URL を使用して、SharePoint がパブリックオリジンとプライベート オリジンの両方のアセットの要求を CDN にリダイレクトする方法について説明します。

+ [アセットへのリンクCDNする](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [パブリックオリジンでのアセットの使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [プライベートオリジンでのアセットの使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

クライアント側 Web パーツをホストするために CDN を使用する方法については、「Office 365 CDN からクライアント側 Web パーツをホストする (Hello World Part [4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)」を参照してください。

> [!NOTE]
> _ClientSideAssets_ フォルダーをプライベート CDNリストに追加すると、CDNホストされたカスタム Web パーツはレンダリングに失敗します。 SPFX Web パーツで使用されるファイルはパブリック CDN のみを使用し、ClientSideAssets フォルダーはパブリック サーバーの既定のCDN。

### <a name="updating-links-to-cdn-assets"></a>アセットへのリンクCDNする

オリジンに追加したアセットを使用するには、元のファイルへのリンクを元のファイルへのパスで更新します。

+ オリジンに追加したアセットへのリンクを含むページまたはコンテンツを編集します。 また、表示される任意の場所で特定のアセットへのリンクを更新する場合は、いくつかの方法のいずれかを使用して、入力サイトまたはサイト コレクション全体のリンクをグローバルに検索および置換できます。
+ オリジン内のアセットへの各リンクについて、パスをコピー元のファイルへのパスCDNします。 相対パスを使用できます。
+ ページまたはコンテンツを保存します。

たとえば、ドキュメント ライブラリ フォルダー _/site/CDN_origins/public/ にコピーしたイメージ /site/SiteAssets/images/image.png_ を _検討します_。 CDN アセットを使用するには、イメージ ファイルの場所への元のパスを原点へのパスに置き換え、新しい URL _/site/CDN_origins/public/image.pngを作成します_。

相対パスではなくアセットの完全な URL を使用する場合は、次のようにリンクを作成します。

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> 一般に、URL を直接、ページ内のアセットにハードコードCDN。 ただし、必要に応じて、パブリック オリジンのアセットの URL を手動で作成できます。 詳細については[、「Hardcoding CDNの URL」を参照してください](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)。

CDN からアセットが提供されているのを確認する方法については、「CDN でアセットが[](use-microsoft-365-cdn-with-spo.md#CDNConfirm)提供されているのを確認する方法」を参照してください。「Office 365 CDN のトラブルシューティング」を[参照してください](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)。

### <a name="using-assets-in-public-origins"></a>パブリックオリジンでのアセットの使用

SharePoint  Online の発行機能は、パブリック オリジンに格納されているアセットの URL を自動的に CDN 同等のアセットに書き換え、SharePoint ではなく CDN サービスからアセットを提供します。

発行元が発行機能が有効なサイト内で、CDN にオフロードするアセットが次のいずれかのカテゴリにある場合、SharePoint は、アセットが CDN ポリシーによって除外されていない場合、オリジンのアセットの URL を自動的に書き換える。

SharePoint 発行機能によって自動的に書き換えられるのは次のようなリンクです。

+ 従来の発行ページの HTML 応答の IMG/LINK/CSS URL
  + これには、ページの HTML コンテンツ内に作成者によって追加された画像が含まれます。
+ 画像ライブラリ スライドショー Web パーツの画像 URL
+ SPList REST API (RenderListDataAsStream) 結果の画像フィールド
  + フィールドのコンマ区切りリストを指定するには、新しいプロパティ _ImageFieldsToTryRewriteToCdnUrls_ を使用します。
  + ハイパーリンク フィールドと PublishingImage フィールドをサポート
+ SharePoint表示

次の図は、公開元SharePointを含むページの要求を受け取るワークフローを示しています。

![ワークフロー図: 公開元Office 365 CDNアセットを取得します。](../media/O365-CDN/o365-cdn-public-steps-transparent.png "ワークフロー: パブリック Office 365 CDNアセットの取得")

> [!TIP]
> ページ上の特定の URL の自動書き換えを無効にする場合は、ページをチェックアウトしてクエリ文字列パラメーターを **追加できます。無効にする各リンクの末尾に NoAutoReWrites=true** を指定します。

#### <a name="constructing-cdn-urls-for-public-assets"></a>パブリックアセットCDN URL の作成

公開機能がパブリック オリジンで有効になっていない場合、またはアセットが CDN サービスの自動書き換え機能でサポートされているリンクの種類の 1 つではない場合は、アセットの CDN 場所に URL を手動で作成し、コンテンツでこれらの URL を使用できます。

> [!NOTE]
> リソースが要求された時点で URL の最後のセクションを形成する必要なアクセス トークンが生成されるので、プライベート オリジンのアセットに CDN URL をハードコードまたは構築することはできません。 パブリック サーバーの URL を作成CDN、変更される可能性がある URL をハード コードする必要はありません。

パブリック アセットCDN URL 形式は次のようになります。

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

**TenantHostName をテナント** 名に置き換える。 例:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> ページ コンテキスト プロパティを使用して、ハード コーディング " " ではなくプレフィックスを作成する必要 https://publiccdn.sharepointonline.com があります。 URL は変更される可能性があります。ハード コード化する必要はありません。 クラシック SharePoint Online で表示テンプレートを使用している場合は、URL のプレフィックスとして表示テンプレートのプロパティ "window._spPageContextInfo.publicCdnBaseUrl" を使用できます。 モダンおよびクラシック SPFx Web パーツを使用する場合SharePointプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" を利用できます。 これにより、プレフィックスが提供され、変更された場合に実装が更新されます。 SPFx の例として、URL はプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" を使用して構築できます。 シーズン 1[のパフォーマンス CDNの一部であるクライアント](https://youtu.be/IH1RbQlbhIA)側コードの 「コードを使用する」[を参照してください。](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>プライベートオリジンでのアセットの使用

プライベートオリジンでアセットを使用するには、追加の構成は必要ありません。 SharePointオンラインでは、プライベートオリジン内のアセットの URL が自動的に書き換わるので、それらのアセットの要求は常にサーバーから提供CDN。 これらの URL には、アセットが要求された時点で SharePoint Online によって自動生成する必要があるトークンが含まれているため、プライベート オリジンの CDN アセットに対して URL を手動でビルドすることはできません。

プライベートオリジンのアセットへのアクセスは、オリジンに対するユーザーのアクセス許可に基づいて動的に生成されたトークンによって保護されます。以下のセクションで説明する注意点があります。 ユーザーがコンテンツをレンダリングするには **、** 少なくとも原点への読み取りアクセスCDN必要があります。

次の図は、プライベートオリジンSharePointを含むページの要求を受け取るワークフローを示しています。

![ワークフロー図: プライベートオリジンOffice 365 CDNアセットを取得します。](../media/O365-CDN/o365-cdn-private-steps-transparent.png "ワークフロー: プライベート Office 365 CDNからアセットを取得する")

#### <a name="token-based-authorization-in-private-origins"></a>プライベートオリジンでのトークンベースの承認

プライベート オリジン内のアセットへのアクセスは、Office 365 CDN Online によって生成されたトークンSharePointされます。 作成元によって指定されたフォルダーまたはライブラリへのアクセス許可を既に持っているユーザーには、アクセス許可レベルに基づいてユーザーがファイルにアクセスできるトークンが自動的に付与されます。 これらのアクセス トークンは、トークン再生攻撃を防止するために生成された後、30 ~ 90 分間有効です。

アクセス トークンが生成されると、SharePoint Online は、2 つの承認パラメーターを含む _クライアントにカスタム_ URI (エッジ承認トークン) と _oat_ (オリジン認証トークン) を返します。 各トークンの構造は _、epoch<_ のセキュリティで保護された署名の>__<の有効期限>。 以下に例を示します。

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> トークンを所有しているユーザーは、リソースにアクセスCDN。 ただし、これらのアクセス トークンを含む URL は HTTPS 経由でのみ共有されます。そのため、トークンの有効期限が切れる前にエンド ユーザーが URL を明示的に共有しない限り、承認されていないユーザーはアセットにアクセスできます。

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>アイテム レベルのアクセス許可は、プライベートオリジンのアセットではサポートされていません

重要な点は、SharePoint Online がプライベートオリジンのアセットに対するアイテム レベルのアクセス許可をサポートしていない点に注意してください。 たとえば、場所にあるファイルの場合、ユーザーは次の条件に従って `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` ファイルに効果的にアクセスできます。

|User  |アクセス許可  |有効なアクセス  |
|---------|---------|---------|
|ユーザー 1     |フォルダー 1 へのアクセス権を持つ         |サーバーからimage1.jpgアクセスCDN         |
|ユーザー 2     |folder1 にアクセスできない         |サーバーからimage1.jpgにアクセスCDN         |
|ユーザー 3     |folder1 へのアクセス権は付与されませんが、オンラインでフォルダーにアクセスするための明示的image1.jpgがSharePointされます。         |オンラインから直接image1.jpgアクセスできますが、SharePointからアクセスCDN         |
|ユーザー 4     |folder1 へのアクセス権を持っていますが、オンラインでフォルダーへのアクセスimage1.jpg明示的SharePointされています         |SharePoint Online からアセットにアクセスすることはできませんが、CDN Online でファイルへのアクセスが拒否されているにもかかわらず、CDN からアセットにSharePointできます。         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>問題のトラブルシューティングOffice 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>アセットがサービスを受け取っているのを確認CDN。

CDN アセットへのリンクをページに追加したら、CDN からアセットが提供されているのを確認するには、ページを参照し、レンダリング後にイメージを右クリックし、イメージの URL を確認します。

ブラウザーの開発者ツールを使用して、ページ上の各アセットの URL を表示したり、サードパーティのネットワーク トレース ツールを使用することもできます。

> [!NOTE]
> Fiddler などのネットワーク ツールを使用して、SharePoint ページからのアセットのレンダリング以外でアセットをテストする場合は、url が SharePoint Online テナントのルート URL である GET 要求に、参照先ヘッダー "Referer:" を手動で追加する必要があります。 `https://yourdomain.sharepoint.com`

Web ブラウザーでCDN URL をテストすることはできません。Web ブラウザーから参照者がオンラインSharePointがあります。 ただし、CDN アセット URL を SharePoint ページに追加し、ブラウザーでページを開いた場合は、CDN アセットがページに表示されます。

ブラウザーで開発者ツールを使用する方法の詳細については、「Microsoft Edge開発者ツール[」をMicrosoft Edgeしてください](/microsoft-edge/devtools-guide)。

SharePoint Developer Patterns and [Practices YouTube](https://aka.ms/sppnp-videos)チャネルでホストされている短いビデオを見て、CDN が動作しているのを確認する方法を説明するには[、「CDN](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)使用状況の確認と最適なネットワーク接続の確保」を参照してください。

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>新しいオリジンのアセットが使用できない理由
登録が CDN 経由で伝達され、アセットが起点から CDN ストレージにアップロードされるのに時間がかかるので、新しいオリジンのアセットはすぐには使用できません。 アセットが利用可能になるのに必要な時間は、CDNの数とファイル サイズによって異なります。

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>クライアント側の Web パーツまたはSharePoint Frameworkソリューションが機能しない

パブリックオリジンのOffice 365 CDNを有効にした場合、CDNサービスは次の既定のオリジンを自動的に作成します。

+ */MASTERPAGE
+ */STYLE ライブラリ
+ */CLIENTSIDEASSETS

*/clientsideassets の生成元が見つからない場合、SharePoint Frameworkソリューションは失敗し、警告メッセージやエラー メッセージは生成されません。 CDN が _-NoDefaultOrigins_ パラメーターを **$true** に設定して有効になっているか、または原点が手動で削除されたため、この原点が見つからない可能性があります。

次の PowerShell コマンドを使用して、どの原点が存在するのか確認できます。

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

または、次の CLI でOffice 365できます。

```cli
spo cdn origin list
```

PowerShell で原点を追加するには、次のコマンドを実行します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

CLI で原点をOffice 365するには、次のOffice 365します。

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>どの PowerShell モジュールと CLI シェルを使用して作業する必要Office 365 CDN?

オンライン管理シェル PowerShell モジュールまたは Office 365 CDN CLIを使用して、SharePointを使用Office 365 **できます**。

+ [SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [Office 365 CLI のインストール](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>関連項目

[Content Delivery Network](./content-delivery-networks.md)

[Office 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[SharePointPerformance Series - Office 365 CDN ビデオ シリーズ](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
