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
description: Exchange 2010 はサポートの終了に達しました。 この計画ロードマップを使用して、Exchange Online またはオンプレミスの新しいバージョンExchange Server準備します。
ms.openlocfilehash: f3531802283368e533ba6646415d4acc019687bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926996"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 のサポート終了のロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Exchange Server 2010 年 10 月 **13** 日にサポートが終了しました。 Exchange 2010 から Microsoft 365、Office 365、または Exchange 2016 への移行をまだ開始していない場合は、計画を開始します。

## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正など、サポート ライフサイクルがあります。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 Exchange 2010 は 2020 年 10 月 13 日にサポートの終了に達したため、Microsoft は次の機能を提供しなくなりました。

- 発生する可能性のある問題に対するテクニカル サポート。
- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。
- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。
- タイム ゾーンの更新。

Exchange 2010 のインストールは、この日付以降も実行されます。 ただし、上記の変更により、できるだけ早く Exchange 2010 から移行することを強く推奨します。

サポートの終了に近付く方法の詳細については [、「2010](upgrade-from-office-2010-servers-and-products.md)サーバーとクライアントからのアップグレードに役立つリソースOfficeを参照してください。

## <a name="what-are-my-options"></a>使用できるオプション

オプションを確認し、移行計画を準備する最適な時期です。 次の操作を実行できます。

- Microsoft 365 に完全に移行します。 カットオーバー、最小限のハイブリッド、または完全なハイブリッド移行を使用してメールボックスを移行します。 次に、オンプレミスの Exchange サーバーと Active Directory を削除します。
- オンプレミス サーバー上の Exchange 2010 サーバーを Exchange 2016 に移行します。

> [!IMPORTANT]
> 組織がメールボックスを Microsoft 365 に移行する場合でも、DirSync または Azure AD Connect を維持してオンプレミスの Active Directory からユーザー アカウントを管理し続ける場合は、少なくとも 1 つの Microsoft Exchange サーバーをオンプレミスに保持する必要があります。 すべての Exchange サーバーを削除した場合は、権限のソースがオンプレミスの Active Directory に残っているので、Exchange Online で Exchange 受信者を変更できません。 そこで変更を加える必要があります。 このシナリオでは、次のオプションがあります。
>
>- *推奨:* メールボックスを Microsoft 365 に移行し、2020 年 10 月 13 日までにサーバーをアップグレードした場合は、Exchange 2010 を使用して Microsoft 365 に接続し、メールボックスを移行します。 次に、Exchange 2010 を Exchange 2016 に移行し、残りの Exchange 2010 サーバーを使用停止します。
>- 2020 年 10 月 13 日までメールボックスの移行とオンプレミス サーバーのアップグレードを完了しなかった場合は、まずオンプレミスの Exchange 2010 サーバーを Exchange 2016 にアップグレードします。 その後、Exchange 2016 を使用して Microsoft 365 に接続し、メールボックスを移行します。

> [!NOTE]
> 少し複雑ですが、オンプレミスの Exchange 2010 サーバーを Exchange 2016 に移行しながら、メールボックスを Microsoft 365 に移行することもできます。

2010 年のサポート終了を回避するために使用できる 3 Exchange Serverします。

![Exchange Server 2010 アップグレード パス](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

以下のセクションでは、各オプションについて詳しく説明します。

## <a name="migrate-to-microsoft-365"></a>Microsoft 365 に移行する

メールを Microsoft 365 に移行する方法は、Exchange 2010 の展開を廃止するのに役立つ最も簡単なオプションです。 Microsoft 365 への移行では、次の機能を含む、古いテクノロジから現在の機能への単一ホップを作成できます。

- 保持ポリシー、In-Place訴訟ホールド、インプレイス電子情報開示などのコンプライアンス機能。
- Microsoft Teams。
- Power BI。
- フォーカスされた受信トレイ。
- MyAnalytics。

Microsoft 365 では、最初に新機能とエクスペリエンスを取得し、組織で使用を開始できます。 また、次のことを心配する必要はありません。

- ハードウェアの購入と保守。
- サーバーの熱と冷却に対する支払い。
- セキュリティ、製品、およびタイム ゾーンの修正を最新の状態に保つ。
- コンプライアンス要件をサポートするためのストレージとソフトウェアの維持。
- Exchange の新しいバージョンへのアップグレード。 Microsoft 365 では常に最新バージョンの Exchange を使用しています。

### <a name="how-should-i-migrate-to-microsoft-365"></a>Microsoft 365 に移行する方法

組織によっては、Microsoft 365 にアクセスするためのいくつかのオプションがあります。 まず、次のようないくつかの点を考慮する必要があります。
- 移動する必要があるシートまたはメールボックスの数。
- 移行を実行する期間。
- 移行中にオンプレミスインストールと Microsoft 365 のシームレスな統合が必要かどうか。
 
次の表に、移行オプションと、使用する方法を決定する最も重要な要素を示します。

|移行オプション|組織のサイズ|Duration|
|---|---|---|
|カットオーバー移行|シート数が 150 未満|1 週間以下|
|最小限のハイブリッド移行|シート数が 150 未満|数週間以下|
|完全なハイブリッド移行|150 席以上|数週間以上|

次のセクションでは、これらのメソッドの概要を説明します。 詳細については、「移行パスを [決定する」を参照してください](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。

### <a name="cutover-migration"></a>カットオーバー移行

カットオーバー移行では、すべてのメールボックス、配布グループ、連絡先など、設定された日時に Office 365 に移行します。 完了したら、オンプレミスの Exchange サーバーをシャットダウンし、Microsoft 365 の使用を排他的に開始します。

カットオーバー移行は、多くのメールボックスを持たなかったり、Microsoft 365 に迅速にアクセスしたい、他の方法の複雑さには対処したくない小規模な組織に最適です。 ただし、1 週間以下で完了する必要があります。 また、ユーザーは Outlook プロファイルを再構成する必要があります。 カットオーバー移行では最大 2,000 のメールボックスを移行できますが、最大 150 のメールボックスを使用することをお勧めします。 より多くの移行を試みた場合、期限前にすべてのメールボックスを転送する時間が切れる可能性があります。また、IT サポート スタッフは、ユーザーが Outlook を再構成するための要求に圧倒される可能性があります。

カットオーバー移行について考慮すべき点を次に示します。

- Microsoft 365 は、Outlook Anywhere over TCP ポート 443 を使用して Exchange 2010 サーバーに接続する必要があります。
- すべてのオンプレミス メールボックスは Microsoft 365 に移動されます。
- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
- Microsoft 365 で使用する Exchange 2010 が受け入れるドメインは、サービスに検証済みドメインとして追加する必要があります。
- 移行を開始して完了フェーズを開始する間、Microsoft 365 は Microsoft 365 メールボックスとオンプレミス メールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスにメールが残る心配なしに移行を完了できます。
- ユーザーは、Microsoft 365 アカウントの新しい一時的なパスワードを受け取る。 メールボックスに初めてサインインするときに変更する必要があります。
- 移行するユーザー メールボックスごとに Exchange Online を含む Microsoft 365 ライセンスが必要です。
- ユーザーは、各デバイスで新しい Outlook プロファイルを設定し、電子メールを再度ダウンロードする必要があります。 Outlook がダウンロードする電子メールの量は異なる場合があります。 詳細については、「Outlook でオフライン [で作業する」を参照してください](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)。

カットオーバー移行の詳細については、以下を参照してください。

- [メールの一切の移行について知る必要がある情報](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [メールから 365 への一Office実行する](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>最小限のハイブリッド移行

最小限のハイブリッド (高速) 移行では、数週間以内に数百のメールボックスを Microsoft 365 に移動します。 このメソッドは、共有空き時間情報のような高度なハイブリッド移行機能をサポートします。

最小限のハイブリッド移行は、メールボックスを Microsoft 365 に移行するためにより多くの時間を必要とする組織に最適ですが、数週間以内に移行を完了する予定です。 複雑さなしに、より高度なフルハイブリッド移行の利点の一部を得る必要があります。 一度に移行するメールボックスの数とメールボックスを制御できます。 Microsoft 365 メールボックスは、オンプレミス アカウントのユーザー名とパスワードで作成されます。 また、切り替えの移行とは異なり、ユーザーは Outlook プロファイルを再作成する必要があります。

最小限のハイブリッド移行について考慮すべき点を次に示します。

- オンプレミスの Active Directory サーバーと Microsoft 365 の間で 1 回のディレクトリ同期を行う必要があります。
- ユーザーは、自分のメールボックスの前と同じユーザー名とパスワードを使用して Microsoft 365 メールボックスにサインインできます。
- 移行するユーザー メールボックスごとに Exchange Online を含む Microsoft 365 ライセンスが必要です。
- ユーザーは、ほとんどのデバイスで新しい Outlook プロファイルを設定する必要はありません。一部の古い Android 携帯電話では新しいプロファイルが必要になる場合があります。 ユーザーは電子メールを再ダウンロードする必要はもう一度行う必要があります。

詳細については、「Use Minimal Hybrid to quickly migrate Exchange mailboxes to Office [365」を参照してください](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)。

### <a name="full-hybrid"></a>フル ハイブリッド

完全なハイブリッド移行では、数百、最大数万のメールボックスを持ち、一部またはすべてが Microsoft 365 に移動します。 通常、これらの移行は長期的な移行なので、ハイブリッド移行によって次の作業が可能になります。

- Microsoft 365 のユーザーの空き時間情報をオンプレミス のユーザーに表示し、その逆も表示します。
- オンプレミスと Microsoft 365 の両方の受信者を含む統合グローバル アドレス一覧を参照してください。
- オンプレミスか Microsoft 365 かにかかわらず、すべてのユーザーの Outlook 受信者の完全なプロパティを表示します。
- TLS と証明書を使用して、オンプレミスの Exchange サーバーと 365 Office間の電子メール通信をセキュリティで保護します。
- オンプレミスの Exchange サーバーと Microsoft 365 の間で送信されるメッセージを内部として扱い、次の処理を可能にします。
  - 内部メッセージを対象とするトランスポートおよびコンプライアンス エージェントによって適切に評価され、処理されます。
  - スパム対策フィルターをバイパスします。

完全なハイブリッド移行は、何か月以上ハイブリッド構成にとどまる組織に最適です。 このセクションの前に示した機能と、ディレクトリ同期、より統合されたコンプライアンス機能、およびオンライン メールボックスの移動を使用して Microsoft 365 との間でメールボックスを移動する機能を取得します。 Microsoft 365 は、オンプレミス組織の拡張機能になります。

完全ハイブリッド移行について考慮する必要があります。

- これらの機能は、すべての組織に適しているのではない。 完全なハイブリッド移行の複雑さから、数百未満のメールボックスを持つ組織では、通常、必要な労力とコストを正当化する利点は見当たらない。 このような場合は、代わりにカットオーバーまたは最小限のハイブリッド移行を検討することをお勧めします。
- Azure Active Directory (Azure AD) を使用してディレクトリ同期をセットアップする必要があります。オンプレミスの Active Directory サーバーと Microsoft 365 の間で接続します。
- ユーザーは、ローカル ネットワークにサインインするときに使用するユーザー名とパスワードが同じ Microsoft 365 メールボックスにサインインできます。 (この機能には、Azure ADパスワード同期または Active Directory フェデレーション サービスとの接続が必要です)。
- 移行するユーザー メールボックスごとに Exchange Online を含む Microsoft 365 ライセンスが必要です。
- 一部の古い Android 携帯電話では新しいプロファイルが必要になる場合があります。ほとんどのデバイスでユーザーが新しい Outlook プロファイルを設定する必要が生じます。 ユーザーは電子メールを再ダウンロードする必要はもう一度行う必要があります。

> [!IMPORTANT]
> 組織がメールボックスを Microsoft 365 に移行する場合でも、DirSync または Azure AD Connect を維持してオンプレミスの Active Directory からユーザー アカウントを管理し続ける場合は、少なくとも 1 つの Exchange サーバーをオンプレミスに保持する必要があります。 すべての Exchange サーバーが削除されると、Exchange Online で Exchange 受信者を変更することはできません。 これは、権限のソースがオンプレミスの Active Directory に残り、そこに変更を加える必要があるためです。

完全なハイブリッド移行が適切に聞こえる場合は、次の役立つリソースを参照してください。

- [Exchange 展開アシスタント](/exchange/exchange-deployment-assistant)
- [Exchange Server のハイブリッド展開](/exchange/exchange-hybrid)
- [ハイブリッド構成ウィザード](/exchange/hybrid-configuration-wizard)
- [ハイブリッド構成ウィザードに関する FAQ](/exchange/hybrid-configuration-wizard-faqs)
- [ハイブリッド展開の前提条件](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>オンプレミスの新しいバージョンExchange Serverアップグレードする

Microsoft 365 に完全に移行することで、最高の価値とユーザー エクスペリエンスを得たと強く信じています。 ただし、一部の組織では一部の Exchange サーバーをオンプレミスに維持する必要がある場合があります。 これは、規制上の要件が理由で、データが外部データセンターに保存されていないか、クラウドで満たできない固有の設定や要件がある、またはオンプレミスで Active Directory を使用するために Exchange がクラウド メールボックスを管理する必要がある場合などです。 いずれにしても、Exchange をオンプレミスに維持する場合は、Exchange 2010 環境が少なくとも Exchange 2013 または Exchange 2016 にアップグレードされている必要があります。

最適なエクスペリエンスを得る場合は、残りのオンプレミス環境を Exchange 2016 にアップグレードすることをお勧めします。 2010 年から 2016 年Exchange Server 2010 年から 2016 年まで直進する場合は、Exchange Server 2013 Exchange Serverする必要があります。

Exchange 2016 には、Exchange の以前のリリースのすべての機能が含まれています。 Microsoft 365 で利用できるエクスペリエンスと最も密接に一致しますが、一部の機能は Microsoft 365 でのみ使用できます。 不足しているいくつかの情報を確認してください。

|Exchange リリース|機能|
|---|---|
|**Exchange 2013**|簡略化されたアーキテクチャでは、サーバーの役割の数を 3 に減らします (メールボックス、クライアント アクセス、エッジ トランスポート)|
||機密情報の漏洩防止に役立つデータ損失防止ポリシー (DLP)|
||改善されたOutlook Web Appエクスペリエンス|
|**Exchange 2016**|*Exchange 2013 および ..からの機能。*|
||メールボックスとエッジ トランスポートに対するサーバーの役割の簡素化|
||SharePoint との統合に合った DLP の強化|
||データベースの復元性の向上|
||オンライン ドキュメントの共同作業|

|考慮事項|詳細|
|---|---|
|サポート終了日|Exchange 2010 と同様に、Exchange の各バージョンには独自のサポート終了日があります。<br/><br/>Exchange 2013 - 2023 年 4 月<br/>Exchange 2016 - 2025 年 10 月<br/><br/>サポート終了日より早く、別の移行を実行する必要があります。 2023 年 4 月は、思ったよりずっと近いです。|
|Exchange 2013 または 2016 への移行パス|Exchange 2010 から新しいバージョンへの移行パスは、Exchange 2013 または Exchange 2016 を選択した場合と同じです。<br/><br/>既存の Exchange 2010 組織に Exchange 2013 または 2016 をインストールします。<br/>サービスや他のインフラストラクチャを Exchange 2013 または 2016 に移動します。<br/>メールボックスとパブリック フォルダーを Exchange 2013 または 2016 の残りの Exchange 2010 サーバーに移動します。|
|バージョンの共存|Exchange 2013 または Exchange 2016 に移行する場合は、いずれかのバージョンを既存の Exchange 2010 組織にインストールできます。 これにより、1 つ以上の Exchange 2013 または Exchange 2016 サーバーをインストールし、移行を実行できます。|
|サーバー ハードウェア|サーバーのハードウェア要件が Exchange 2010 から変更されました。 ハードウェアが互換性を持つかどうかを確認します。 各バージョンのハードウェア要件の詳細については、こちらを参照してください。<br/><br/>[Exchange 2016 のシステム要件](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016)<br/>[Exchange 2013 のシステム要件](/Exchange/exchange-2013-system-requirements-exchange-2013-help)<br/><br/>Exchange のパフォーマンスが大幅に向上し、新しいサーバーの処理能力とストレージ容量が増えたので、同じ数のメールボックスをサポートするために必要なサーバーの数が少ない可能性があります。|
|オペレーティング システムのバージョン|各バージョンでサポートされるオペレーティング システムの最小バージョンは次のとおりです。<br/><br/>Exchange 2016 - Windows Server 2012<br/>Exchange 2013 - Windows Server 2008 R2 SP1<br/><br/>オペレーティング システムのサポートの詳細については [、「Exchange サポート可能性マトリックス」を参照してください](/exchange/plan-and-deploy/supportability-matrix)。|
|Active Directory フォレストの機能レベル|各バージョンでサポートされる Active Directory フォレストの最小機能レベルは次のとおりです。<br/><br/>Exchange 2016 - Windows Server 2008 R2 SP1<br/>Exchange 2013 - Windows Server 2003<br/><br/>フォレストの機能レベルのサポートの詳細については [、「Exchange サポート可能性マトリックス」を参照してください](/exchange/plan-and-deploy/supportability-matrix)。|
|Officeのバージョン|各バージョンでサポートOfficeクライアント バージョンは次のとおりです。<br/><br/>Exchange 2016 - Office 2010 (最新の更新プログラム付き)<br/>Exchange 2013 - Office 2007 SP3<br/><br/>クライアント サポートの詳細については、「Exchange サポートOffice [マトリックス」を参照してください](/exchange/plan-and-deploy/supportability-matrix)。||| 


移行を支援するには、次のリソースを使用します。

- [Exchange 展開アシスタント](/exchange/exchange-deployment-assistant)
- Exchange [2016 、2013](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016)の Active Directory スキーマ [の変更](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)
- Exchange [2016 、2013](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016)のシステム [要件](/Exchange/exchange-2013-system-requirements-exchange-2013-help)
- Exchange [2016 、2013](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016)の [前提条件](/Exchange/exchange-2013-prerequisites-exchange-2013-help)

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>2010 クライアントとOffice Windows 7 のオプションの概要

Office 2010 サーバー/クライアント、および Windows 7のアップグレード、移行、およびクラウドへの移行オプションを視覚的にまとめた概要は、[サポート終了ポスター](../downloads/Office2010Windows7EndOfSupport.pdf) をご覧ください。

[![2010 年 2010 Officeサーバーと Windows 7 ポスターのサポートの終了](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

この 1 ページのポスターは、Office 2010 クライアントおよびサーバー製品、およびサポートの終了に達する Windows 7 に対応するために使用できるさまざまなパスを示しています。Microsoft 365 Enterprise での優先パスとオプション サポートが強調表示されています。

また、この [ポスター](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) をダウンロードして、レター、リーガル、またはタブロイド (11 x 17) 形式で印刷することもできます。

## <a name="what-if-i-need-help"></a>ヘルプが必要な場合は、

Microsoft 365 に移行する場合は、Microsoft FastTrack サービスを使用できる可能性があります。 FastTrack は、Microsoft 365 への移行を可能な限りシームレスに行うベスト プラクティス、ツール、およびリソースを提供します。 何より、サポート エンジニアが計画と設計から最後のメールボックスの移行までを説明します。 FastTrack の詳細については [、「Microsoft FastTrack」を参照してください](https://fasttrack.microsoft.com/)。

Microsoft 365 への移行中に問題が発生し、FastTrack を使用していない場合、または新しいバージョンの Exchange Server に移行する場合は、次のリソースを使用できます。

- [テクニカル コミュニティ](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [カスタマー サポート](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>関連記事

[Office 2010 サーバー/クライアントからのアップグレードに役立つリソース](upgrade-from-office-2010-servers-and-products.md)