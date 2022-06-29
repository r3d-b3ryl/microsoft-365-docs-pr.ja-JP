---
title: SharePoint Online で Office 365 コンテンツ配信ネットワーク (CDN) を使用する
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
description: Office 365 コンテンツ配信ネットワーク (CDN) を使用して SharePoint Online アセットの配信を高速化する方法について説明します。
ms.openlocfilehash: 19a6ef51c73340c9f048ffa60208a5216a1959db
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66492515"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>SharePoint Online での Office 365 コンテンツ配信ネットワーク (CDN) の使用

組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用して静的資産をホストすることで、SharePoint Online ページのパフォーマンスを向上させることができます。 Office 365 CDN では、静的資産を要求しているブラウザーの近くに静的資産をキャッシュするとパフォーマンスが向上します。これにより、ダウンロードが速くなり、待ち時間が短縮されます。 また、Office 365 CDN では、圧縮と HTTP パイプラインを強化するために [HTTP/2 プロトコル](https://en.wikipedia.org/wiki/HTTP/2)を使用します。 Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

> [!NOTE]
> Office 365 CDN は、**本番** (ワールドワイド) クラウドのテナントのみが利用できます。 現在、米国政府および中国のクラウドのテナントは、Office 365 CDN をサポートしていません。

Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。 Office 365 CDN でホストするコンテンツの種類に応じて、**公開**、**非公開**、またはその両方の元の場所を追加できます。 パブリックオリジンとプライベートオリジンの違いの詳細については、「 [各配信元をパブリックまたはプライベートにするかどうかを選択](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) する」を参照してください。

![CDN 概念図Office 365。](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN の概念図")

CDN の動作に既に精通している場合は、テナントの Office 365 CDN を有効にするには、いくつかの手順を完了するだけで済みます。 このトピックでは、その方法について説明します。 静的資産のホスティングを開始する方法の詳細については、こちらを参照してください。

> [!TIP]
> 特殊な使用シナリオにOffice 365で使用できる他の Microsoft ホスト CDN がありますが、このトピックでは説明しませんが、Office 365 CDN の範囲外であるためです。 詳細については、「 [その他の Microsoft CDN」を](content-delivery-networks.md#other-microsoft-cdns)参照してください。

 **[Office 365のネットワーク計画とパフォーマンスのチューニングに](./network-planning-and-performance.md)戻ります。**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>SharePoint Online での Office 365 CDN の操作の概要

組織の Office 365 CDN を設定するには、次の基本的な手順に従います。

+ [Office 365 CDN のデプロイを計画する](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [CDN でホストする静的資産を決定](use-microsoft-365-cdn-with-spo.md#CDNAssets)します。
  + [資産を格納する場所を決定します](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。 この場所は、SharePoint サイト、ライブラリ、またはフォルダーであり、 _配信元_ と呼ばれます。
  + [各配信元をパブリックまたはプライベートにするかどうかを選択](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)します。 パブリック型とプライベート型の両方のオリジンを複数追加できます。

+ PowerShell または CLI for Microsoft 365 を使用して CDN を設定して構成する

  + [SharePoint Online 管理シェルを使用して CDN を設定して構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [PnP PowerShell を使用して CDN を設定して構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [MICROSOFT 365 用 CLI を使用して CDN を設定して構成する](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  この手順を完了すると、次のようになります。

  + 組織の CDN を有効にしました。
  + 配信元を追加し、各配信元をパブリックまたはプライベートとして識別しました。

セットアップが完了したら、次の方法で[Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) を時間の経過と共に管理できます。

+ アセットの追加、更新、削除
+ 配信元の追加と削除
+ CDN ポリシーの構成
+ 必要に応じて、CDN を無効にする

最後に、「 [CDN アセットを使用して](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) 、パブリックオリジンとプライベートオリジンの両方から CDN アセットにアクセスする方法について説明します。

一般的な問題の解決に関するガイダンスについては、「[Office 365 CDN のトラブルシューティング](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)」を参照してください。

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Office 365 CDN のデプロイを計画する

Office 365 テナントにOffice 365 CDN をデプロイする前に、計画プロセスの一環として次の要素を考慮する必要があります。

  + [CDN でホストする静的資産を決定する](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [資産を格納する場所を決定する](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [各配信元をパブリックまたはプライベートにするかどうかを選択する](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>CDN でホストする静的資産を決定する

一般に、CDN は _、静的資産_、またはあまり頻繁に変更されない資産をホストする場合に最も効果的です。 適切な経験則は、次の条件の一部またはすべてを満たすファイルを識別することです。

+ ページに埋め込まれた静的ファイル (スクリプトやイメージなど) は、ページの読み込み時間に大きな影響を与える可能性があります
+ 実行可能ファイルやインストール ファイルなどの大きなファイル
+ クライアント側のコードをサポートするリソース ライブラリ

たとえば、サイト イメージやスクリプトのように繰り返し要求される小さなファイルは、サイトレンダリングのパフォーマンスを大幅に向上させ、CDN 配信元に追加するときに SharePoint Online サイトの負荷を段階的に減らすことができます。 インストール実行可能ファイルなどの大きなファイルは CDN からダウンロードでき、パフォーマンスへの影響が高く、SharePoint Online サイトに頻繁にアクセスされない場合でも、その後の負荷の削減につながります。

ファイルごとのパフォーマンスの向上は、最も近い CDN エンドポイントへのクライアントの近接性、ローカル ネットワーク上の一時的な条件など、多くの要因に依存します。 多くの静的ファイルは非常に小さく、Office 365から 1 秒未満でダウンロードできます。 ただし、Web ページには、累積ダウンロード時間が数秒の埋め込みファイルが多数含まれている場合があります。 CDN からこれらのファイルを提供すると、ページ全体の読み込み時間を大幅に短縮できます。 例については、「 [CDN によってどのようなパフォーマンスの向上が得られますか?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) 」を参照してください。

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>資産を格納する場所を決定する

CDN では、_配信元_ と呼ばれる場所からアセットをフェッチします。 配信元には、URL でアクセスできる SharePoint サイト、ドキュメント ライブラリ、またはフォルダーを指定できます。 組織の配信元を指定する場合は、優れた柔軟性があります。 たとえば、複数の配信元を指定したり、すべての CDN 資産を配置する 1 つの配信元を指定したりできます。 組織の元の場所としてパブリックとプライベートの両方を指定することができます。 ほとんどの組織は、2 つを組み合わせて実装します。

フォルダーやドキュメント ライブラリなどの配信元の新しいコンテナーを作成し、CDN から使用できるようにするファイルを追加できます。 これは、CDN から使用できるようにする特定の資産セットがあり、CDN 資産のセットをコンテナー内のファイルのみに制限する場合に適した方法です。

また、既存のサイト コレクション、サイト、ライブラリ、またはフォルダーを配信元として構成することもできます。これにより、コンテナー内のすべての適格な資産が CDN から使用できるようになります。 既存のコンテナーを配信元として追加する前に、匿名アクセスや承認されていないユーザーに資産を誤って公開しないように、その内容とアクセス許可を認識しておくことが重要です。

_CDN ポリシー_ を定義して、配信元のコンテンツを CDN から除外できます。 CDN ポリシーは、 _ファイルの種類_ や _サイト分類_ などの属性によってパブリックまたはプライベート配信元の資産を除外し、ポリシーで指定した CdnType (プライベートまたはパブリック) のすべての配信元に適用されます。 たとえば、複数のサブサイトを含むサイトで構成されるプライベート配信元を追加する場合、 **機密** としてマークされたサイトを除外するポリシーを定義して、その分類が適用されたサイトからコンテンツが CDN から提供されないようにすることができます。 このポリシーは、CDN に追加 _したすべての_ プライベート配信元のコンテンツに適用されます。

配信元の数が多いほど、CDN サービスが要求を処理するのにかかる時間への影響が大きくなることに注意してください。 配信元の数を可能な限り制限することをお勧めします。

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>各配信元をパブリックまたはプライベートにするかどうかを選択する

配信元を特定するときに、配信元を _パブリック_ にするか _プライベート_ にするかを指定します。 パブリック配信元の CDN 資産へのアクセスは匿名であり、プライベート配信元の CDN コンテンツは、セキュリティを強化するために動的に生成されたトークンによって保護されます。 選択したオプションに関係なく、CDN 自体の管理に関しては、Microsoft がすべての重い作業を行います。 また、CDN を設定して配信元を特定した後で、後で考えを変えることもできます。

パブリックとプライベートの両方のオプションで、同様のパフォーマンスの向上を得られますが、それぞれに固有の属性と利点があります。

Office 365 CDN 内の **パブリック** 配信元には匿名でアクセスでき、ホストされている資産には資産の URL を持つすべてのユーザーがアクセスできます。 公開されている元の場所のコンテンツへのアクセスは匿名になるため、アクセスしたコンテンツは、機密データ以外の一般的なコンテンツ (JavaScript ファイル、スクリプト、アイコン、画像など) をキャッシュする場合にのみ使用するようにしてください。

Office 365 CDN 内の **非公開** の元の場所は、SharePoint Online ドキュメント ライブラリ、サイト、独自のイメージなど、ユーザー コンテンツへのプライベート アクセスを行う場合に使用します。 プライベート配信元のコンテンツへのアクセスは、動的に生成されたトークンによってセキュリティで保護されるため、元のドキュメント ライブラリまたは保存場所に対するアクセス許可を持つユーザーのみがアクセスできます。 Office 365 CDN のプライベート配信元は SharePoint Online コンテンツにのみ使用でき、SharePoint Online テナントからのリダイレクトを使用してプライベート配信元のアセットにのみアクセスできます。

プライベート配信元のアセットへの CDN アクセスのしくみの詳細については、「プライベート配信元の [アセットを使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)する」を参照してください。

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

+ プライベート配信元の資産は、SharePoint Online テナントから参照する必要があります。 プライベート CDN 資産への直接アクセスは機能しません。

+ プライベート配信元から資産を削除した場合、その資産はキャッシュから最大 1 時間引き続き使用できます。ただし、CDN 内の資産へのリンクは、資産の削除から 15 分以内に無効になります。

+ プライベートの配信元用に含まれている既定のファイルの種類は、.gif、.ico、.jpeg、.jpg、.js、.png です。 追加のファイルの種類を指定できます。

+ パブリック配信元と同様に、ワイルドカードを使用してフォルダーまたはドキュメント ライブラリ内のすべての資産を含める場合でも、指定したサイト分類によって識別された資産を除外するポリシーを構成できます。

Office 365 CDN、一般的な CDN の概念、およびOffice 365 テナントで使用できるその他の Microsoft CDN を使用する理由の詳細については、「[コンテンツ配信ネットワーク](content-delivery-networks.md)」を参照してください。

### <a name="default-cdn-origins"></a>既定の CDN 配信元

特に指定しない限り、Office 365 CDN を有効にすると、既定の配信元が設定Office 365。 最初にプロビジョニングしないことを選択した場合は、セットアップの完了後にこれらの配信元を追加できます。 既定の配信元の設定をスキップした場合の結果を理解し、特定の理由がある場合を除き、CDN を有効にするときに作成できるようにする必要があります。

既定のプライベート CDN 配信元:

+ \*/userphoto.aspx
+ \*/siteassets

既定のパブリック CDN 配信元:

+ \*/masterpage
+ \*/style ライブラリ
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ は、2017 年 12 月に Office 365 CDN サービスに追加された既定のパブリック配信元です。 CDN のSharePoint Framework ソリューションを機能させるには、この配信元が存在する必要があります。 2017 年 12 月より前に Office 365 CDN を有効にした場合、または CDN を有効にしたときに既定の配信元の設定をスキップした場合は、この配信元を手動で追加できます。 詳細については、「[クライアント側の Web パーツまたは SharePoint Framework ソリューションが機能していない」](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)を参照してください。

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>SharePoint Online Management Shell を使用してOffice 365 CDN を設定して構成する

このセクションの手順では、SharePoint Online 管理シェルを使用して SharePoint Online に接続する必要があります。 手順については、「[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)」を参照してください。

SharePoint Online 管理シェルを使用して SharePoint Online で資産をホストするように CDN を設定および構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>組織で Office 365 CDN を使用できるようにする

テナント CDN 設定を変更する前に、Office 365 テナントのプライベート CDN 構成の現在の状態を取得する必要があります。 SharePoint Online 管理シェルを使用してテナントに接続します。

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

次に **、Get-SPOTenantCdnEnabled** コマンドレットを使用して、テナントから CDN 状態設定を取得します。

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

指定した CdnType の CDN の状態が画面に出力されます。

**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織で Office 365 CDN を使用できるようにします。 組織でパブリックオリジン、プライベートオリジン、またはその両方を一度に使用できるようにします。 また、CDN を有効にすると、既定の配信元の設定をスキップするように構成することもできます。 このトピックで説明するように、これらの配信元は後でいつでも追加できます。

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

[Office 365 CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) を有効にしたときに既定でプロビジョニングされる配信元と、既定の配信元の設定をスキップした場合の潜在的な影響については、「既定の CDN 配信元」を参照してください。

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
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Office 365 CDN に含めるファイルの種類の一覧を変更する (省略可能)

> [!TIP]
> **Set-SPOTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義する場合は、現在定義されているリストを上書きします。 リストにファイルの種類を追加する場合は、最初にコマンドレットを使用して、既に許可されているファイルの種類を調べ、新しいファイルの種類と共に一覧に含めます。

**Set-SPOTenantCdnPolicy** コマンドレットを使用して、CDN のパブリック配信元とプライベート配信元でホストできる静的ファイルの種類を定義します。 既定では、.css、.gif、.jpg、.jsなどの一般的な資産の種類が許可されます。

SharePoint Online のWindows PowerShell:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

たとえば、CDN で .css ファイルと .png ファイルをホストできるようにするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

CDN によって現在許可されているファイルの種類を確認するには、 **Get-SPOTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

これらのコマンドレットの詳細については、 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) と [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/) に関するページを参照してください。

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Office 365 CDN から除外するサイト分類の一覧を変更する (省略可能)

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

_IncludeFileExtensions_ プロパティには、CDN から提供されるファイル拡張子の一覧が含まれています。

> [!NOTE]
> 既定のファイル拡張子は、パブリックとプライベートの間で異なります。

_ExcludeRestrictedSiteClassifications_ プロパティには、CDN から除外するサイト分類が含まれています。 たとえば、 **機密** としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツが CDN から提供されないようにすることができます。

_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性設定に基づいて CDN からコンテンツを除外します。 既定では、_NoScript_ 属性は _[モダン_ サイト **に対して有効]** に設定され、_クラシック_ サイトでは **[無効] に設定されます**。 これは、テナントの設定によって異なります。

これらのコマンドレットの詳細については、 [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) と [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/) に関するページを参照してください。

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>アセットの配信元を追加する

**Add-SPOTenantCdnOrigin** コマンドレットを使用して、配信元を定義します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

> [!IMPORTANT]
> ユーザー情報を含むリソースや、組織の機密と見なされるリソースをパブリック配信元に配置しないでください。

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_パス_ の値は、アセットを含むライブラリまたはフォルダーへの相対パスです。 相対パスに加え、ワイルドカードも使用できます。 配信元では、URL の前にワイルドカードが追加されます。 これにより、複数のサイトにまたがる配信元を作成できます。 たとえば、CDN 内のパブリック配信元として、すべてのサイトの masterpages フォルダーにすべてのアセットを含めるには、次のコマンドを入力します。

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
> プライベート配信元では、配信元から共有されるアセットに、CDN からアクセスする前にメジャー バージョンが発行されている必要があります。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>例: マスター ページと SharePoint Online のスタイル ライブラリのパブリック配信元を構成する

通常、これらの配信元は、Office 365 CDN を有効にすると既定で設定されます。 ただし、手動で有効にする場合は、次の手順に従います。

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
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>例: SharePoint Online のサイトアセット、サイト ページ、発行イメージのプライベート配信元を構成する

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

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 SharePoint Online テナントが CDN サービスに接続するときに予期される _構成保留中_ のメッセージが表示される場合があります。 これには最大 15 分かかる場合があります。

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Office 365 CDN を管理する

CDN を設定したら、このセクションで説明するように、コンテンツの更新時やニーズの変化に応じて構成を変更できます。

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Office 365 CDN からアセットを追加、更新、または削除する

セットアップ手順が完了したら、新しいアセットを追加し、必要に応じて既存のアセットを更新または削除できます。 配信元として識別したフォルダーまたは SharePoint ライブラリ内のアセットに変更を加えるだけです。 新しい資産を追加すると、CDN からすぐに使用できます。 ただし、資産を更新すると、新しいコピーが反映されて CDN で使用可能になるまでに最大で 15 分かかります。

配信元の場所を取得する必要がある場合は、 **Get-SPOTenantCdnOrigins** コマンドレットを使用できます。 このコマンドレットの使用方法については、「 [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)」を参照してください。

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Office 365 CDN から配信元を削除する

配信元として識別したフォルダーまたは SharePoint ライブラリへのアクセス権を削除できます。 これを行うには、 **Remove-SPOTenantCdnOrigin** コマンドレットを使用します。

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

このコマンドレットの使用方法については、「 [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)」を参照してください。

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Office 365 CDN で配信元を変更する

作成した配信元は変更できません。 代わりに、配信元を削除してから、新しい配信元を追加します。 詳細については、「[Office 365 CDN から配信元を削除するには](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)」と「[アセットの配信元を追加するには」を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Office 365 CDN を無効にする

**Set-SPOTenantCdnEnabled** コマンドレットを使用して、組織の CDN を無効にします。 CDN でパブリック配信元とプライベート配信元の両方を有効にしている場合は、次の例に示すようにコマンドレットを 2 回実行する必要があります。

CDN でのパブリック配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

CDN でプライベート配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

このコマンドレットの詳細については、「 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)」を参照してください。

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>PnP PowerShell を使用して Office 365 CDN を設定して構成する

このセクションの手順では、PnP PowerShell を使用して SharePoint Online に接続する必要があります。 手順については、「 [PnP PowerShell の概要](https://github.com/SharePoint/PnP-PowerShell#getting-started)」を参照してください。

PnP PowerShell を使用して SharePoint Online で資産をホストするように CDN を設定および構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>組織で Office 365 CDN を使用できるようにする

テナント CDN 設定を変更する前に、Office 365 テナントのプライベート CDN 構成の現在の状態を取得する必要があります。 PnP PowerShell を使用してテナントに接続します。

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

次に **、Get-PnPTenantCdnEnabled** コマンドレットを使用して、テナントから CDN 状態設定を取得します。

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

指定した CdnType の CDN の状態が画面に出力されます。

**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織で Office 365 CDN を使用できるようにします。 組織でパブリックオリジン、プライベート配信元、またはその両方を同時に使用できるようにします。 また、CDN を有効にすると、既定の配信元の設定をスキップするように構成することもできます。 このトピックで説明するように、これらの配信元は後でいつでも追加できます。

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

[Office 365 CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) を有効にしたときに既定でプロビジョニングされる配信元と、既定の配信元の設定をスキップした場合の潜在的な影響については、「既定の CDN 配信元」を参照してください。

組織でパブリックオリジンを使用できるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

組織でプライベート配信元を使用できるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

このコマンドレットの詳細については、「 [Set-PnPTenantCdnEnabled](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnEnabled.html)」を参照してください。

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Office 365 CDN に含めるファイルの種類の一覧を変更する (省略可能)

> [!TIP]
> **Set-PnPTenantCdnPolicy** コマンドレットを使用してファイルの種類を定義する場合は、現在定義されているリストを上書きします。 リストにファイルの種類を追加する場合は、最初にコマンドレットを使用して、既に許可されているファイルの種類を調べ、新しいファイルの種類と共に一覧に含めます。

**Set-PnPTenantCdnPolicy** コマンドレットを使用して、CDN のパブリック配信元とプライベート配信元でホストできる静的ファイルの種類を定義します。 既定では、.css、.gif、.jpg、.jsなどの一般的な資産の種類が許可されます。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

たとえば、CDN で .css ファイルと .png ファイルをホストできるようにするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

CDN で現在許可されているファイルの種類を確認するには、 **Get-PnPTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

これらのコマンドレットの詳細については、 [Set-PnPTenantCdnPolicy](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnPolicy.html) と [Get-PnPTenantCdnPolicies](https://pnp.github.io/powershell/cmdlets/Get-PnPTenantCdnPolicies.html) に関するページを参照してください。

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Office 365 CDN から除外するサイト分類の一覧を変更する (省略可能)

> [!TIP]
> **Set-PnPTenantCdnPolicy** コマンドレットを使用してサイト分類を除外すると、現在定義されているリストが上書きされます。 追加のサイト分類を除外する場合は、最初にコマンドレットを使用して、既に除外されている分類を調べ、新しい分類と共に追加します。

**Set-PnPTenantCdnPolicy** コマンドレットを使用して、CDN 経由で使用できないようにするサイト分類を除外します。 既定で除外されるサイトの分類はありません。

PnP PowerShell の場合:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

現在制限されているサイト分類を確認するには、 **Get-PnPTenantCdnPolicies** コマンドレットを使用します。

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

返されるプロパティは _、IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 、 _ExcludeIfNoScriptDisabled です_。

_IncludeFileExtensions_ プロパティには、CDN から提供されるファイル拡張子の一覧が含まれています。

> [!NOTE]
> 既定のファイル拡張子は、パブリックとプライベートの間で異なります。

_ExcludeRestrictedSiteClassifications_ プロパティには、CDN から除外するサイト分類が含まれています。 たとえば、 **機密** としてマークされたサイトを除外して、その分類が適用されたサイトのコンテンツが CDN から提供されないようにすることができます。

_ExcludeIfNoScriptDisabled_ プロパティは、サイト レベルの _NoScript_ 属性設定に基づいて CDN からコンテンツを除外します。 既定では、_NoScript_ 属性は _[モダン_ サイト **に対して有効]** に設定され、_クラシック_ サイトでは **[無効] に設定されます**。 これは、テナントの設定によって異なります。

これらのコマンドレットの詳細については、 [Set-PnPTenantCdnPolicy](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnPolicy.html) と [Get-PnPTenantCdnPolicies](https://pnp.github.io/powershell/cmdlets/Get-PnPTenantCdnPolicies.html) に関するページを参照してください。

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>アセットの配信元を追加する

**Add-PnPTenantCdnOrigin** コマンドレットを使用して、配信元を定義します。 複数の配信元を定義できます。 配信元は、CDN でホストする資産が含まれる SharePoint ライブラリまたはフォルダーを指す URL です。

> [!IMPORTANT]
> ユーザー情報を含むリソースや、組織の機密と見なされるリソースをパブリック配信元に配置しないでください。

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

_パス_ の値は、アセットを含むライブラリまたはフォルダーへの相対パスです。 相対パスに加え、ワイルドカードも使用できます。 配信元では、URL の前にワイルドカードが追加されます。 これにより、複数のサイトにまたがる配信元を作成できます。 たとえば、CDN 内のパブリック配信元として、すべてのサイトの masterpages フォルダーにすべてのアセットを含めるには、次のコマンドを入力します。

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

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html)」を参照してください。

> [!NOTE]
> プライベート配信元では、配信元から共有されるアセットに、CDN からアクセスする前にメジャー バージョンが発行されている必要があります。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>例: マスター ページと SharePoint Online のスタイル ライブラリのパブリック配信元を構成する

通常、これらの配信元は、Office 365 CDN を有効にすると既定で設定されます。 ただし、手動で有効にする場合は、次の手順に従います。

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、スタイル ライブラリをパブリックオリジンとして定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ **Add-PnPTenantCdnOrigin** コマンドレットを使用して、マスター ページをパブリック配信元として定義します。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>例: SharePoint Online のサイトアセット、サイト ページ、発行イメージのプライベート配信元を構成する

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

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 これには最大 15 分かかる場合があります。

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>例: SharePoint Online のサイト コレクションのプライベート配信元を構成する

**Add-PnPTenantCdnOrigin** コマンドレットを使用して、サイト コレクションをプライベートオリジンとして定義します。 次に例を示します。

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

このコマンドとその構文の詳細については、「 [Add-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Add-PnPTenantCdnOrigin.html)」を参照してください。

コマンドを実行すると、システムはデータセンター全体で構成を同期します。 SharePoint Online テナントが CDN サービスに接続するときに予期される _構成保留中_ のメッセージが表示される場合があります。 これには最大 15 分かかる場合があります。

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Office 365 CDN を管理する

CDN を設定したら、このセクションで説明するように、コンテンツの更新時やニーズの変化に応じて構成を変更できます。

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Office 365 CDN からアセットを追加、更新、または削除する

セットアップ手順が完了したら、新しいアセットを追加し、必要に応じて既存のアセットを更新または削除できます。 配信元として識別したフォルダーまたは SharePoint ライブラリ内のアセットに変更を加えるだけです。 新しい資産を追加すると、CDN からすぐに使用できます。 ただし、資産を更新すると、新しいコピーが反映されて CDN で使用可能になるまでに最大で 15 分かかります。

配信元の場所を取得する必要がある場合は、 **Get-PnPTenantCdnOrigin コマンドレットを** 使用できます。 このコマンドレットの使用方法については、「 [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)」を参照してください。

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Office 365 CDN から配信元を削除する

配信元として識別したフォルダーまたは SharePoint ライブラリへのアクセス権を削除できます。 これを行うには、 **Remove-PnPTenantCdnOrigin** コマンドレットを使用します。

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

このコマンドレットの使用方法については、「 [Remove-PnPTenantCdnOrigin](https://pnp.github.io/powershell/cmdlets/Remove-PnPTenantCdnOrigin.html)」を参照してください。

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Office 365 CDN で配信元を変更する

作成した配信元は変更できません。 代わりに、配信元を削除してから、新しい配信元を追加します。 詳細については、「[Office 365 CDN から配信元を削除するには](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)」と「[アセットの配信元を追加するには」を参照してください](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Office 365 CDN を無効にする

**Set-PnPTenantCdnEnabled** コマンドレットを使用して、組織の CDN を無効にします。 CDN でパブリック配信元とプライベート配信元の両方を有効にしている場合は、次の例に示すようにコマンドレットを 2 回実行する必要があります。

CDN でのパブリック配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

CDN でプライベート配信元の使用を無効にするには、次のコマンドを入力します。

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

このコマンドレットの詳細については、「 [Set-PnPTenantCdnEnabled](https://pnp.github.io/powershell/cmdlets/Set-PnPTenantCdnEnabled.html)」を参照してください。

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-cli-for-microsoft-365"></a>Microsoft 365 用 CLI を使用して、Office 365 CDN を設定して構成する

このセクションの手順では、 [Microsoft 365 用の CLI](https://aka.ms/cli-m365) をインストールしている必要があります。 次に、[login](https://pnp.github.io/cli-microsoft365/cmd/login/) コマンドを使用して、Office 365 テナントに接続します。

Microsoft 365 用 CLI を使用して SharePoint Online で資産をホストするように CDN を設定および構成するには、次の手順を実行します。

<details>
  <summary>クリックして展開</summary>

### <a name="enable-the-office-365-cdn"></a>Office 365 CDN を有効にする

テナントの Office 365 CDN の状態は [spo cdn set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-set/) コマンドを使用して管理できます。

テナントで Office 365 パブリック CDN を有効にするには、次のように実行します。

```cli
spo cdn set --type Public --enabled true
```

Office 365 SharePoint CDN を有効にするには、次のコマンドを実行します。

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Office 365 CDN の現在の状況を確認する

特定の種類の Office 365 CDN が有効または無効になっているかどうかを確認するには、[spo cdn get](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-get/) コマンドを使用します。

Office 365 パブリック CDN が有効かどうかを確認するには、次のように実行します。

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Office 365 CDN 配信元を表示する

現在構成されている Office 365 パブリック CDN の配信元を確認するには、次のように実行します。

```cli
spo cdn origin list --type Public
```

[Office 365 CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) を有効にするときに既定でプロビジョニングされる配信元については、「既定の CDN 配信元」を参照してください。

### <a name="add-an-office-365-cdn-origin"></a>Office 365 CDN 配信元を追加する

> [!IMPORTANT]
> 組織に依存していると見なされるリソースは、パブリック配信元として構成された SharePoint ドキュメント ライブラリに配置しないでください。

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

### <a name="remove-an-office-365-cdn-origin"></a>Office 365 CDN 配信元を削除する

[spo cdn origin remove](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-remove/) コマンドを使用して、指定した種類の CDN の配信元を削除します。

CDN 構成からパブリック配信元を削除するには、次のコマンドを実行します。

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> CDN 配信元を削除しても、その配信元と一致するドキュメント ライブラリに格納されているファイルには影響しません。 これらのアセットが SharePoint URL を使用して参照されている場合、SharePoint はドキュメント ライブラリを指す元の URL に自動的に切り替わります。 ただし、パブリック CDN URL を使用してアセットが参照されている場合は、配信元を削除するとリンクが中断され、手動で変更する必要があります。

### <a name="modify-an-office-365-cdn-origin"></a>Office 365 CDN 配信元を変更する

既存の CDN の配信元を変更することはできません。 代わりに、`spo cdn origin remove` コマンドを使用して定義済みの CDN の配信元を削除して、`spo cdn origin add` コマンドで新しい配信元を作成する必要があります。

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Office 365 CDN に含めるファイルの種類を変更する

既定では、 _.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff、.woff2_ というファイルの種類が CDN に含まれています。 CDN に他の種類のファイルを含める必要がある場合、[spo cdn policy set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して CDN 構成を変更できます。

> [!NOTE]
> ファイルの種類のリストを変更する場合、現在定義されているリストを上書きします。 他のファイルの種類を追加する場合は、[spo cdn policy list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-origin-list/) コマンドを最初に使用して現在構成されているファイルの種類を確認します。

パブリック CDN に含まれるファイルの種類の既定の一覧に _JSON_ ファイルの種類を追加するには、次のコマンドを実行します。

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Office 365 CDN から除外するサイトの分類のリストを変更する

[spo cdn policy set](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-set/) コマンドを使用して、CDN で利用できるようにしないサイトの分類を除外します。 既定で除外されるサイトの分類はありません。

> [!NOTE]
> 除外するサイトの分類のリストを変更する場合、現在定義されているリストを上書きします。 他の分類を除外する場合は、[spo cdn policy list](https://pnp.github.io/cli-microsoft365/cmd/spo/cdn/cdn-policy-list/) コマンドを最初に使用して現在構成されている分類を確認します。

_HBI_ として分類されたサイトをパブリック CDN から除外するには、次のコマンドを実行します。

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Office 365 CDN を無効にする

Office 365 CDN を無効にするには、`spo cdn set` コマンドを使用します。たとえば、次のように実行します。

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>CDN 資産の使用

CDN を有効にし、配信元とポリシーを構成したので、CDN 資産の使用を開始できます。

このセクションでは、SharePoint のページとコンテンツで CDN URL を使用して、SharePoint がパブリックオリジンとプライベート配信元の両方のアセットの要求を CDN にリダイレクトする方法を理解するのに役立ちます。

+ [CDN アセットへのリンクの更新](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [パブリックオリジンでのアセットの使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [プライベート配信元でのアセットの使用](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

クライアント側 Web パーツをホストするために CDN を使用する方法については、「CDN [からクライアント側 Web パーツをホストする (パート 4)Hello World](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn) Office 365トピックを参照してください。

> [!NOTE]
> _ClientSideAssets_ フォルダーを **プライベート** CDN 配信元リストに追加すると、CDN でホストされるカスタム Web パーツのレンダリングに失敗します。 SPFX Web パーツで使用されるファイルはパブリック CDN のみを使用でき、ClientSideAssets フォルダーはパブリック CDN の既定の配信元です。

### <a name="updating-links-to-cdn-assets"></a>CDN アセットへのリンクの更新

配信元に追加したアセットを使用するには、元のファイルへのリンクを、配信元のファイルへのパスで更新するだけです。

+ 配信元に追加したアセットへのリンクを含むページまたはコンテンツを編集します。 また、複数の方法のいずれかを使用して、入力サイトまたはサイト コレクション全体のリンクをグローバルに検索して置き換えることができます。リンクを特定のアセットに表示されるすべての場所に更新する場合は、サイトまたはサイト コレクション全体でリンクを更新します。
+ 配信元のアセットへのリンクごとに、CDN 配信元のファイルへのパスにパスを置き換えます。 相対パスを使用できます。
+ ページまたはコンテンツを保存します。

たとえば、ドキュメント ライブラリ フォルダー _/site/CDN_origins/public/_ にコピーしたイメージ _/site/SiteAssets/images/image.png_ を考えてみましょう。 CDN 資産を使用するには、イメージ ファイルの場所への元のパスを配信元へのパスに置き換えて、新しい URL _/site/CDN_origins/public/image.png_ を作成します。

相対パスの代わりに資産への完全な URL を使用する場合は、次のようにリンクを作成します。

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> 一般に、CDN 内のアセットに URL を直接ハードコーディングしないでください。 ただし、必要に応じて、パブリック配信元のアセットの URL を手動で作成できます。 詳細については、 [パブリック資産の CDN URL のハードコーディングに関するページを](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)参照してください。

資産が CDN から提供されていることを確認する方法については、「Office 365 CDN の[トラブルシューティング](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)」の「CDN [によってアセットが提供されていることを確認](use-microsoft-365-cdn-with-spo.md#CDNConfirm)操作方法」を参照してください。

### <a name="using-assets-in-public-origins"></a>パブリックオリジンでのアセットの使用

SharePoint Online の **発行機能** は、パブリック配信元に格納されている資産の URL を CDN に自動的に書き換えて、SharePoint ではなく CDN サービスからアセットが提供されるようにします。

配信元が発行機能が有効になっているサイト内にあり、CDN にオフロードする資産が次のいずれかのカテゴリにある場合、資産が CDN ポリシーによって除外されていない場合、SharePoint は配信元のアセットの URL を自動的に書き換えます。

SharePoint 発行機能によって自動的に書き換えられるのは次のようなリンクです。

+ 従来の発行ページの HTML 応答の IMG/LINK/CSS URL
  + これには、ページの HTML コンテンツ内に作成者によって追加された画像が含まれます。
+ 画像ライブラリ スライドショー Web パーツの画像 URL
+ SPList REST API (RenderListDataAsStream) 結果の画像フィールド
  + 新しいプロパティ _ImageFieldsToTryRewriteToCdnUrls_ を使用して、フィールドのコンマ区切りリストを指定します
  + ハイパーリンク フィールドと PublishingImage フィールドをサポートしています
+ SharePoint イメージの表示

次の図は、SharePoint がパブリック配信元からアセットを含むページの要求を受信したときのワークフローを示しています。

![ワークフロー図: パブリック配信元から Office 365 CDN 資産を取得する。](../media/O365-CDN/o365-cdn-public-steps-transparent.png "ワークフロー: パブリック配信元から Office 365 CDN 資産を取得する")

> [!TIP]
> ページ上の特定の URL の自動書き換えを無効にする場合は、ページをチェックアウトしてクエリ文字列パラメーターを追加できます **。無効にする各リンクの末尾に NoAutoReWrites=true** 。

#### <a name="constructing-cdn-urls-for-public-assets"></a>パブリック資産の CDN URL を作成する

公開元に対して _発行_ 機能が有効になっていない場合、または資産が CDN サービスの自動書き換え機能でサポートされているリンクの種類の 1 つではない場合は、アセットの CDN の場所への URL を手動で作成し、コンテンツでこれらの URL を使用できます。

> [!NOTE]
> URL の最後のセクションを形成する必要なアクセス トークンは、リソースが要求された時点で生成されるため、プライベート配信元のアセットに CDN URL をハードコーディングまたは構築することはできません。 パブリック CDN の URL を作成できます。変更される可能性があるため、URL をハードコーディングしないでください。

パブリック CDN アセットの場合、URL 形式は次のようになります。

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

**TenantHostName を** テナント名に置き換えます。 例:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> ページ コンテキスト プロパティは、ハード コーディング ""https://publiccdn.sharepointonline.com ではなくプレフィックスを作成するために使用する必要があります。 URL は変更される可能性があるため、ハード コーディングしないでください。 クラシック SharePoint Online で表示テンプレートを使用している場合は、URL のプレフィックスとして表示テンプレートのプロパティ "window._spPageContextInfo.publicCdnBaseUrl" を使用できます。 モダンおよびクラシック SharePoint 用の SPFx Web パーツの場合は、プロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" を使用できます。 これにより、プレフィックスが変更された場合に実装が更新されるようにプレフィックスが提供されます。 SPFx の例として、URL はプロパティ "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" を使用して構築できます。 [シーズン 1 パフォーマンス シリーズ](https://aka.ms/sppnp-perfvideos)の一部である[クライアント側コードでの CDN の使用](https://youtu.be/IH1RbQlbhIA)に関するページを参照してください。


### <a name="using-assets-in-private-origins"></a>プライベート配信元でのアセットの使用

プライベート配信元でアセットを使用するために追加の構成は必要ありません。 SharePoint Online では、プライベート配信元のアセットの URL が自動的に書き換えられます。そのため、それらの資産に対する要求は常に CDN から提供されます。 プライベート配信元の CDN アセットに URL を手動で作成することはできません。これらの URL には、資産が要求された時点で SharePoint Online によって自動生成する必要があるトークンが含まれているためです。

プライベート配信元の資産へのアクセスは、配信元に対するユーザーのアクセス許可に基づいて動的に生成されたトークンによって保護されます。この点については、次のセクションで説明します。 CDN がコンテンツをレンダリングするには、少なくとも配信元への **読み取り** アクセス権がユーザーに付与されている必要があります。

次の図は、SharePoint がプライベート配信元からアセットを含むページの要求を受信したときのワークフローを示しています。

![ワークフロー図: プライベート配信元から Office 365 CDN 資産を取得する。](../media/O365-CDN/o365-cdn-private-steps-transparent.png "ワークフロー: プライベート配信元から Office 365 CDN 資産を取得する")

#### <a name="token-based-authorization-in-private-origins"></a>プライベート配信元でのトークン ベースの承認

Office 365 CDN 内のプライベート配信元の資産へのアクセスは、SharePoint Online によって生成されたトークンによって付与されます。 配信元によって指定されたフォルダーまたはライブラリへのアクセス許可を既に持っているユーザーには、ユーザーがアクセス許可レベルに基づいてファイルにアクセスできるようにするトークンが自動的に付与されます。 これらのアクセス トークンは、トークン再生攻撃を防ぐために生成されてから 30 分から 90 分間有効です。

アクセス トークンが生成されると、SharePoint Online は、2 つの承認パラメーター _が食べられ_ (エッジ承認トークン) と _oat_ (配信元承認トークン) を含むカスタム URI をクライアントに返します。 各トークンの構造は _<エポック時間形式の有効期限'>__<'secure signature'>_ です。 次に例を示します。

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> トークンを所有しているユーザーは、CDN 内のリソースにアクセスできます。 ただし、これらのアクセス トークンを含む URL は HTTPS 経由でのみ共有されるため、トークンの有効期限が切れる前にエンド ユーザーによって URL が明示的に共有されていない限り、資産は承認されていないユーザーからアクセスできなくなります。

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>アイテム レベルのアクセス許可は、プライベート配信元の資産ではサポートされていません

SharePoint Online では、プライベート配信元の資産に対するアイテム レベルのアクセス許可はサポートされないことに注意してください。 たとえば、次の条件を満たすファイルの `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg`場合、ユーザーはファイルに効果的にアクセスできます。

|User  |アクセス許可  |効果的なアクセス  |
|---------|---------|---------|
|ユーザー 1     |folder1 にアクセスできます         |CDN からimage1.jpgにアクセスできます         |
|ユーザー 2     |folder1 にアクセスできない         |CDN からimage1.jpgにアクセスできない         |
|ユーザー 3     |folder1 にはアクセスできませんが、SharePoint Online でimage1.jpgにアクセスするための明示的なアクセス許可が付与されます         |SharePoint Online から直接アセット image1.jpgにアクセスできますが、CDN からアクセスすることはできません         |
|ユーザー 4     |folder1 にアクセスできますが、SharePoint Online でimage1.jpgへのアクセスが明示的に拒否されました         |SharePoint Online から資産にアクセスすることはできませんが、SharePoint Online のファイルへのアクセスが拒否されているにもかかわらず、CDN から資産にアクセスできます         |

<a name="CDNTroubleshooting"></a>

## <a name="troubleshooting-the-office-365-cdn"></a>Office 365 CDN のトラブルシューティング

<a name="CDNConfirm"></a>

### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>CDN によってアセットが提供されていることを確認操作方法。

CDN アセットへのリンクをページに追加したら、ページを参照し、レンダリング後に画像を右クリックし、イメージ URL を確認することで、CDN からアセットが提供されていることを確認できます。

ブラウザーの開発者ツールを使用して、ページ上の各資産の URL を表示したり、サード パーティのネットワーク トレース ツールを使用したりすることもできます。

> [!NOTE]
> Fiddler などのネットワーク ツールを使用して、SharePoint ページからアセットをレンダリングする以外のアセットをテストする場合は、URL が SharePoint Online テナントのルート URL である GET 要求に、参照元ヘッダー "Referer: `https://yourdomain.sharepoint.com`" を手動で追加する必要があります。

SharePoint Online から提供される参照元が必要なため、Web ブラウザーで CDN URL を直接テストすることはできません。 ただし、SHAREPoint ページに CDN 資産 URL を追加し、ブラウザーでページを開くと、CDN 資産がページにレンダリングされます。

Microsoft Edge ブラウザーで開発者ツールを使用する方法の詳細については、「 [Microsoft Edge 開発者ツール](/microsoft-edge/devtools-guide)」を参照してください。

[SharePoint Developer Patterns and Practices YouTube チャネル](https://aka.ms/sppnp-videos)でホストされている短いビデオを視聴して、CDN が動作していることを確認する方法については、「[CDN の使用状況を確認し、最適なネットワーク接続を確保する](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)」を参照してください。

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>新しい配信元のアセットが利用できないのはなぜですか?
新しい配信元のアセットは、CDN を介して登録が伝達され、配信元から CDN ストレージにアップロードされるまでに時間がかかるため、すぐに使用することはできません。 CDN で資産を使用するために必要な時間は、資産の数とファイル サイズによって異なります。

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>クライアント側の Web パーツまたはSharePoint Framework ソリューションが機能しない

パブリック配信元に対して Office 365 CDN を有効にすると、CDN サービスによって次の既定の配信元が自動的に作成されます。

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

*/clientsideassets 配信元が見つからない場合、SharePoint Frameworkソリューションは失敗し、警告メッセージやエラー メッセージは生成されません。 この配信元は、 _-NoDefaultOrigins_ パラメーターが **$true** に設定された CDN が有効になっているか、または配信元が手動で削除されたために欠落している可能性があります。

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

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Office 365 CDN を操作するために必要な PowerShell モジュールと CLI シェルは何ですか?

**SharePoint Online Management Shell** PowerShell モジュールまたはOffice 365 CLI を使用して **、Office 365** CDN を使用することを選択できます。

+ [SharePoint Online 管理シェルの使用を開始する](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [Office 365 CLI のインストール](https://pnp.github.io/cli-microsoft365/user-guide/installing-cli/)

## <a name="see-also"></a>関連項目

[Content Delivery Network](./content-delivery-networks.md)

[Office 365 のネットワーク計画とパフォーマンス チューニング](./network-planning-and-performance.md)

[SharePoint パフォーマンス シリーズ - Office 365 CDN ビデオ シリーズ](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
