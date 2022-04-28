---
title: SharePoint Online でOffice 365 Content Delivery Network (CDN) を使用する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/13/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
description: Office 365 Content Delivery Network (CDN) を使用して、SharePoint Online アセットの配信を高速化する方法について説明します。
ms.openlocfilehash: 42836fa8a43b7251be27cfd841b67d47e12b036e
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092009"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用

組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的資産をホストすることで、SharePoint Online ページのパフォーマンスを向上させることができます。 Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。 また、Office 365 CDNでは、圧縮と HTTP パイプライン処理を改善するために [HTTP/2 プロトコル](https://en.wikipedia.org/wiki/HTTP/2)を使用します。 Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

> [!NOTE]
> Office 365 CDN は、**本番** (ワールドワイド) クラウドのテナントのみが利用できます。 現在、米国政府、中国、ドイツのクラウドのテナントは Office 365 CDN をサポートしていません。

Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。 Office 365 CDN でホストするコンテンツの種類に応じて、**公開**、**非公開**、またはその両方の元の場所を追加できます。 パブリックオリジンとプライベートオリジンの違いの詳細については、「 [各配信元をパブリックまたはプライベートにするかどうかを選択](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) する」を参照してください。

![概念図Office 365 CDN。](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN の概念図")

CDN の動作に既に精通している場合は、テナントのOffice 365 CDNを有効にするには、いくつかの手順を完了するだけで済みます。 このトピックでは、その方法について説明します。 静的資産のホスティングを開始する方法の詳細については、こちらを参照してください。

> [!TIP]
> 特殊な使用シナリオでOffice 365と共に使用できる他の Microsoft ホステッド CDN がありますが、このトピックでは説明しません。これは、Office 365 CDNの範囲外であるためです。 詳細については、「 [その他の Microsoft CDN」を](content-delivery-networks.md#other-microsoft-cdns)参照してください。

 **[Office 365のネットワーク計画とパフォーマンスのチューニングに](./network-planning-and-performance.md)戻ります。**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>SharePoint Online でのOffice 365 CDNの操作の概要

組織のOffice 365 CDNを設定するには、次の基本的な手順に従います。

+ [Office 365 CDNのデプロイを計画する](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [CDNでホストする静的資産を決定](use-microsoft-365-cdn-with-spo.md#CDNAssets)します。
  + [資産を格納する場所を決定します](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。 この場所は、SharePoint サイト、ライブラリ、またはフォルダーと呼ばれ、_配信元_ と呼ばれます。
  + [各配信元をパブリックまたはプライベートにするかどうかを選択](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)します。 パブリック型とプライベート型の両方のオリジンを複数追加できます。

+ PowerShell または CLI を使用してCDNを設定して構成Microsoft 365

  + [SharePoint Online Management Shell を使用してCDNを設定して構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [PnP PowerShell を使用してCDNを設定して構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [MICROSOFT 365用の CLI を使用してCDNを設定して構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  この手順を完了すると、次のようになります。

  + 組織のCDNを有効にしました。
  + 配信元を追加し、各配信元をパブリックまたはプライベートとして識別しました。

セットアップが完了したら、次の方法で時間の経過と共[にOffice 365 CDNを管理](use-microsoft-365-cdn-with-spo.md#CDNManage)できます。

+ アセットの追加、更新、削除
+ 配信元の追加と削除
+ CDN ポリシーの構成
+ 必要に応じて、CDNを無効にします

最後に、[CDNアセットを使用して](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)、パブリックとプライベートの両方の配信元からCDNアセットにアクセスする方法について説明します。

一般的[な問題の解決に](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)関するガイダンスについては、「Office 365 CDNのトラブルシューティング」を参照してください。

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Office 365 CDNのデプロイを計画する

Office 365 テナントのOffice 365 CDNをデプロイする前に、計画プロセスの一環として次の要素を考慮する必要があります。

  + [CDNでホストする静的資産を決定する](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [資産を格納する場所を決定する](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [各配信元をパブリックまたはプライベートにするかどうかを選択する](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>CDNでホストする静的資産を決定する

一般に、CDN は _、静的資産_、またはあまり頻繁に変更されない資産をホストする場合に最も効果的です。 適切な経験則は、次の条件の一部またはすべてを満たすファイルを識別することです。

+ ページに埋め込まれた静的ファイル (スクリプトやイメージなど) は、ページの読み込み時間に大きな影響を与える可能性があります
+ 実行可能ファイルやインストール ファイルなどの大きなファイル
+ クライアント側のコードをサポートするリソース ライブラリ

たとえば、サイト イメージやスクリプトのように繰り返し要求される小さなファイルは、サイトレンダリングのパフォーマンスを大幅に向上させ、CDNの配信元に追加すると、SharePoint Online サイトの負荷を段階的に減らすことができます。 インストール実行可能ファイルなどの大規模なファイルは、CDNからダウンロードできます。SharePoint Online サイトへのアクセス頻度が低い場合でも、パフォーマンスへの影響が高く、その後の負荷の軽減につながります。

ファイルごとのパフォーマンスの向上は、最も近いCDN エンドポイントへのクライアントの近接性、ローカル ネットワーク上の一時的な状態など、多くの要因に依存します。 多くの静的ファイルは非常に小さく、Office 365から 1 秒未満でダウンロードできます。 ただし、Web ページには、累積ダウンロード時間が数秒の埋め込みファイルが多数含まれている場合があります。 CDNからこれらのファイルを提供すると、ページ全体の読み込み時間を大幅に短縮できます。 例については、「[CDNはどのようなパフォーマンス向上を提供](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)しますか?」を参照してください。

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>資産を格納する場所を決定する

CDNは _、配信元_ と呼ばれる場所からアセットをフェッチします。 配信元には、URL でアクセスできるSharePoint サイト、ドキュメント ライブラリ、またはフォルダーを指定できます。 組織の配信元を指定する場合は、優れた柔軟性があります。 たとえば、複数の原点を指定したり、すべてのCDNアセットを配置する 1 つの原点を指定したりできます。 組織のパブリックオリジンとプライベート配信元の両方を選択できます。 ほとんどの組織では、2 つの組み合わせを実装することを選択します。

フォルダーやドキュメント ライブラリなどの配信元の新しいコンテナーを作成し、CDNから使用できるようにするファイルを追加できます。 これは、CDNから使用できる特定の資産セットがあり、CDNアセットのセットをコンテナー内のそれらのファイルのみに制限する場合に適した方法です。

また、既存のサイト コレクション、サイト、ライブラリ、またはフォルダーを配信元として構成することもできます。これにより、コンテナー内のすべての対象資産がCDNから使用できるようになります。 既存のコンテナーを配信元として追加する前に、匿名アクセスや承認されていないユーザーに資産を誤って公開しないように、その内容とアクセス許可を認識しておくことが重要です。

_CDN ポリシー_ を定義して、配信元のコンテンツをCDNから除外できます。 CDN ポリシーは、_ファイルの種類_ や _サイト分類_ などの属性によってパブリックまたはプライベート配信元の資産を除外し、ポリシーで指定した CdnType (プライベートまたはパブリック) のすべての配信元に適用されます。 たとえば、複数のサブサイトを含むサイトで構成されるプライベート配信元を追加する場合、**機密** としてマークされたサイトを除外するポリシーを定義して、その分類が適用されたサイトからコンテンツがCDNから提供されないようにすることができます。 ポリシーは、CDNに追加 _したすべての_ プライベート配信元のコンテンツに適用されます。

配信元の数が多いほど、要求の処理にCDN サービスにかかる時間への影響が大きくなることに注意してください。 配信元の数を可能な限り制限することをお勧めします。

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>各配信元をパブリックまたはプライベートにするかどうかを選択する

配信元を特定するときに、配信元を _パブリック_ にするか _プライベート_ にするかを指定します。 パブリックオリジンのCDNアセットへのアクセスは匿名であり、プライベート配信元のCDNコンテンツは、セキュリティを強化するために動的に生成されたトークンによって保護されます。 選択したオプションに関係なく、Microsoft は、CDN自体の管理に関して、すべての重い作業を行います。 また、CDNを設定して配信元を特定した後で、後で考えを変えることもできます。

パブリック オプションとプライベート オプションはどちらも同様のパフォーマンス向上を提供しますが、それぞれに固有の属性と利点があります。

Office 365 CDN内の **パブリック** オリジンには匿名でアクセスでき、ホストされている資産には資産の URL を持つすべてのユーザーがアクセスできます。 公開されている元の場所のコンテンツへのアクセスは匿名になるため、アクセスしたコンテンツは、機密データ以外の一般的なコンテンツ (JavaScript ファイル、スクリプト、アイコン、画像など) をキャッシュする場合にのみ使用するようにしてください。

Office 365 CDN 内の **非公開** の元の場所は、SharePoint Online ドキュメント ライブラリ、サイト、独自のイメージなど、ユーザー コンテンツへのプライベート アクセスを行う場合に使用します。 プライベート配信元のコンテンツへのアクセスは、動的に生成されたトークンによってセキュリティで保護されるため、元のドキュメント ライブラリまたは保存場所に対するアクセス許可を持つユーザーのみがアクセスできます。 Office 365 CDNのプライベート配信元は、SharePoint Online コンテンツにのみ使用でき、SharePoint Online テナントからのリダイレクトを使用してプライベート配信元のアセットにのみアクセスできます。

プライベートオリジン内のアセットへのアクセスCDN方法の詳細については、「プライベートオリジンでアセットを使用する」[を参照](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)してください。

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>パブリックオリジンでアセットをホストする属性と利点

+ パブリックの配信元で公開されている資産には、すべてのユーザーが匿名でアクセスできます。
    > [!IMPORTANT]
    > ユーザー情報を含むリソースや、組織の機密と見なされるリソースをパブリック配信元に配置しないでください。

+ パブリックの配信元から資産を削除した場合、その資産は最大 30 日間はキャッシュから引き続き使用できます。ただし、CDN 内の資産へのリンクは 15 分以内に無効になります。

+ パブリックの配信元にスタイル シート (CSS ファイル) をホストする場合は、コード内で相対パスと URI を使用できます。 つまり、背景画像と他のオブジェクトの場所を、呼び出し元の資産の場所からの相対位置で参照することができます。

+ パブリック配信元の URL を作成できますが、注意してページ コンテキスト プロパティを使用し、そのガイダンスに従ってください。 CDN にアクセスできなくなった場合、SharePoint Online でその URL は自動的に組織に対して解決されず、結果としてリンクが壊れて他のエラーが発生する可能性があるためです。 また、URL は変更される可能性があるため、現在の値にハードコーディングしないでください。

+ パブリックオリジンに含まれる既定のファイルの種類は、.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2 です。 追加のファイルの種類を指定できます。

+ 指定したサイト分類によって識別された資産を除外するポリシーを構成できます。 たとえば、許可されているファイルの種類のもので、パブリックの配信元にある資産であっても、"社外秘" または "制限付き" としてマークされている資産はすべて除外する、といったことができます。

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>プライベート配信元でアセットをホストする属性と利点

+ プライベート配信元は、SharePoint Online アセットにのみ使用できます。

+ ユーザーは、コンテナーにアクセスするアクセス許可を持っている場合にのみ、プライベート配信元からアセットにアクセスできます。 これらの資産に匿名でアクセスすることはできません。

+ プライベート配信元の資産は、SharePoint Online テナントから参照する必要があります。 プライベート CDN アセットへの直接アクセスは機能しません。

+ プライベート配信元から資産を削除した場合、その資産はキャッシュから最大 1 時間引き続き使用できます。ただし、資産の削除から 15 分以内に、CDN内の資産へのリンクは無効になります。

+ プライベートの配信元用に含まれている既定のファイルの種類は、.gif、.ico、.jpeg、.jpg、.js、.png です。 追加のファイルの種類を指定できます。

+ パブリック配信元と同様に、ワイルドカードを使用してフォルダーまたはドキュメント ライブラリ内のすべての資産を含める場合でも、指定したサイト分類によって識別された資産を除外するポリシーを構成できます。

Office 365 テナントで使用できるOffice 365 CDN、一般的なCDN概念、およびその他の Microsoft CDN を使用する理由の詳細については、「[コンテンツ配信ネットワーク](content-delivery-networks.md)」を参照してください。

### <a name="default-cdn-origins"></a>既定のCDN配信元

特に指定しない限り、Office 365 CDNを有効にすると、既定の配信元が設定Office 365。 最初にプロビジョニングしないことを選択した場合は、セットアップの完了後にこれらの配信元を追加できます。 既定の配信元の設定をスキップした場合の結果を理解し、特定の理由がある場合を除き、CDNを有効にしたときに作成できるようにする必要があります。

既定のプライベート CDN配信元:

+ \*/userphoto.aspx
+ \*/siteassets

既定のパブリック CDN配信元:

+ \*/masterpage
+ \*/style ライブラリ
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ は、2017 年 12 月にOffice 365 CDN サービスに追加された既定のパブリック配信元です。 CDNのSharePoint Frameworkソリューションが機能するためには、この配信元が存在する必要があります。 2017 年 12 月より前にOffice 365 CDNを有効にした場合、またはCDNを有効にしたときに既定の配信元の設定をスキップした場合は、この配信元を手動で追加できます。 詳細については、「[クライアント側の Web パーツまたは SharePoint Framework ソリューションが機能していない」](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)を参照してください。

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>SharePoint Online Management Shell を使用してOffice 365 CDNを設定して構成する

このセクションの手順では、SharePoint Online Management Shell を使用して SharePoint Online に接続する必要があります。 手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

SharePoint Online 管理シェルを使用して、SharePoint Online で資産をホストするようにCDNを設定および構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>組織でOffice 365 CDNを使用できるようにする

テナントCDN設定を変更する前に、Office 365 テナントのプライベート CDN構成の現在の状態を取得する必要があります。 SharePoint Online Management Shell を使用してテナントにConnectします。

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

次に **、Get-SPOTenantCdnEnabled** コマンドレットを使用して、テナントからCDN状態設定を取得します。

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

指定した CdnType のCDNの状態が画面に出力されます。

**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織でOffice 365 CDNを使用できるようにします。 組織でパブリックオリジン、プライベートオリジン、またはその両方を一度に使用できるようにします。 有効にすると、既定の配信元の設定をスキップするようにCDNを構成することもできます。 このトピックで説明するように、これらの配信元は後でいつでも追加できます。

SharePoint Online のWindows PowerShell:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

たとえば、組織でパブリックオリジンとプライベートオリジンの両方を使用できるようにするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

組織でパブリックオリジンとプライベートオリジンの両方を使用し、既定の配信元の設定をスキップできるようにするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

[Office 365 CDNを](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)有効にしたときに既定でプロビジョニングされる配信元と、既定の配信元の設定をスキップした場合の潜在的な影響については、「既定のCDN配信元」を参照してください。

組織でパブリックオリジンを使用できるようにするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

組織でプライベート配信元を使用できるようにするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

このコマンドレットの詳細については、「 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)」を参照してください。

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Office 365 CDNに含めるファイルの種類の一覧を変更する (省略可能)

> [!TIP]
> **Set-SPOTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義する場合は、現在定義されているリストを上書きします。 リストにファイルの種類を追加する場合は、最初にコマンドレットを使用して、既に許可されているファイルの種類を調べ、新しいファイルの種類と共に一覧に含めます。

**Set-SPOTenantCdnPolicy** コマンドレットを使用して、CDNのパブリック配信元とプライベート配信元でホストできる静的ファイルの種類を定義します。 既定では、.css、.gif、.jpg、.jsなどの一般的な資産の種類が許可されます。

SharePoint Online のWindows PowerShell:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

たとえば、.css ファイルと.png ファイルをホストするCDNを有効にするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

CDNで現在許可されているファイルの種類を確認するには、**Get-SPOTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

これらのコマンドレットの詳細については、 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) と [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/) に関するページを参照してください。

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Office 365 CDNから除外するサイト分類の一覧を変更する (省略可能)

> [!TIP]
> **Set-SPOTenantCdnPolicy** コマンドレットを使用してサイト分類を除外すると、現在定義されているリストが上書きされます。 追加のサイト分類を除外する場合は、最初にコマンドレットを使用して、既に除外されている分類を調べ、新しい分類と共に追加します。


  **Set-SPOTenantCdnPolicy** コマンドレットを使用して、CDN で利用できるようにしないサイトの分類を除外します。 既定で除外されるサイトの分類はありません。

SharePoint Online のWindows PowerShell:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

現在制限されているサイト分類を確認するには、 **Get-SPOTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

返されるプロパティは _、IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 、 _ExcludeIfNoScriptDisabled です_。

_IncludeFileExtensions_ プロパティには、CDNから提供されるファイル拡張子の一覧が含まれています。

> [!NOTE]
> 既定のファイル拡張子は、パブリックとプライベートの間で異なります。

_ExcludeRestrictedSiteClassifications_ プロパティには、CDNから除外するサイト分類が含まれています。 たとえば、**機密** としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツがCDNから提供されないようにすることができます。

_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性設定に基づいて、CDNからコンテンツを除外します。 既定では、_NoScript_ 属性は _[モダン_ サイト **に対して有効]** に設定され、_クラシック_ サイトでは **[無効] に設定されます**。 これは、テナントの設定によって異なります。

これらのコマンドレットの詳細については、 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) と [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/) に関するページを参照してください。

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>アセットの配信元を追加する

**Add-SPOTenantCdnOrigin** コマンドレットを使用して、配信元を定義します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

> [!IMPORTANT]
> ユーザー情報を含むリソースや、組織の機密と見なされるリソースをパブリック配信元に配置しないでください。

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_パス_ の値は、アセットを含むライブラリまたはフォルダーへの相対パスです。 相対パスに加え、ワイルドカードも使用できます。 配信元では、URL の前にワイルドカードが追加されます。 これにより、複数のサイトにまたがる配信元を作成できます。 たとえば、CDN内のパブリック配信元として、すべてのサイトの masterpages フォルダーにすべてのアセットを含めるには、次のコマンドを入力します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ ワイルドカード修飾子 ***/** はパスの先頭でのみ使用でき、指定した URL の下にあるすべての URL セグメントと一致します。
+ このパスは、ドキュメント ライブラリ、フォルダー、またはサイトを指すことができます。 たとえば、パス _*/site1 は、サイト_ の下にあるすべてのドキュメント ライブラリと一致します。

特定の相対パスを持つ配信元を追加できます。 完全なパスを使用して配信元を追加することはできません。

この例では、特定のサイトに siteassets ライブラリのプライベートオリジンを追加します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

次の使用例は、サイト コレクションのサイト資産ライブラリに _folder1_ フォルダーのプライベート配信元を追加します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換えることができます。 次の例では、サイト コレクションのサイト資産ライブラリに _フォルダー 1_ フォルダーのプライベート配信元を追加します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

このコマンドとその構文の詳細については、「 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)」を参照してください。

> [!NOTE]
> プライベート配信元では、配信元から共有されるアセットに、CDNからアクセスする前にメジャー バージョンが発行されている必要があります。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>例: マスター ページと、SharePoint Online 用のスタイル ライブラリのパブリック配信元を構成する

通常、これらの配信元は、Office 365 CDNを有効にすると既定で設定されます。 ただし、手動で有効にする場合は、次の手順に従います。

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、スタイル ライブラリをパブリックオリジンとして定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、マスター ページをパブリックオリジンとして定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

このコマンドとその構文の詳細については、「 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>例: サイト資産、サイト ページ、および SharePoint Online 用の発行イメージのプライベート配信元を構成する

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト資産フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベート配信元として定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ **Add-SPOTenantCdnOrigin** コマンドレットを使用して、発行イメージ フォルダーをプライベート配信元として定義します。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

このコマンドとその構文の詳細については、「 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>例: SharePoint Online のサイト コレクションのプライベート配信元を構成する

**Add-SPOTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。 次に例を示します。

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

このコマンドとその構文の詳細については、「 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 SharePoint Online テナントがCDN サービスに接続するときに予期される _構成保留中_ のメッセージが表示される場合があります。 これには最大 15 分かかる場合があります。

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Office 365 CDNを管理する

CDNを設定したら、このセクションで説明するように、コンテンツの更新時やニーズの変化に応じて構成を変更できます。

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Office 365 CDNからアセットを追加、更新、または削除する

セットアップ手順が完了したら、新しいアセットを追加し、必要に応じて既存のアセットを更新または削除できます。 配信元として識別したフォルダーまたはSharePoint ライブラリ内のアセットに変更を加えるだけです。 新しい資産を追加すると、CDNからすぐに使用できます。 ただし、資産を更新すると、新しいコピーが反映されてCDNで使用可能になるまでに最大で 15 分かかります。

配信元の場所を取得する必要がある場合は、 **Get-SPOTenantCdnOrigins** コマンドレットを使用できます。 このコマンドレットの使用方法については、「 [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)」を参照してください。

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Office 365 CDNから配信元を削除する

配信元として識別したフォルダーまたはSharePoint ライブラリへのアクセス権を削除できます。 これを行うには、 **Remove-SPOTenantCdnOrigin** コマンドレットを使用します。

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

このコマンドレットの使用方法については、「 [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)」を参照してください。

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Office 365 CDNで配信元を変更する

作成した配信元は変更できません。 代わりに、配信元を削除してから、新しい配信元を追加します。 詳細については、「[Office 365 CDNから配信元を削除するには](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)」と「[アセットの配信元を追加するには」を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Office 365 CDNを無効にする

**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織のCDNを無効にします。 CDNに対してパブリックオリジンとプライベートオリジンの両方が有効になっている場合は、次の例に示すようにコマンドレットを 2 回実行する必要があります。

CDNでパブリック配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

CDNでプライベート配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

このコマンドレットの詳細については、「 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)」を参照してください。

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>PnP PowerShell を使用してOffice 365 CDNを設定して構成する

このセクションの手順では、PnP PowerShell を使用して SharePoint Online に接続する必要があります。 手順については、「 [PnP PowerShell の概要](https://github.com/SharePoint/PnP-PowerShell#getting-started)」を参照してください。

PnP PowerShell を使用してSharePoint Online で資産をホストするようにCDNを設定して構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>組織でOffice 365 CDNを使用できるようにする

テナントCDN設定を変更する前に、Office 365 テナントのプライベート CDN構成の現在の状態を取得する必要があります。 PnP PowerShell を使用してテナントにConnectします。

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

次に **、Get-PnPTenantCdnEnabled** コマンドレットを使用して、テナントからCDN状態設定を取得します。

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

指定した CdnType のCDNの状態が画面に出力されます。

**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織でOffice 365 CDNを使用できるようにします。 組織でパブリックオリジン、プライベート配信元、またはその両方を同時に使用できるようにします。 有効にすると、既定の配信元の設定をスキップするようにCDNを構成することもできます。 このトピックで説明するように、これらの配信元は後でいつでも追加できます。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

たとえば、組織でパブリックオリジンとプライベートオリジンの両方を使用できるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

組織でパブリックオリジンとプライベートオリジンの両方を使用し、既定の配信元の設定をスキップできるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

[Office 365 CDNを](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)有効にしたときに既定でプロビジョニングされる配信元と、既定の配信元の設定をスキップした場合の潜在的な影響については、「既定のCDN配信元」を参照してください。

組織でパブリックオリジンを使用できるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

組織でプライベート配信元を使用できるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

このコマンドレットの詳細については、「 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)」を参照してください。

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Office 365 CDNに含めるファイルの種類の一覧を変更する (省略可能)

> [!TIP]
> **Set-PnPTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義する場合は、現在定義されているリストを上書きします。 リストにファイルの種類を追加する場合は、最初にコマンドレットを使用して、既に許可されているファイルの種類を調べ、新しいファイルの種類と共に一覧に含めます。

**Set-PnPTenantCdnPolicy** コマンドレットを使用して、CDNのパブリック配信元とプライベート配信元でホストできる静的ファイルの種類を定義します。 既定では、.css、.gif、.jpg、.jsなどの一般的な資産の種類が許可されます。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

たとえば、.css ファイルと.png ファイルをホストするCDNを有効にするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

CDNで現在許可されているファイルの種類を確認するには、**Get-PnPTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

これらのコマンドレットの詳細については、 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) と [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies) に関するページを参照してください。

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Office 365 CDNから除外するサイト分類の一覧を変更する (省略可能)

> [!TIP]
> **Set-PnPTenantCdnPolicy** コマンドレットを使用してサイト分類を除外すると、現在定義されているリストが上書きされます。 追加のサイト分類を除外する場合は、最初にコマンドレットを使用して、既に除外されている分類を調べ、新しい分類と共に追加します。

**Set-PnPTenantCdnPolicy** コマンドレットを使用して、CDNで使用できないようにするサイト分類を除外します。 既定で除外されるサイトの分類はありません。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

現在制限されているサイト分類を確認するには、 **Get-PnPTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

返されるプロパティは _、IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 、 _ExcludeIfNoScriptDisabled です_。

_IncludeFileExtensions_ プロパティには、CDNから提供されるファイル拡張子の一覧が含まれています。

> [!NOTE]
> 既定のファイル拡張子は、パブリックとプライベートの間で異なります。

_ExcludeRestrictedSiteClassifications_ プロパティには、CDNから除外するサイト分類が含まれています。 たとえば、**機密** としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツがCDNから提供されないようにすることができます。

_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性設定に基づいて、CDNからコンテンツを除外します。 既定では、_NoScript_ 属性は _[モダン_ サイト **に対して有効]** に設定され、_クラシック_ サイトでは **[無効] に設定されます**。 これは、テナントの設定によって異なります。

これらのコマンドレットの詳細については、 [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) と [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies) に関するページを参照してください。

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>アセットの配信元を追加する

**Add-PnPTenantCdnOrigin** コマンドレットを使用して、配信元を定義します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

> [!IMPORTANT]
> ユーザー情報を含むリソースや、組織の機密と見なされるリソースをパブリック配信元に配置しないでください。

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_パス_ の値は、アセットを含むライブラリまたはフォルダーへの相対パスです。 相対パスに加え、ワイルドカードも使用できます。 配信元では、URL の前にワイルドカードが追加されます。 これにより、複数のサイトにまたがる配信元を作成できます。 たとえば、CDN内のパブリック配信元として、すべてのサイトの masterpages フォルダーにすべてのアセットを含めるには、次のコマンドを入力します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ ワイルドカード修飾子 ***/** はパスの先頭でのみ使用でき、指定した URL の下にあるすべての URL セグメントと一致します。
+ このパスは、ドキュメント ライブラリ、フォルダー、またはサイトを指すことができます。 たとえば、パス _*/site1 は、サイト_ の下にあるすべてのドキュメント ライブラリと一致します。

特定の相対パスを持つ配信元を追加できます。 完全なパスを使用して配信元を追加することはできません。

次の使用例は、サイト資産ライブラリのプライベート配信元を特定のサイトに追加します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

次の使用例は、サイト コレクションのサイト資産ライブラリに _folder1_ フォルダーのプライベート配信元を追加します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

パスにスペースがある場合は、パスを二重引用符で囲むか、スペースを URL エンコード %20 に置き換えることができます。 次の例では、サイト コレクションのサイト資産ライブラリに _フォルダー 1_ フォルダーのプライベート配信元を追加します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)」を参照してください。

> [!NOTE]
> プライベート配信元では、配信元から共有されるアセットに、CDNからアクセスする前にメジャー バージョンが発行されている必要があります。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>例: マスター ページと、SharePoint Online 用のスタイル ライブラリのパブリック配信元を構成する

通常、これらの配信元は、Office 365 CDNを有効にすると既定で設定されます。 ただし、手動で有効にする場合は、次の手順に従います。

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、スタイル ライブラリをパブリックオリジンとして定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、マスター ページをパブリック配信元として定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>例: サイト資産、サイト ページ、および SharePoint Online 用の発行イメージのプライベート配信元を構成する

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト資産フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト ページ フォルダーをプライベートオリジンとして定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、発行イメージ フォルダーをプライベート配信元として定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>例: SharePoint Online のサイト コレクションのプライベート配信元を構成する

**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。 次に例を示します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 SharePoint Online テナントがCDN サービスに接続するときに予期される _構成保留中_ のメッセージが表示される場合があります。 これには最大 15 分かかる場合があります。

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Office 365 CDNを管理する

CDNを設定したら、このセクションで説明するように、コンテンツの更新時やニーズの変化に応じて構成を変更できます。

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Office 365 CDNからアセットを追加、更新、または削除する

セットアップ手順が完了したら、新しいアセットを追加し、必要に応じて既存のアセットを更新または削除できます。 配信元として識別したフォルダーまたはSharePoint ライブラリ内のアセットに変更を加えるだけです。 新しい資産を追加すると、CDNからすぐに使用できます。 ただし、資産を更新すると、新しいコピーが反映されてCDNで使用可能になるまでに最大で 15 分かかります。

配信元の場所を取得する必要がある場合は、 **Get-PnPTenantCdnOrigin コマンドレットを** 使用できます。 このコマンドレットの使用方法については、「 [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)」を参照してください。

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Office 365 CDNから配信元を削除する

配信元として識別したフォルダーまたはSharePoint ライブラリへのアクセス権を削除できます。 これを行うには、 **Remove-PnPTenantCdnOrigin** コマンドレットを使用します。

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

このコマンドレットの使用方法については、「 [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)」を参照してください。

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Office 365 CDNで配信元を変更する

作成した配信元は変更できません。 代わりに、配信元を削除してから、新しい配信元を追加します。 詳細については、「[Office 365 CDNから配信元を削除するには](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)」と「[アセットの配信元を追加するには」を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Office 365 CDNを無効にする

**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織のCDNを無効にします。 CDNに対してパブリックオリジンとプライベートオリジンの両方が有効になっている場合は、次の例に示すようにコマンドレットを 2 回実行する必要があります。

CDNでパブリック配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

CDNでプライベート配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

このコマンドレットの詳細については、「 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)」を参照してください。

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-cli-for-microsoft-365"></a>MICROSOFT 365用の CLI を使用してOffice 365 CDNを設定して構成する

このセクションの手順では、[Microsoft 365用の CLI](https://aka.ms/cli-m365) をインストールしている必要があります。 次に、[login](https://pnp.github.io/cli-microsoft365/cmd/login/) コマンドを使用して、Office 365 テナントに接続します。

MICROSOFT 365用 CLI を使用して、SharePoint Online で資産をホストするCDNを設定して構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-the-office-365-cdn"></a>Office 365 CDNを有効にする

テナントの Office 365 CDN の状態は [spo cdn set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-set/) コマンドを使用して管理できます。

テナントで Office 365 パブリック CDN を有効にするには、次のように実行します。

```cli
spo cdn set --type Public --enabled true
```

Office 365 SharePoint CDNを有効にするには、次のコマンドを実行します。

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Office 365 CDN の現在の状況を確認する

特定の種類のOffice 365 CDNが有効または無効になっているかどうかを確認するには、[spo cdn get](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-get/) コマンドを使用します。

Office 365 パブリック CDN が有効かどうかを確認するには、次のように実行します。

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Office 365 CDNの配信元を表示する

現在構成されている Office 365 パブリック CDN の配信元を確認するには、次のように実行します。

```cli
spo cdn origin list --type Public
```

[Office 365 CDNを](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)有効にしたときに既定でプロビジョニングされる配信元については、「既定のCDN配信元」を参照してください。

### <a name="add-an-office-365-cdn-origin"></a>Office 365 CDNの配信元を追加する

> [!IMPORTANT]
> 組織に依存していると見なされるリソースを、パブリック配信元として構成されたSharePointドキュメント ライブラリに配置しないでください。

[spo cdn origin add](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-add/) コマンドを使用して CDN の配信元を定義します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

アセットを含むフォルダーへの相対パスはどこにありますか `path` 。 相対パスに加え、ワイルドカードも使用できます。

すべてのサイトの **マスター ページ ギャラリー** 内のすべてのアセットをパブリックオリジンとして含めるには、次のコマンドを実行します。

```cli
spo cdn origin add --type Public --origin */masterpage
```

特定のサイト コレクションのプライベートの配信元を構成するには、次のように実行します。

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> CDN の配信元の追加後、CDN サービス経由でファイルを取得できるようになるまで最大 15 分かかることがあります。 特定の配信元が既に有効かどうかは、[spo cdn origin list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-list/) コマンドを使用して検証できます。

### <a name="remove-an-office-365-cdn-origin"></a>Office 365 CDNの配信元を削除する

[spo cdn origin remove](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-remove/) コマンドを使用して、指定した種類の CDN の配信元を削除します。

CDN構成からパブリック配信元を削除するには、次のコマンドを実行します。

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> CDN配信元を削除しても、その配信元と一致するドキュメント ライブラリに格納されているファイルには影響しません。 これらのアセットがSharePoint URL を使用して参照されている場合、SharePointはドキュメント ライブラリを指す元の URL に自動的に切り替わります。 ただし、パブリック CDN URL を使用してアセットが参照されている場合は、配信元を削除するとリンクが中断され、手動で変更する必要があります。

### <a name="modify-an-office-365-cdn-origin"></a>Office 365 CDNの原点を変更する

既存の CDN の配信元を変更することはできません。 代わりに、`spo cdn origin remove` コマンドを使用して定義済みの CDN の配信元を削除して、`spo cdn origin add` コマンドで新しい配信元を作成する必要があります。

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Office 365 CDNに含めるファイルの種類を変更する

既定では、_.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2_ というファイルの種類がCDNに含まれています。 CDN に他の種類のファイルを含める必要がある場合、[spo cdn policy set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して CDN 構成を変更できます。

> [!NOTE]
> ファイルの種類のリストを変更する場合、現在定義されているリストを上書きします。 他のファイルの種類を追加する場合は、[spo cdn policy list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-list/) コマンドを最初に使用して現在構成されているファイルの種類を確認します。

パブリック CDNに含まれる既定のファイルの種類の一覧に _JSON_ ファイルの種類を追加するには、次のコマンドを実行します。

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Office 365 CDN から除外するサイトの分類のリストを変更する

[spo cdn policy set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して、CDN で利用できるようにしないサイトの分類を除外します。 既定で除外されるサイトの分類はありません。

> [!NOTE]
> 除外するサイトの分類のリストを変更する場合、現在定義されているリストを上書きします。 他の分類を除外する場合は、[spo cdn policy list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-list/) コマンドを最初に使用して現在構成されている分類を確認します。

_HBI_ として分類されたサイトをパブリック CDNから除外するには、次のコマンドを実行します。

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Office 365 CDNを無効にする

Office 365 CDN を無効にするには、`spo cdn set` コマンドを使用します。たとえば、次のように実行します。

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>CDNアセットの使用

CDNを有効にし、配信元とポリシーを構成したので、CDNアセットの使用を開始できます。

このセクションは、SharePoint ページとコンテンツでCDN URL を使用する方法を理解するのに役立ちます。これにより、SharePointはパブリックオリジンとプライベート配信元の両方のアセットの要求をCDNにリダイレクトします。

+ [CDNアセットへのリンクの更新](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [パブリックオリジンでのアセットの使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [プライベート配信元でのアセットの使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

クライアント側 Web パーツをホストするためにCDNを使用する方法については、「Office 365 CDN[からクライアント側 Web パーツをホストする (パート 4)Hello World](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)」を参照してください。

> [!NOTE]
> _ClientSideAssets_ フォルダーを **プライベート** CDN配信元の一覧に追加すると、CDNホストされているカスタム Web パーツのレンダリングに失敗します。 SPFX Web パーツで使用されるファイルはパブリック CDNのみを使用でき、ClientSideAssets フォルダーはパブリック CDNの既定の配信元です。

### <a name="updating-links-to-cdn-assets"></a>CDNアセットへのリンクの更新

配信元に追加したアセットを使用するには、元のファイルへのリンクを、配信元のファイルへのパスで更新するだけです。

+ 配信元に追加したアセットへのリンクを含むページまたはコンテンツを編集します。 また、複数の方法のいずれかを使用して、入力サイトまたはサイト コレクション全体のリンクをグローバルに検索して置き換えることができます。リンクを特定のアセットに表示されるすべての場所に更新する場合は、サイトまたはサイト コレクション全体でリンクを更新します。
+ 配信元のアセットへのリンクごとに、パスをCDNの配信元のファイルへのパスに置き換えます。 相対パスを使用できます。
+ ページまたはコンテンツを保存します。

たとえば、ドキュメント ライブラリ フォルダー _/site/CDN_origins/public/_ にコピーしたイメージ _/site/SiteAssets/images/image.png_ を考えてみましょう。 CDNアセットを使用するには、イメージ ファイルの場所への元のパスを配信元へのパスに置き換えて、新しい URL _/site/CDN_origins/public/image.png_ を作成します。

相対パスの代わりに資産への完全な URL を使用する場合は、次のようにリンクを作成します。

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> 一般に、URL をCDN内のアセットに直接ハードコーディングしないでください。 ただし、必要に応じて、パブリック配信元のアセットの URL を手動で作成できます。 詳細については、「[パブリック資産のハードコーディング CDN URL」を](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)参照してください。

CDNからアセットが提供されていることを確認する方法については、「[Office 365 CDNのトラブルシューティング」の「CDNによってアセットが提供されていることを確認](use-microsoft-365-cdn-with-spo.md#CDNConfirm)する[操作方法」を](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)参照してください。

### <a name="using-assets-in-public-origins"></a>パブリックオリジンでのアセットの使用

SharePoint Online の **発行機能** では、パブリック配信元に格納されている資産の URL が自動的にCDN相当する URL に書き換え、アセットがSharePointではなくCDN サービスから提供されるようにします。

配信元が発行機能が有効になっているサイトにあり、CDNにオフロードするアセットが次のいずれかのカテゴリにある場合、SharePointは、CDN ポリシーによって除外されていない資産に対して配信元のアセットの URL を自動的に書き換えることになります。

SharePoint 発行機能によって自動的に書き換えられるのは次のようなリンクです。

+ 従来の発行ページの HTML 応答の IMG/LINK/CSS URL
  + これには、ページの HTML コンテンツ内に作成者によって追加された画像が含まれます。
+ 画像ライブラリ スライドショー Web パーツの画像 URL
+ SPList REST API (RenderListDataAsStream) 結果の画像フィールド
  + 新しいプロパティ _ImageFieldsToTryRewriteToCdnUrls_ を使用して、フィールドのコンマ区切りリストを指定します
  + ハイパーリンク フィールドと PublishingImage フィールドをサポートしています
+ SharePointイメージの表示

次の図は、SharePointがパブリックオリジンからアセットを含むページの要求を受信したときのワークフローを示しています。

![ワークフロー図: パブリックオリジンからOffice 365 CDNアセットを取得する。](../media/O365-CDN/o365-cdn-public-steps-transparent.png "ワークフロー: パブリックオリジンからOffice 365 CDNアセットを取得する")

> [!TIP]
> ページ上の特定の URL の自動書き換えを無効にする場合は、ページをチェックアウトしてクエリ文字列パラメーターを追加できます **。無効にする各リンクの末尾に NoAutoReWrites=true** 。

#### <a name="constructing-cdn-urls-for-public-assets"></a>パブリック資産のCDN URL の作成

公開元に対して _発行_ 機能が有効になっていない場合、またはアセットがCDN サービスの自動書き換え機能でサポートされているリンクの種類の 1 つではない場合は、アセットのCDNの場所に URL を手動で作成し、コンテンツ内のこれらの URL を使用できます。

> [!NOTE]
> URL の最後のセクションを形成する必要なアクセス トークンは、リソースの要求時に生成されるため、プライベート配信元のアセットに対してCDN URL をハードコーディングまたは構築することはできません。 パブリック CDNの URL を作成できます。変更される可能性があるため、URL をハードコーディングしないでください。

パブリック CDNアセットの場合、URL 形式は次のようになります。

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

**TenantHostName を** テナント名に置き換えます。 例:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> ページ コンテキスト プロパティは、ハード コーディング ""https://publiccdn.sharepointonline.com ではなくプレフィックスを作成するために使用する必要があります。 URL は変更される可能性があるため、ハード コーディングしないでください。 クラシック SharePoint Online で表示テンプレートを使用している場合は、URL のプレフィックスとして表示テンプレートのプロパティ "window._spPageContextInfo.publicCdnBaseUrl" を使用できます。 モダンおよびクラシック SharePointの Web パーツをSPFxする場合は、プロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" を使用できます。 これにより、プレフィックスが変更された場合に実装が更新されるようにプレフィックスが提供されます。 SPFxの例として、URL はプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" を使用して構築できます。 [シーズン 1 パフォーマンス シリーズ](https://aka.ms/sppnp-perfvideos)の一部である[クライアント側コードでのCDNの使用](https://youtu.be/IH1RbQlbhIA)に関するページを参照してください


### <a name="using-assets-in-private-origins"></a>プライベート配信元でのアセットの使用

プライベート配信元でアセットを使用するために追加の構成は必要ありません。 SharePoint Online では、プライベート配信元のアセットの URL が自動的に書き換えられます。そのため、それらの資産に対する要求は常にCDNから提供されます。 これらの URL には、資産が要求された時点で SharePoint Online によって自動生成する必要があるトークンが含まれているため、プライベート配信元のCDNアセットに対して URL を手動で作成することはできません。

プライベート配信元の資産へのアクセスは、配信元に対するユーザーのアクセス許可に基づいて動的に生成されたトークンによって保護されます。この点については、次のセクションで説明します。 ユーザーがコンテンツをレンダリングするには、少なくともCDNの配信元への **読み取り** アクセス権が必要です。

次の図は、プライベート配信元からアセットを含むページの要求をSharePointが受信したときのワークフローを示しています。

![ワークフロー図: プライベートオリジンからOffice 365 CDNアセットを取得する。](../media/O365-CDN/o365-cdn-private-steps-transparent.png "ワークフロー: プライベートオリジンからOffice 365 CDNアセットを取得する")

#### <a name="token-based-authorization-in-private-origins"></a>プライベート配信元でのトークン ベースの承認

Office 365 CDN内のプライベート配信元の資産へのアクセスは、SharePoint Online によって生成されたトークンによって付与されます。 配信元によって指定されたフォルダーまたはライブラリへのアクセス許可を既に持っているユーザーには、ユーザーがアクセス許可レベルに基づいてファイルにアクセスできるようにするトークンが自動的に付与されます。 これらのアクセス トークンは、トークン再生攻撃を防ぐために生成されてから 30 分から 90 分間有効です。

アクセス トークンが生成されると、SharePoint Online は、2 つの承認パラメーター _eat_ (エッジ承認トークン) と _oat_ (配信元承認トークン) を含むカスタム URI をクライアントに返します。 各トークンの構造は _<エポック時間形式の有効期限'>__<'secure signature'>_ です。 次に例を示します。

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> トークンを所有しているユーザーは、CDN内のリソースにアクセスできます。 ただし、これらのアクセス トークンを含む URL は HTTPS 経由でのみ共有されるため、トークンの有効期限が切れる前にエンド ユーザーによって URL が明示的に共有されていない限り、資産は承認されていないユーザーからアクセスできなくなります。

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>アイテム レベルのアクセス許可は、プライベート配信元の資産ではサポートされていません

SharePoint Online では、プライベート配信元の資産に対するアイテム レベルのアクセス許可はサポートされないことに注意してください。 たとえば、次の条件を満たすファイルの `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`場合、ユーザーはファイルに効果的にアクセスできます。

|ユーザー  |アクセス許可  |効果的なアクセス  |
|---------|---------|---------|
|ユーザー 1     |folder1 にアクセスできます         |CDNからimage1.jpgにアクセスできます         |
|ユーザー 2     |folder1 にアクセスできない         |CDNからimage1.jpgにアクセスできない         |
|ユーザー 3     |folder1 にはアクセスできませんが、SharePoint Online のimage1.jpgにアクセスするための明示的なアクセス許可が付与されます         |SharePoint Online から直接アセット image1.jpgにアクセスできますが、CDNからアクセスすることはできません。         |
|ユーザー 4     |folder1 にアクセスできますが、SharePoint Online でimage1.jpgへのアクセスが明示的に拒否されました         |SharePoint Online から資産にアクセスすることはできませんが、SharePoint Online でファイルへのアクセスが拒否されているにもかかわらず、CDNから資産にアクセスできます         |

<a name="CDNTroubleshooting"></a>

## <a name="troubleshooting-the-office-365-cdn"></a>Office 365 CDNのトラブルシューティング

<a name="CDNConfirm"></a>

### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>CDNによって資産が提供されていることを確認操作方法。

CDNアセットへのリンクをページに追加したら、ページを参照し、画像を右クリックしてイメージ URL を確認することで、CDNからアセットが提供されていることを確認できます。

ブラウザーの開発者ツールを使用して、ページ上の各資産の URL を表示したり、サード パーティのネットワーク トレース ツールを使用したりすることもできます。

> [!NOTE]
> Fiddler などのネットワーク ツールを使用して、SharePoint ページからアセットをレンダリングする以外のアセットをテストする場合は、URL がSharePoint Online テナントのルート URL である GET 要求に、参照元ヘッダー "Referer: `https://yourdomain.sharepoint.com`" を手動で追加する必要があります。

CDN URL を Web ブラウザーで直接テストすることはできません。これは、SharePoint Online からの参照元が必要であるためです。 ただし、CDNアセット URL をSharePoint ページに追加し、ブラウザーでページを開くと、CDNアセットがページにレンダリングされます。

Microsoft Edge ブラウザーで開発者ツールを使用する方法の詳細については、「[開発者ツールのMicrosoft Edge](/microsoft-edge/devtools-guide)」を参照してください。

[SharePoint開発者パターンとプラクティス YouTube チャネル](https://aka.ms/sppnp-videos)でホストされている短いビデオを視聴して、CDNが機能していることを確認する方法については、「[CDNの使用状況を確認し、最適なネットワーク接続を確保する](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)」を参照してください。

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>新しい配信元のアセットが利用できないのはなぜですか?
新しい配信元のアセットは、登録がCDNを通じて伝達され、アセットが配信元からCDNストレージにアップロードされるまでに時間がかかるため、すぐに使用することはできません。 CDNでアセットを使用するために必要な時間は、アセットの数とファイル サイズによって異なります。

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>クライアント側の Web パーツまたはSharePoint Framework ソリューションが機能しない

パブリック配信元のOffice 365 CDNを有効にすると、CDN サービスによって次の既定の配信元が自動的に作成されます。

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

*/clientsideassets 配信元が見つからない場合、SharePoint Frameworkソリューションは失敗し、警告メッセージやエラー メッセージは生成されません。 この配信元は、_-NoDefaultOrigins_ パラメーターが **$true** に設定されたCDNが有効になっているか、または配信元が手動で削除されたために欠落している可能性があります。

次の PowerShell コマンドを使用して、どの配信元が存在するかを確認できます。

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

または、Office 365 CLI で確認することもできます。

```cli
spo cdn origin list
```

PowerShell で配信元を追加するには:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Office 365 CLI で配信元を追加するには:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Office 365 CDNを操作するために必要な PowerShell モジュールと CLI シェルは何ですか?

**SharePoint Online Management Shell** PowerShell モジュールまたはOffice 365 CLI を使用して **、Office 365 CDN** を操作することもできます。

+ [SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [Office 365 CLI のインストール](https://pnp.github.io/cli-microsoft365/user-guide/installing-cli/)

## <a name="see-also"></a>関連項目

[Content Delivery Network](./content-delivery-networks.md)

[Office 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[SharePoint パフォーマンス シリーズ - Office 365 CDN ビデオ シリーズ](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
