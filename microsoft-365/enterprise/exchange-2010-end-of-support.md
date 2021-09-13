---
title: Exchange 2010 のサポート終了のロードマップ
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010 はサポートの終了に達しました。 この計画ロードマップを使用して、Exchange Onlineまたは新しいバージョンのExchange Server準備します。
ms.openlocfilehash: 14875c793380c509c578d86d2d835596fa57cc73
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218554"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 のサポート終了のロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Exchange Server 2010 年 10 月 **13** 日にサポートが終了しました。 Exchange 2010 から Microsoft 365、Office 365、または Exchange 2016 への移行をまだ開始していない場合は、計画を開始します。

## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正など、サポート ライフサイクルがあります。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 2010 Exchange 2010 は 2020 年 10 月 13 日にサポートの終了に達したため、Microsoft は次の情報を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。
- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。
- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。
- タイム ゾーンの更新。

2010 Exchangeのインストールは、この日付以降も実行されます。 ただし、上記の変更により、できるだけ早く Exchange 2010 から移行することを強く推奨します。

サポートの終了に近付く方法の詳細については[、「2010](upgrade-from-office-2010-servers-and-products.md)サーバーとクライアントからのアップグレードに役立つリソースOfficeを参照してください。

## <a name="what-are-my-options"></a>使用できるオプション

オプションを確認し、移行計画を準備する最適な時期です。 次の操作を実行できます。

- 完全に移行してMicrosoft 365。 カットオーバー、最小限のハイブリッド、または完全なハイブリッド移行を使用してメールボックスを移行します。 次に、オンプレミスのサーバー Exchange Active Directory を削除します。
- オンプレミス サーバー Exchange 2010 Exchange 2016 に移行します。

> [!IMPORTANT]
> 組織がメールボックスを Microsoft 365 に移行する場合でも、オンプレミスの Active Directory からユーザー アカウントの管理を続行するために DirSync または Azure AD Connect を維持する計画がある場合は、少なくとも 1 つの Microsoft Exchange サーバーをオンプレミスに保持する必要があります。 すべての Exchange サーバーを削除した場合、権限のソースがオンプレミスの Active Directory に残っているため、Exchange Online の Exchange 受信者に変更を加えできません。 そこで変更を加える必要があります。 このシナリオでは、次のオプションがあります。
>
>- *推奨:* メールボックスを Microsoft 365 に移行し、2020 年 10 月 13 日までサーバーをアップグレードした場合は、Exchange 2010 を使用して Microsoft 365 に接続し、メールボックスを移行します。 次に、2010 Exchange 2010 から Exchange 2016 に移行し、残りの 2010 サーバー Exchange使用を停止します。
>- 2020 年 10 月 13 日までメールボックスの移行とオンプレミス サーバーのアップグレードを完了しなかった場合は、オンプレミスの Exchange 2010 サーバーを最初に Exchange 2016 にアップグレードします。 次に、Exchange 2016 を使用して、メールボックスMicrosoft 365移行します。

> [!NOTE]
> 少し複雑ですが、2010 年のオンプレミス Exchange サーバーを 2016 年に移行しながら、メールボックスを Microsoft 365 に移行Exchangeすることもできます。

2010 年のサポート終了を回避するために使用できる 3 つのExchange Serverします。

![Exchange Server 2010 アップグレード パス。](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

以下のセクションでは、各オプションについて詳しく説明します。

## <a name="migrate-to-microsoft-365"></a>Microsoft 365 に移行する

メールを 2010 Microsoft 365に移行すると、2010 年の展開を終了するのに役立つ最も簡単なExchangeです。 アプリケーションへの移行Microsoft 365、次の機能を含む、古いテクノロジから現在の機能への単一ホップを作成できます。

- 保持ポリシー、In-Place訴訟ホールド、インプレイス電子情報開示などのコンプライアンス機能。
- Microsoft Teams。
- Power BI。
- フォーカスされた受信トレイ。
- MyAnalytics。

Microsoft 365機能とエクスペリエンスを最初に取得し、組織がそれらを使用し始め、すぐ使い始めできます。 また、次のことを心配する必要はありません。

- ハードウェアの購入と保守。
- サーバーの熱と冷却に対する支払い。
- セキュリティ、製品、およびタイム ゾーンの修正を最新の状態に保つ。
- コンプライアンス要件をサポートするためのストレージとソフトウェアの維持。
- 新しいバージョンのサーバーにアップグレードExchange。 ユーザーは常に最新バージョンのExchangeをMicrosoft 365。

### <a name="how-should-i-migrate-to-microsoft-365"></a>ユーザーに移行するMicrosoft 365?

組織によっては、組織にアクセスするためのオプションがいくつかMicrosoft 365。 まず、次のようないくつかの点を考慮する必要があります。

- 移動する必要があるシートまたはメールボックスの数。
- 移行を実行する期間。
- 移行中に、オンプレミスのインストールとサーバー間のシームレスな統合が必要Microsoft 365かどうか。

次の表に、移行オプションと、使用する方法を決定する最も重要な要素を示します。

<br>

****

|移行オプション|組織のサイズ|Duration|
|---|---|---|
|カットオーバー移行|シート数が 150 未満|1 週間以下|
|最小限のハイブリッド移行|シート数が 150 未満|数週間以下|
|完全なハイブリッド移行|150 席以上|数週間以上|
|

次のセクションでは、これらのメソッドの概要を説明します。 詳細については、「移行パスを [決定する」を参照してください](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。

### <a name="cutover-migration"></a>カットオーバー移行

カットオーバー移行では、すべてのメールボックス、配布グループ、連絡先など、設定された日時にOffice 365に移行します。 完了したら、オンプレミスのサーバーをシャットダウンし、Exchange専用Microsoft 365開始します。

カットオーバー移行は、多くのメールボックスを持たなかったり、Microsoft 365 にすばやくアクセスしたい、他の方法の複雑さには対処したくない小規模な組織に最適です。 ただし、1 週間以下で完了する必要があります。 また、ユーザーは自分のプロファイルを再構成Outlook必要です。 カットオーバー移行では最大 2,000 のメールボックスを移行できますが、最大 150 のメールボックスを使用することをお勧めします。 より多くの移行を試みた場合、期限前にすべてのメールボックスを転送する時間が切れる可能性があります。また、IT サポート スタッフは、ユーザーが Outlook を再構成するための要求に圧倒される可能性があります。

カットオーバー移行について考慮すべき点を次に示します。

- Microsoft 365 2010 サーバーに接続するには、TCP ポート 443 Exchange Anywhere を使用Outlook 2010 サーバーに接続する必要があります。
- すべてのオンプレミス のメールボックスは、すべてのメールボックスにMicrosoft 365。
- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
- Exchangeで使用する 2010 年に受け入Microsoft 365、サービスに検証済みドメインとして追加する必要があります。
- 移行を開始して完了フェーズを開始するMicrosoft 365、Microsoft 365メールボックスとオンプレミスメールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスにメールが残る心配なしに移行を完了できます。
- ユーザーは自分のアカウントの新しい一時的なパスワードMicrosoft 365されます。 メールボックスに初めてサインインするときに変更する必要があります。
- 移行する各ユーザー メールボックスMicrosoft 365をExchange Onlineライセンスが必要です。
- ユーザーは、各デバイスで新しいOutlookプロファイルを設定し、電子メールを再度ダウンロードする必要があります。 ダウンロードするメールのOutlook異なる場合があります。 詳細については、「Work [offline in Outlook」を参照してください](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)。

カットオーバー移行の詳細については、以下を参照してください。

- [メールの一切の移行について知る必要がある情報](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [メールからメールへの一切の移行を実行Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>最小限のハイブリッド移行

最小限のハイブリッド(高速)移行では、数百のメールボックスを数週間以内にMicrosoft 365に移動します。 このメソッドは、共有空き時間情報のような高度なハイブリッド移行機能をサポートします。

最小限のハイブリッド移行は、メールボックスを Microsoft 365 に移行するためにより多くの時間を必要とする組織に最適ですが、数週間以内に移行を完了する予定です。 複雑さなしに、より高度なフルハイブリッド移行の利点の一部を得る必要があります。 一度に移行するメールボックスの数とメールボックスを制御できます。 Microsoft 365メールボックスは、オンプレミス アカウントのユーザー名とパスワードで作成されます。 また、カットオーバー移行とは異なり、ユーザーはユーザープロファイルを再作成Outlook必要があります。

最小限のハイブリッド移行について考慮すべき点を次に示します。

- オンプレミスの Active Directory サーバーとサーバー間で 1 回のディレクトリ同期を行うMicrosoft 365。
- ユーザーは、自分のメールボックスの前とMicrosoft 365同じユーザー名とパスワードで自分のメールボックスにサインインできます。
- 移行する各ユーザー メールボックスMicrosoft 365のExchange Onlineライセンスが必要です。
- 一部の古い Android 携帯電話では新しいプロファイルが必要Outlook、ほとんどのデバイスで新しいプロファイルをセットアップする必要はありません。 ユーザーは電子メールを再ダウンロードする必要はもう一度行う必要があります。

詳細については、「Use [Minimal Hybrid」を参照して、](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)メールボックスをExchangeにすばやく移行Office 365。

### <a name="full-hybrid"></a>フル ハイブリッド

完全なハイブリッド移行では、数百、最大数万のメールボックスを持ち、一部またはすべてがメールボックスに移動Microsoft 365。 通常、これらの移行は長期的な移行なので、ハイブリッド移行によって次の作業が可能になります。

- オンプレミス のユーザーに、ユーザーの空き時間情報を表示し、その逆Microsoft 365を表示します。
- オンプレミスとユーザーの両方の受信者を含む統合グローバル アドレス一覧をMicrosoft 365。
- オンプレミスまたはOutlookに関係なく、すべてのユーザーの完全な受信者プロパティを表示Microsoft 365。
- TLS と証明書を使用して、オンプレミスExchangeサーバーとOffice 365メール通信をセキュリティで保護します。
- 社内サーバーとサーバー間で送信されるExchangeを内部Microsoft 365として扱い、次の処理を可能にします。
  - 内部メッセージを対象とするトランスポートおよびコンプライアンス エージェントによって適切に評価され、処理されます。
  - スパム対策フィルターをバイパスします。

完全なハイブリッド移行は、何か月以上ハイブリッド構成にとどまる組織に最適です。 このセクションの前に示した機能と、ディレクトリ同期、より統合されたコンプライアンス機能、およびオンライン メールボックスの移動を使用してメールボックスをMicrosoft 365する機能を取得します。 Microsoft 365オンプレミス組織の拡張機能になります。

完全ハイブリッド移行について考慮する必要があります。

- これらの機能は、すべての組織に適しているのではない。 完全なハイブリッド移行の複雑さから、数百未満のメールボックスを持つ組織では、通常、必要な労力とコストを正当化する利点は見当たらない。 このような場合は、代わりにカットオーバーまたは最小限のハイブリッド移行を検討することをお勧めします。
- オンプレミスの Active Directory サーバーとサーバー間Azure Active Directory (Azure AD) Connectを使用してディレクトリ同期を設定するMicrosoft 365。
- ユーザーは、ローカル ネットワークにサインインするときに使用Microsoft 365同じユーザー名とパスワードで自分のメールボックスにサインインできます。 (この機能では、パスワード同期AD Connect Active Directory フェデレーション サービスを使用して Azure サーバーを使用する必要があります)。
- 移行する各ユーザー Microsoft 365のExchange Onlineを含むライセンスが必要です。
- 一部の古い Android 携帯電話では新しいプロファイルが必要になる場合Outlook、ほとんどのデバイスで新しいプロファイルをセットアップする必要があります。 ユーザーは電子メールを再ダウンロードする必要はもう一度行う必要があります。

> [!IMPORTANT]
> 組織がメールボックスを Microsoft 365 に移行する場合でも、オンプレミスの Active Directory からユーザー アカウントの管理を続行するために DirSync または Azure AD Connect を維持する計画がある場合は、少なくとも 1 つの Exchange サーバーをオンプレミスに保持する必要があります。 すべてのサーバー Exchange削除された場合は、ユーザーの受信者にExchange変更Exchange Online。 これは、権限のソースがオンプレミスの Active Directory に残り、そこに変更を加える必要があるためです。

完全なハイブリッド移行が適切に聞こえる場合は、次の役立つリソースを参照してください。

- [Exchange展開アシスタント](/exchange/exchange-deployment-assistant)
- [Exchange Server のハイブリッド展開](/exchange/exchange-hybrid)
- [ハイブリッド構成ウィザード](/exchange/hybrid-configuration-wizard)
- [ハイブリッド構成ウィザードに関する FAQ](/exchange/hybrid-configuration-wizard-faqs)
- [ハイブリッド展開の前提条件](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>オンプレミスの新しいバージョンExchange Serverアップグレードする

完全に移行することで、最高の価値とユーザー エクスペリエンスを得Microsoft 365。 ただし、一部の組織では、一部のサーバーをオンプレミスExchangeする必要があります。 これは、規制上の要件が理由で、データが外部データセンターに保存されるのを保証するために、クラウドで満たできない固有の設定や要件を持っている場合や、オンプレミスで Active Directory を使用するためにクラウド メールボックスを管理するために Exchange が必要な場合などです。 いずれにしても、Exchange をオンプレミスに維持する場合は、Exchange 2010 環境が少なくとも Exchange 2013 または Exchange 2016 にアップグレードされている必要があります。

最適なエクスペリエンスを得る場合は、残りのオンプレミス環境を 2016 年Exchangeすることをお勧めします。 2010 年 2010 年から 2016 年Exchange Serverに直進する場合は、Exchange Server 2013 Exchange Serverする必要があります。

Exchange 2016 には、以前のリリースのすべての機能が含Exchange。 この機能は、Microsoft 365で使用できるエクスペリエンスと最も密接に一致しますが、一部の機能はMicrosoft 365。 不足しているいくつかの情報を確認してください。

<br>

****

|Exchangeリリース|機能|
|---|---|
|**Exchange 2013**|簡略化されたアーキテクチャでは、サーバーの役割の数を 3 に減らします (メールボックス、クライアント アクセス、エッジ トランスポート)|
||機密情報の漏洩防止に役立つデータ損失防止ポリシー (DLP)|
||改善されたOutlook Web Appエクスペリエンス|
|**Exchange 2016**|*2013 Exchange ..の機能。*|
||メールボックスとエッジ トランスポートに対するサーバーの役割の簡素化|
||DLP の強化と、データの統合SharePoint|
||データベースの復元性の向上|
||オンライン ドキュメントの共同作業|
|

<br>

****

|考慮事項|詳細情報|
|---|---|
|サポート終了日|2010 Exchangeと同様に、各バージョンExchangeサポート終了日が設定されています。 <p> Exchange 2013 - 2023 年 4 月 <p> Exchange 2016 - 2025 年 10 月 <p> サポート終了日より早く、別の移行を実行する必要があります。 2023 年 4 月は、思ったよりずっと近いです。|
|2013 Exchange 2016 への移行パス|2010 Exchange から新しいバージョンへの移行パスは、2013 年または 2016 年Exchange選択Exchangeです。 <p> 2013 Exchange 2016 を既存の 2010 組織Exchangeインストールします。 <p> サービスおよび他のインフラストラクチャを 2013 または 2016 Exchangeに移動します。 <p> メールボックスとパブリック フォルダーを 2013 または 2016 Exchange 2010 サーバーの残りの使用停止Exchange移動します。|
|バージョンの共存|Exchange 2013 または Exchange 2016 に移行する場合は、いずれかのバージョンを既存の 2010 組織Exchangeできます。 これにより、2013 または 2013 または 2016 Exchange 1 つ以上のサーバーをインストールExchange移行を実行できます。|
|サーバー ハードウェア|サーバーのハードウェア要件が 2010 年Exchangeされています。 ハードウェアが互換性を持つかどうかを確認します。 各バージョンのハードウェア要件の詳細については、こちらを参照してください。 <p> [Exchange 2016 のシステム要件](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) <p> [Exchange 2013 のシステム要件](/Exchange/exchange-2013-system-requirements-exchange-2013-help) <p> Exchange のパフォーマンスが大幅に向上し、新しいサーバーの処理能力とストレージ容量が増えたので、同じ数のメールボックスをサポートするために必要なサーバーが少なくなっている可能性があります。|
|オペレーティング システムのバージョン|各バージョンでサポートされるオペレーティング システムの最小バージョンは次のとおりです。 <p> Exchange 2016 - Windows Server 2012 <p> Exchange 2013 - Windows Server 2008 R2 SP1 <p> オペレーティング システムのサポートに関する詳細については、「サポートExchange[マトリックス」を参照してください](/exchange/plan-and-deploy/supportability-matrix)。|
|Active Directory フォレストの機能レベル|各バージョンでサポートされる Active Directory フォレストの最小機能レベルは次のとおりです。 <p> Exchange 2016 - Windows Server 2008 R2 SP1 <p> Exchange 2013 - Windows Server 2003 <p> フォレストの機能レベルのサポートに関する詳細については、「サポートExchange[マトリックス」を参照してください](/exchange/plan-and-deploy/supportability-matrix)。|
|Officeのバージョン|各バージョンでサポートOfficeの最小バージョンは次のとおりです。 <p> Exchange 2016 - Office 2010 (最新の更新プログラム付き) <p> Exchange 2013 - Office 2007 SP3 <p> クライアント サポートの詳細については、「サポートOfficeマトリックス」[をExchange参照してください](/exchange/plan-and-deploy/supportability-matrix)。|
|

移行を支援するには、次のリソースを使用します。

- [Exchange展開アシスタント](/exchange/exchange-deployment-assistant)
- [2016 、2013 年 2016](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016&preserve-view=true)Exchange Active Directory スキーマ[の変更](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- [2016 年 2016](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true)Exchange [2013](/Exchange/exchange-2013-system-requirements-exchange-2013-help)年のシステム要件
- [2016 年 2016](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016&preserve-view=true)Exchange [2013](/Exchange/exchange-2013-prerequisites-exchange-2013-help)年の前提条件

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>2010 クライアントとサーバー Office 7 のオプションWindows概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![2010 年のクライアントOfficeサーバーと 7 ポスターのWindows終了します。](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

この 1 ページのポスターは、Office 2010 クライアントおよびサーバー製品、および Windows 7 のサポート終了に対応するために使用できるさまざまなパスを示し、Microsoft 365 Enterprise での優先パスとオプションのサポートが強調表示されています。

また、この [ポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) をダウンロードして、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="what-if-i-need-help"></a>ヘルプが必要な場合は、

移行する場合は、microsoft Microsoft 365 サービスを使用する資格FastTrackがあります。 FastTrack、ベスト プラクティス、ツール、およびリソースを提供して、移行を可能な限りシームレスMicrosoft 365作成します。 何より、サポート エンジニアが計画と設計から最後のメールボックスの移行までを説明します。 詳細については、「Microsoft FastTrack」[を参照FastTrack。](https://fasttrack.microsoft.com/)

Microsoft 365 への移行中に問題が発生し、FastTrack を使用していない場合、または新しいバージョンの Exchange Server に移行する場合は、次のリソースを使用できます。

- [テクニカル コミュニティ](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [カスタマー サポート](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>関連記事

[Office 2010 サーバー/クライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)
