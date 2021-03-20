---
title: コンテンツ配信ネットワーク
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: この情報を使用して、Office 365 がコンテンツ配信ネットワーク (CDN) を使用してパフォーマンスを向上させる方法について学習します。
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911098"
---
# <a name="content-delivery-networks-cdns"></a>コンテンツ配信ネットワーク (CDNs)

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

CDN は、エンド Office 365 を高速かつ信頼性の高い状態に保つのに役立ちます。 Office 365 のようなクラウド サービスでは、CDN を使用して、ダウンロードの高速化とエンド ユーザーの待ち時間の短縮を要求する静的アセットをブラウザーに近づけてキャッシュします。 このトピックの情報は、コンテンツ配信ネットワーク (CDN) と、コンテンツ 配信ネットワーク 365 でどのように使用Office役立ちます。

## <a name="what-exactly-is-a-cdn"></a>CDN とは正確に何ですか?

CDN は、高速バックボーン ネットワークによって接続されたデータセンター内のプロキシ サーバーとファイル サーバーで構成される地理的に分散されたネットワークです。 CDN は、Web サイトまたはサービス内の指定された一連のファイルとオブジェクトの待機時間と読み込み時間を短縮するために使用されます。 CDN には、任意の場所からの受信要求の最適なサービスを提供するために、何千ものエンドポイントが存在する場合があります。

一般的に、CDN は、Javascript ファイル、アイコン、イメージなどの Web サイトまたはサービスの汎用コンテンツのダウンロードを高速化するために使用され、SharePoint Online ドキュメント ライブラリ内のファイル、ストリーミング メディア ファイル、カスタム コードなどのユーザー コンテンツへのプライベート アクセスを提供することもできます。

CDN は、ほとんどのエンタープライズ クラウド サービスで使用されます。 Office 365 などのクラウド サービスでは、何百万人ものユーザーが独自のコンテンツ (電子メールなど) と汎用コンテンツ (アイコンなど) を一度にダウンロードしています。 アイコンなど、誰もが使用する画像を、ユーザーのコンピューターに可能な限り近くに置く方が効率的です。 すべてのクラウド サービスが、この一般的なコンテンツをすべての大都市地域に格納する CDN データセンターを構築したり、世界中のすべての主要なインターネット ハブに構築したりするとは、実用的ではないので、これらの CDN の一部は共有されます。

## <a name="how-do-cdns-make-services-work-faster"></a>CDN を使用すると、サービスの動作が速くなりますか?

サイト イメージやアイコンのような一般的なオブジェクトを何度も何度もダウンロードすると、ネットワーク帯域幅が消費され、電子メールやドキュメントなど、重要な個人コンテンツのダウンロードに使用できます。 Office 365 は、CDN を含むアーキテクチャを使用します。アイコン、スクリプト、その他の汎用コンテンツは、クライアント コンピューターに近いサーバーからダウンロードして、ダウンロードを高速化できます。 つまり、365 データセンターに安全に保存される個人コンテンツOffice速くなります。

CDN は、いくつかの方法でクラウド サービスのパフォーマンスを向上させるのに役立ちます。

- CDN は、ネットワークとファイルのダウンロードの負荷の一部をクラウド サービスから遠く離れ、静的資産の要求を処理する必要性を減らすことで、ユーザー コンテンツや他のサービスを提供するクラウド サービス リソースを解放します。
- CDN は、高性能ネットワークとファイル サーバーを実装し [、HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) などの更新されたネットワーク プロトコルを効率的な圧縮と要求多重化で活用することで、低遅延のファイル アクセスを提供するために構築されています。
- CDN ネットワークでは、多くのグローバルに分散されたエンドポイントを使用して、ユーザーがコンテンツを可能な限り近く利用できます。

## <a name="the-office-365-cdn"></a>The Office 365 CDN

組み込みの Office 365 コンテンツ配信ネットワーク (CDN) を使用すると、Office 365 管理者は、静的アセットを要求するブラウザーに近いブラウザーにキャッシュすることで、組織の SharePoint Online ページのパフォーマンスを向上させることができます。 このOffice 365 CDN は [、HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) プロトコルを使用して圧縮速度とダウンロード速度を向上させます。

> [!NOTE]
> このOffice 365 CDN は、Production **(ワールド** ワイド) クラウドのテナントでのみ使用できます。 米国政府、中国、ドイツのクラウドのテナントは、現在、365 CDN Officeサポートされていません。

Office 365 CDN は静的資産を複数の場所 _(元の場所)_ でホストできる複数の CDN で構成されているため、静的資産をグローバルな高速ネットワークから提供することができます。 Office 365 CDN でホストするコンテンツの種類に応じて、**公開**、**非公開**、またはその両方の元の場所を追加できます。

![Office 365 CDN の概念図](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN の概念図")

Office 365 CDN 内で **公開されている** 元の場所のコンテンツは匿名でのアクセスが可能で、ホストされた資産への URL があれば誰でもアクセスできます。 公開されている元の場所のコンテンツへのアクセスは匿名になるため、アクセスしたコンテンツは、機密データ以外の一般的なコンテンツ (JavaScript ファイル、スクリプト、アイコン、画像など) をキャッシュする場合にのみ使用するようにしてください。 Office 365 CDN は、Office 365 クライアント アプリケーションのような一般リソースを、公開されている元の場所からダウンロードする際に既定で使用します。

**Office** 365 CDN 内のプライベートオリジンは、SharePoint Online ドキュメント ライブラリ、サイト、および独自のイメージなどのユーザー コンテンツへのプライベート アクセスを提供します。 公開されている元のファイルのコンテンツへのアクセスは、動的に生成されたトークンで保護されているため、元のドキュメント ライブラリまたは保存場所へのアクセス許可を持つユーザーのみがアクセスできます。 Office 365 CDN で公開されている元の場所は SharePoint Online コンテンツに対してのみ使用することができ、SharePoint Online テナントからのリダイレクトによってのみ資産にアクセスすることができます。

Office 365 CDN サービスは、SharePoint Online サブスクリプションの一部として含まれます。

365 CDN を使用する方法Officeについては、「SharePoint Online で Office [365](use-microsoft-365-cdn-with-spo.md)コンテンツ配信ネットワークを使用する」を参照してください。

Office 365 CDN の使用に関する概念的な情報と HOWTO 情報を提供する一連の短いビデオを見る場合は [、SharePoint Developer Patterns and Practices YouTube](https://aka.ms/sppnp-videos)チャンネルを参照してください。

## <a name="other-microsoft-cdns"></a>その他の Microsoft CDN

Office 365 CDN の一部ではないが、Office 365 テナントでこれらの CDN を使用して、sharePoint 開発ライブラリ、カスタム コード、および Office 365 CDN のスコープ外にあるその他の目的にアクセスできます。

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>SharePoint Online は、2020 年第 3 四半期から、ビデオの再生と信頼性の向上をサポートするために Azure CDN でビデオのキャッシュを開始します。 人気のあるビデオは、ユーザーに最も近い CDN エンドポイントからストリーミングされます。 このデータは、Microsoft 365 コンプライアンスの境界内に残ります。 これは、すべてのテナントの無料サービスであり、構成に顧客の操作を必要とします。

**Azure CDN** を使用して、カスタム Web パーツ、ライブラリ、その他のリソース資産をホストするために独自の CDN インスタンスを展開できます。これにより、CDN ストレージにアクセス キーを適用し、CDN 構成を制御できます。 Azure CDN の使用は無料ではなく、Azure サブスクリプションが必要です。

Azure CDN インスタンスを構成する方法の詳細については、「クイック スタート: Azure ストレージ アカウントと Azure CDN を統合 [する」を参照してください](/azure/cdn/cdn-create-a-storage-account-with-cdn)。

Azure CDN を使用して SharePoint Web パーツをホストする方法の例については、「SharePoint クライアント側 Web パーツを Azure CDN に展開する」 [を参照してください](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)。

Azure CDN PowerShell モジュールの詳細については [、「PowerShell を使用して Azure CDN を管理する」を参照してください](/azure/cdn/cdn-manage-powershell)。

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft の **Ajax CDN** は、jQuery (とその他のすべてのライブラリ)、ASP.NET Ajax、ブートストラップ、Knockout.js など、多くの一般的な開発ライブラリを提供する読み取り専用 CDN です。
  
これらのスクリプトをプロジェクトに含めるには、公開されているライブラリへの参照を、プロジェクト自体に含める代わりに CDN アドレスへの参照に置き換えます。 たとえば、jQuery にリンクするには、次のコードを使用します。

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Microsoft Ajax CDN の使用方法の詳細については、「Microsoft Ajax [CDN」を参照してください](/aspnet/ajax/cdn/overview)。

## <a name="how-does-office-365-use-content-from-a-cdn"></a>365 Office CDN のコンテンツの使用方法

365 テナントに対して構成Officeに関係なく、基本的なデータ取得プロセスは同じです。

1. クライアント (ブラウザーまたはクライアント アプリケーションOffice) は、365 からデータOfficeします。

2. Office 365 は、データをクライアントに直接返すか、データが CDN によってホストされる一連のコンテンツの一部である場合は、クライアントを CDN URL にリダイレクトします。

    a. データが既にパブリック 配信元にキャッシュされている場合、クライアントはデータを最も近い CDN の場所からクライアントに直接ダウンロードします。

    b. データが既にプライベート配信元にキャッシュされている場合、CDN サービスは、配信元に対する Office 365 ユーザー アカウントのアクセス許可をチェックします。 アクセス許可がある場合、SharePoint Online は CDN 内のアセットへのパスと 2 つのアクセス トークンで構成されるカスタム URL を動的に生成し、カスタム URL をクライアントに返します。 その後、クライアントはカスタム URL を使用して、最も近い CDN の場所からクライアントに直接データをダウンロードします。

3. CDN でデータがキャッシュされていない場合、CDN ノードは Office 365 からデータを要求し、クライアントがデータをダウンロードした後、一期間データをキャッシュします。

CDN は、ユーザーのブラウザーに最も近いデータセンターを把握し、リダイレクトを使用して、要求されたデータをそこからダウンロードします。 CDN リダイレクトは迅速で、ユーザーのダウンロード時間を多く節約できます。

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>CDN が 365 で最適に動作Office必要がありますか?

ネットワーク上のクライアントと CDN エンドポイント間の待機時間を最小限に抑えることは、最適なパフォーマンスを確保するための重要な考慮事項です。 [「Office 365](managing-office-365-endpoints.md)エンドポイントの管理」で説明されているベスト プラクティスを使用して、ネットワーク構成によって、不要な遅延を回避するために中央プロキシを介して CDN トラフィックをルーティングするのではなく、クライアント ブラウザーが CDN に直接アクセスできます。

また [、365 ネットワークOffice原則を読んで、365](./microsoft-365-network-connectivity-principles.md) ネットワークパフォーマンスの最適化の背後にある概念Office理解できます。

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>365 で使用されるすべての CDn のOfficeはありますか?

Office 365 で使用されている CDN は常に変更される可能性があります。多くの場合、イベント 1 が使用できない場合に複数の CDN パートナーが構成されています。 365 で使用されるプライマリ Officeは次のとおりです。

|CDN  |Company  |用途  |リンク  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |パブリック オリジンの汎用アセット、プライベート オリジンの SharePoint ユーザー コンテンツ         |[SharePoint Online での Office 365 コンテンツ配信ネットワークの使用](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |カスタム コード、SharePoint Framework ソリューション         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (読み取り専用)     |Microsoft         |Ajax、jQuery、ASP.NET ブートストラップ、Knockout.jsなどの一般的なライブラリ。         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>CDN が提供するパフォーマンスの向上は何ですか?

Office 365 から直接ダウンロードされたデータと、テナントを基準にした場所、最も近い CDN エンドポイントに対する場所、CDN によって提供されるページ上のアセットの数、ネットワーク遅延と帯域幅の一時的な変化など、特定の CDN からダウンロードされたデータのパフォーマンスの特定の違いを測定するには、多くの要因が関係します。 ただし、単純な A/B テストは、特定のファイルのダウンロード時間の違いを示すのに役立ちます。

次のスクリーン ショットは、Office 365 のネイティブ ファイルの場所と Microsoft Ajax コンテンツ配信ネットワークでホストされているファイルとの間のダウンロード速度の違いを [示しています](/aspnet/ajax/cdn/overview)。 これらのスクリーン ショットは、11 の開発者 **ツールの** [ネットワーク] Internet Explorerから表示されます。 これらのスクリーン ショットは、一般的なライブラリ jQuery の待機時間を示しています。 この画面を表示するには、Internet Explorer **F12** キーを押して、[ネットワーク]タブを選択し、アイコンでWi-Fiします。
  
![F12 ネットワークのスクリーンショット](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
このスクリーン ショットは、SharePoint Online サイト自体のマスター ページ ギャラリーにアップロードされたライブラリを示しています。 ライブラリのアップロードにかかった時間は 1.51 秒です。
  
![読み込み時間 1.51 秒のスクリーン ショット](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
2 番目のスクリーン ショットは、Microsoft の CDN によって配信された同じファイルを示しています。 今回の待機時間は約 496 ミリ秒です。 これは大きな改善点であり、1 秒がオブジェクトをダウンロードする合計時間を削り取られたと示しています。
  
![読み込み時間 469 ミリ秒のスクリーンショット](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>データは安全ですか?

ビジネスを実行するデータを保護するために、弊社は大きな注意を必要とします。 Office 365 CDN に格納されたデータは、転送中と保存時の両方で暗号化され、Office 365 SharePoint CDN 内のデータへのアクセスは、Office 365 ユーザーのアクセス許可とトークン承認によって保護されます。 Office 365 SharePoint CDN のデータ要求は、Office 365 テナントから参照 (リダイレクト) する必要があります。または承認トークンは生成されません。

データが安全に維持される状態を維持するために、ユーザー コンテンツや他の機密データをパブリック CDN に保存し続けすることをお勧めします。 パブリック CDN 内のデータへのアクセスは匿名なので、パブリック CDN は、Web スクリプト ファイル、アイコン、画像、その他の機密性の高いアセットなどの汎用コンテンツをホストするためにのみ使用する必要があります。

> [!NOTE]
> サードパーティの CDN プロバイダーには、365 セキュリティ センターで概説されているコミットメントとは異なるプライバシーとコンプライアンスOfficeがあります。 CDN サービスを介してキャッシュされたデータは、Microsoft Data Processing Terms (DPT) に準拠していない可能性があります。また、Office 365 Trust Center コンプライアンスの境界外にある可能性があります。

365 CDN プロバイダーのプライバシーとデータ保護Office詳細については、以下を参照してください。  

- Microsoft Trust [Center](https://www.microsoft.com/trustcenter) Office 365 プライバシーとデータ保護の詳細
- Akamai のプライバシーとデータ保護の詳細については [、「Akamai Privacy Trust Center」を参照してください。](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Azure のプライバシーとデータ保護の詳細については [、「Azure Trust Center」を参照してください。](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>これらすべてのサードパーティ サービスでネットワークをセキュリティで保護するには、どうすれば良いですか?

パートナー サービスの広範なセットを活用することで、Office 365 は可用性要件を拡張して満たし、Office 365 を使用できます。 365 の 365 のOfficeには、両方の証明書失効リストが含まれます。例: crl.microsoft.com または sa.symcb.com CDN など。などの r3.res.outlook.com。 365 で生成Office CDN FQDN は、365 のカスタム FQDN Officeです。 Office 365 の要求で FQDN に送信される場合は、CDN プロバイダーが FQDN と、その場所の基になるコンテンツを制御します。
  
Microsoft または Office 365 データセンター宛ての要求を第三者宛ての要求から分離する場合は、「Office [365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)エンドポイントの管理」に関するガイダンスについて説明しました。

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>CDN を活用するすべての FQDN の一覧はありますか?

FQDN の一覧と、その CDN の活用方法は、時間の間に変化します。 CDN を活用 [するOffice最新の FQDN](./urls-and-ip-address-ranges.md) を取得するには、公開されている 365 URL と IP アドレス範囲のページを参照してください。

[また、Office 365 IP](microsoft-365-ip-web-service.md)アドレスと URL Web サービスを使用して、CSV または JSON 形式の現在の Office 365 URL と IP アドレス範囲を要求することもできます。

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>自分の CDN とキャッシュ コンテンツをローカル ネットワークで使用できますか?

お客様のニーズをサポートする新しい方法を継続的に探し続け、現在、キャッシュ プロキシ ソリューションや他のオンプレミス CDN ソリューションの使用を模索しています。

Office 365 CDN の一部ではありませんが、カスタム Web パーツ、ライブラリ、その他のリソース資産をホストするために **Azure CDN** を使用することもできます。これにより、CDN ストレージにアクセス キーを適用し、CDN 構成を制御できます。 Azure CDN の使用は無料ではなく、Azure サブスクリプションが必要です。 Azure CDN インスタンスを構成する方法の詳細については、「クイック スタート: Azure ストレージ アカウントと Azure CDN を統合 [する」を参照してください](/azure/cdn/cdn-create-a-storage-account-with-cdn)。

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Azure ExpressRoute を 365 Office使用しているのですが、その変更点は変わりますか?

[Azure ExpressRoute for Office 365](azure-expressroute.md) は、パブリック インターネットから分離Office 365 インフラストラクチャへの専用接続を提供します。 つまり、クライアントは ExpressRoute 以外の接続を使用して、ExpressRoute でサポートされるサービスの一覧に明示的に含まれていない CDN や他の Microsoft インフラストラクチャに接続する必要があります。 CDN 宛ての要求などの特定のトラフィックをルーティングする方法の詳細については、「Office [365](routing-with-expressroute.md)ネットワーク トラフィック管理」を参照してください。

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>SharePoint Server オンプレミスで CDN を使用できますか?

CDN の使用は SharePoint Online コンテキストでのみ意味を持ち、SharePoint Server では避ける必要があります。 これは、サーバーがオンプレミスまたは地理的に近い場所にある場合、地理的な場所に関する利点はすべて当てはかからないのでです。 さらに、ホストされているサーバーへのネットワーク接続がある場合、サイトはインターネットに接続せずに使用される可能性があります。したがって、CDN ファイルを取得することはできません。 それ以外の場合は、サイトに必要なライブラリとファイルに使用可能で安定した CDN がある場合は、CDN を使用する必要があります。
  
ここに戻る場合は、次のショート リンクをご利用ください: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>関連項目

[Office 365 ネットワーク接続の原則](./microsoft-365-network-connectivity-principles.md)

[Office 365 のネットワーク接続の評価](assessing-network-connectivity.md)

[Office 365 エンドポイントの管理](managing-office-365-endpoints.md)

[Office 365 の URL および IP アドレスの範囲](./urls-and-ip-address-ranges.md)

[SharePoint Online での Office 365 コンテンツ配信ネットワークの使用](use-microsoft-365-cdn-with-spo.md)

[Microsoft Trust Center](https://www.microsoft.com/trustcenter)

[Office 365 のパフォーマンスをチューニングする](tune-microsoft-365-performance.md)