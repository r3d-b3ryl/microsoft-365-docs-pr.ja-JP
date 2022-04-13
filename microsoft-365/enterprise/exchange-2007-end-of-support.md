---
title: Exchange 2007 のサポート終了ロードマップ
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Exchange Server 2007 サポート終了後のオプションについて説明し、2016 年のMicrosoft 365、Office 365、またはExchangeへの移行の計画を開始します。
ms.openlocfilehash: 8aecc835fbdde21f6651946acd15c4c70788b3da
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824402"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Exchange Server 2007 は 2017 年 4 月にサポートを終了しました。 2007 年Exchangeから 2016 年のMicrosoft 365、Office 365、またはExchangeへの移行を開始していない場合は、計画を開始します。

## <a name="what-does-end-of-support-mean"></a>*サポート終了とは* どういう意味ですか?

Exchange Serverは、ほぼすべての Microsoft 製品と同様に、新機能、バグ修正、セキュリティ修正などを提供するサポート ライフサイクルを備えています。 このライフサイクルは通常、製品の初期リリースから 10 年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 2007 Exchangeが 2017 年 4 月 11 日にサポートの終了に達したため、Microsoft では次の機能は提供されなくなりました。

- 発生する可能性がある問題のテクニカル サポート。

- サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。

- サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。

- タイム ゾーンの更新。

Exchange 2007 のインストールは、サポート終了日以降も引き続き実行されます。 ただし、新しい更新プログラムやサポートがないため、できるだけ早く 2007 Exchangeから移行することを強くお勧めします。

サポート終了間近の 2007 サーバー Officeの詳細については、「[Office 2007 サーバーと製品からのアップグレードを計画](upgrade-from-office-2007-servers-and-products.md)する」を参照してください。

## <a name="what-are-my-options"></a>使用できるオプション

次の操作を行うことができます:

- カットオーバー、ステージング、またはハイブリッド移行を使用して、Microsoft 365に移行します。

- Exchange 2007 サーバーをオンプレミス サーバー上の新しいバージョンのExchangeに移行します。

以降のセクションでは、各オプションについて詳しく説明します。

### <a name="migrate-to-microsoft-365"></a>Microsoft 365 に移行する

Microsoft 365へのメールの移行は、Exchange 2007 の展開を廃止するのに役立つ最も簡単なオプションです。 Microsoft 365への移行では、10 年前のテクノロジから最新の機能に 1 ホップを作成できます。次のような機能があります。

- 保持ポリシー、In-Place、訴訟ホールド、インプレース電子情報開示などのコンプライアンス機能

- Microsoft 365 グループ

- 優先受信トレイ

- MyAnalytics

- メール、予定表、連絡先などへのプログラムによるアクセスのための REST API

Microsoft 365は、新機能とエクスペリエンスを最初に取得します。そのため、ユーザーは通常、すぐに使用を開始できます。 次のことを心配する必要はありません。

- ハードウェアの購入と保守。

- サーバーを加熱して冷却するために支払います。

- セキュリティ、製品、タイム ゾーンの修正に関する最新情報。

- コンプライアンス要件をサポートするためのストレージとソフトウェアの保守。

- 新しいバージョンのExchangeにアップグレードする。 Microsoft 365では、常に最新バージョンのExchangeを使用できます。

#### <a name="how-should-i-migrate-to-microsoft-365"></a>Microsoft 365に移行するにはどうすればよいですか?

移行オプションがいくつかあります。 次のようないくつかの点を考慮する必要があります。

- 移動する必要があるシートまたはメールボックスの数。
- 移行を継続する期間。
- 移行中にオンプレミスのインストールとMicrosoft 365間のシームレスな統合が必要かどうか。

次の表に、移行オプションと、使用する方法を決定する最も重要な要因を示します。

|移行オプション|組織のサイズ|期間|
|---|---|---|
|カットオーバー移行|150 席未満|1 週間以下|
|段階的な移行|150 席を超える|数週間|
|完全なハイブリッド移行|数百から数千の席|数か月以上|

次のセクションでは、これらのメソッドの概要について説明します。 詳細については、「 [移行パスの決定](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)」を参照してください。

#### <a name="cutover-migration"></a>カットオーバー移行

一括移行では、すべてのメールボックス、配布グループ、連絡先などを事前に選択された日時にMicrosoft 365に移行します。 移行が完了したら、オンプレミスのExchange サーバーをシャットダウンし、Microsoft 365を排他的に使用します。

一括移行は、メールボックスの数が少ない小規模な組織や、Microsoft 365を迅速に行い、他の方法の複雑さに対処したくない小規模な組織に適しています。 ただし、1 週間以内に完了する必要があり、ユーザーはOutlook プロファイルを再構成する必要があります。 一括移行では最大 2,000 個のメールボックスを処理できますが、それを使用して最大 150 個のメールボックスを移行することを強くお勧めします。 より多くの移行を試みると、期限までにすべてのメールボックスを転送する時間が不足する可能性があります。また、IT サポート スタッフは、ユーザーがOutlookを再構成するのに役立つ要求に圧倒される可能性があります。

一括移行を行うことを検討している場合は、次の点を考慮してください。

- Microsoft 365は、OUTLOOK Anywhere over TCP ポート 443 を使用して、Exchange 2007 サーバーに接続する必要があります。

- オンプレミスのすべてのメールボックスは、Microsoft 365に移動されます。

- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。

- Microsoft 365で使用するExchange 2007 承認済みドメインは、サービス内の検証済みドメインとして追加する必要があります。

- 移行を開始してから完了フェーズを開始するまで、Microsoft 365はMicrosoft 365とオンプレミスのメールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスに電子メールが残される心配なく移行を完了できます。

- ユーザーは、Microsoft 365 アカウントの新しい一時パスワードを受け取ります。 メールボックスに初めてサインインするときに、パスワードを変更する必要があります。

- 移行する各ユーザー メールボックスのExchange Onlineを含むMicrosoft 365 ライセンスが必要です。

- ユーザーは、各デバイスに新しいOutlook プロファイルを設定し、もう一度電子メールをダウンロードする必要があります。 Outlookがダウンロードする電子メールの量は異なる場合があります。 詳細については、「 [オフラインにするメールの量を変更する」を](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)参照してください。

一括移行の詳細については、次を参照してください。

- [一括メール移行について知っておくべきこと](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)

- [メールの一括移行を実行する](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)

#### <a name="staged-migration"></a>段階的な移行

段階的移行では、Microsoft 365に移行する数百または数千のメールボックスがあり、移行を完了するには 1 週間以上かかる必要があり、共有の空き時間予定表情報などの高度なハイブリッド移行機能は必要ありません。

段階的移行は、メールボックスをMicrosoft 365に移行するのに時間がかかる必要があるが、数週間以内に移行を完了する予定の組織にとって最適です。 メールボックスはバッチで移行できます。 特定の時点で移行されるメールボックスの数とメールボックスの数を制御します。 たとえば、同じ部署のユーザーのメールボックスをバッチ処理して、それらがすべて同時に移動されるようにすることができます。 または、最後のバッチまでエグゼクティブ メールボックスを残すことがあります。 一括移行と同様に、ユーザーはOutlookプロファイルを再作成する必要があります。

段階的な移行を行うことを検討している場合は、次のことを考慮してください。

- Microsoft 365は、OUTLOOK Anywhere over TCP ポート 443 を使用して、Exchange 2007 サーバーに接続する必要があります。

- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。

- Microsoft 365で使用する予定のExchange 2007 承認済みドメインを、サービス内の検証済みドメインとして追加する必要があります。

- バッチで移行する予定の各メールボックスの完全な名前と電子メール アドレスを含む CSV ファイルを作成する必要があります。 また、移行するメールボックスごとに新しいパスワードを含め、そのパスワードを各ユーザーに送信する必要もあります。 ユーザーは、新しいMicrosoft 365 メールボックスに初めてサインインする際にパスワードを変更するように求められます。

- 移行バッチを開始してから完了フェーズを開始するまで、Microsoft 365はバッチに含まれるMicrosoft 365とオンプレミスのメールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスに電子メールが残される心配なく移行を完了できます。

- 移行する各ユーザー メールボックスのExchange Onlineを含むMicrosoft 365 ライセンスが必要です。

- ユーザーは、各デバイスに新しいOutlook プロファイルを設定し、もう一度電子メールをダウンロードする必要があります。 Outlookがダウンロードする電子メールの量は異なる場合があります。 詳細については、「 [オフラインにするメールの量を変更する」を](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)参照してください。

段階的移行の詳細については、次を参照してください。

- [段階的な電子メール移行について知っておくべきこと](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)

- [電子メールの段階的移行を実行する](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)

#### <a name="full-hybrid"></a>フル ハイブリッド

完全ハイブリッド移行では、組織には数百、最大数万個のメールボックスがあり、それらの一部または全部をMicrosoft 365に移動する必要があります。 これらの移行は通常、より長期的であるため、ハイブリッド移行では次の処理を行うことができます。

- オンプレミスユーザーに、Microsoft 365のユーザーの空き時間情報の予定表情報を表示します。また、その逆も同様です。

- オンプレミスとMicrosoft 365の両方の受信者を含む統合グローバル アドレス一覧を参照してください。

- オンプレミスかMicrosoft 365かに関係なく、すべてのユーザーの完全なOutlook受信者プロパティを表示します。

- TLS と証明書を使用して、オンプレミスのExchange サーバーとMicrosoft 365間の電子メール通信をセキュリティで保護します。

- オンプレミスのExchange サーバーとMicrosoft 365間で送信されたメッセージを内部として扱い、次の処理を行うことができます。

  - 内部メッセージをターゲットとするトランスポート エージェントとコンプライアンス エージェントによって適切に評価され、処理されます。

  - スパム対策フィルターをバイパスします。

完全なハイブリッド移行は、何か月以上ハイブリッド構成を維持する予定の組織に最適です。 このセクションの前に示した機能に加えて、ディレクトリ同期、統合コンプライアンス機能の強化、オンライン メールボックスの移動を使用してメールボックスをMicrosoft 365との間で移動する機能を提供します。 Microsoft 365は、オンプレミス組織の拡張機能になります。

完全なハイブリッド移行を行うことを検討している場合は、次の点を考慮してください。

- 完全なハイブリッド移行は、すべての種類の組織に適しているわけではありません。 完全なハイブリッド移行の複雑さのために、数百個未満のメールボックスを持つ組織では、通常、セットアップに必要な労力とコストを正当化する利点は見られません。 組織のように聞こえる場合は、代わりに一括移行または段階的移行を検討することをお勧めします。

- "ハイブリッド サーバー" として機能するには、Exchange 2007 組織に少なくとも 1 つの 2013 Exchange サーバーをデプロイする必要があります。 このサーバーは、Exchange 2007 サーバーに代わってMicrosoft 365と通信します。

- Microsoft 365は、OUTLOOK Anywhere over TCP ポート 443 を使用して "ハイブリッド サーバー" に接続する必要があります。

- オンプレミスの Active Directory サーバーとMicrosoft 365間のAzure Active Directory (Azure AD) Connectを使用してディレクトリ同期を設定する必要があります。

- ユーザーは、ローカル ネットワークにサインインするときと同じユーザー名とパスワードを使用して、自分のMicrosoft 365 メールボックスにサインインできます。 (この機能では、パスワード同期やActive Directory フェデレーション サービス (AD FS)を使用したAzure AD Connectが必要です)。

- 移行する各ユーザー メールボックスのExchange Onlineを含むMicrosoft 365 ライセンスが必要です。

- ユーザーは、ほとんどのデバイスで新しいOutlook プロファイルを設定する必要はありませんが、古い Android スマートフォンの中には新しいプロファイルが必要な場合があります。 ユーザーは自分のメールを再ダウンロードする必要はありません。

完全なハイブリッド移行が適切に行える場合は、移行に役立つ次のリソースを参照してください。

- [Exchange 展開アシスタント](/exchange/exchange-deployment-assistant)

- [Exchange Server のハイブリッド展開](/exchange/exchange-hybrid)

- [ハイブリッド構成ウィザード](/exchange/hybrid-configuration-wizard)

- [ハイブリッド構成ウィザードに関する FAQ](/exchange/hybrid-configuration-wizard-faqs)

- [ハイブリッド展開の前提条件](/exchange/hybrid-deployment-prerequisites)

### <a name="migrate-to-a-newer-version-of-exchange-server"></a>新しいバージョンのExchange Serverに移行する

Microsoft 365に移行することで、最高の価値とユーザー エクスペリエンスを実現できると強く考えています。 ただし、一部の組織では、オンプレミスで電子メールを保持する必要があることを理解しています。 これは、規制要件が原因で、データが別の国にあるデータセンターに格納されないことを保証するため、または類似している可能性があります。 電子メールをオンプレミスに保持する場合は、Exchange 2007 環境を 2010 年、Exchange 2013 年、または 2016 年Exchange Exchangeに移行できます。

Microsoft 365に移行できない場合は、Exchange 2016 に移行することをお勧めします。 Exchange 2016 には、以前のリリースのExchangeのすべての機能が含まれています。 また、Microsoft 365で使用できるエクスペリエンスと最もよく一致しますが、一部の機能はMicrosoft 365でのみ使用できます。 不足している点のほんの一部を確認してください。

|Exchange リリース|機能|
|---|---|
|Exchange 2010| Role-Based Access Control (ACL のないアクセス許可) <br/> Outlook Web App メールボックス ポリシー <br/> 空き時間情報を共有し、組織間で予定表を委任する機能|
|Exchange 2013| *Exchange 2010 および ... の機能。* <br/> サーバー ロールの数を 3 に減らした簡略化されたアーキテクチャ (メールボックス、クライアント アクセス、エッジ トランスポート) <br/> 機密情報の漏洩を防ぐデータ損失防止ポリシー (DLP) <br/> Outlook Web Appエクスペリエンスの向上|
|Exchange 2016| *Exchange 2013 および ... の機能。* <br/> メールボックスとエッジ トランスポートだけに対するサーバーの役割をさらに簡略化しました <br/> SharePointとの統合と共に DLP を改善しました <br/> データベースの回復性の向上 <br/> オンライン ドキュメントコラボレーション|

#### <a name="which-version-should-i-migrate-to"></a>どのバージョンに移行する必要がありますか?

最初は、Exchange 2016 に移行することを前提にすることをお勧めします。 次に、次の情報を使用して、想定を確認するか、2016 Exchange除外します。 何らかの理由で Exchange 2016 に移行できない場合は、Exchange 2013 などと同じプロセスを実行します。

|考慮事項|詳細情報|
|---|---|
|サポート終了日| Exchange 2007 と同様に、Exchangeの各バージョンには、独自のサポート終了日があります。 <br/> *Exchange 2010* - 2020 年 1 月 <br/> *Exchange 2013* - 2023 年 4 月 <br/> *Exchange 2016* - 2025 年 10 月 <br/> サポートの終了が早ければ早いほど、別の移行を実行する必要があります。|
|Exchange 2010 と 2013 への移行パス。|Exchange 2010 または Exchange 2013 に移行するための一般的なフェーズを次に示します。 <br/> - Exchange 2010 または 2013 を既存の Exchange 2007 組織にインストールします。 <br/>- サービスとその他のインフラストラクチャを 2010 または 2013 Exchangeに移動します。<br/>- メールボックスとパブリック フォルダーを 2010 または 2013 Exchangeに移動します。<br/>- 残りの 2007 サーバー Exchange使用停止します。|
|Exchange 2016 への移行パス|Exchange 2016 に移行するための一般的なフェーズを次に示します。 <br/> - Exchange 2013 を既存のExchange 2007 組織にインストールします。<br/>- サービスとその他のインフラストラクチャを Exchange 2013 に移動します。<br/>- メールボックスとパブリック フォルダーを Exchange 2013 に移動します。<br/>- 残りの 2007 サーバー Exchange使用停止します。<br/>- Exchange 2016 を既存のExchange 2013 組織にインストールします。<br/>- メールボックス、パブリック フォルダー、サービス、その他のインフラストラクチャを 2016 Exchangeに移動します (順序は関係ありません)。 残りの 2013 サーバー Exchange使用停止します。<br/><br/> **メモ：** Exchange 2013 から Exchange 2016 への移行は簡単です。 2 つのバージョンのハードウェア要件はほぼ同じであり、これらのバージョンは非常に互換性があります。 そのため、Exchange 2013 用に購入したサーバーをリビルドし、Exchange 2016 をインストールできます。 オンライン メールボックスの移動の場合、ほとんどのユーザーは、メールボックスがサーバーから移動され、2016 Exchangeで再構築された後に戻ったことに気付くことさえありません。|
|バージョンの共存| に移行する場合... <br/> **Exchange 2016:** Exchange 2016 は、Exchange 2007 サーバーを含む組織にインストールできません。 最初に 2010 または 2013 Exchangeに移行し (2013 Exchange強くお勧めします)、Exchange 2007 サーバーをすべて削除してから、2016 Exchangeに移行する必要があります。 <br/> **Exchange 2010 または Exchange 2013:** Exchange 2010 または Exchange 2013 を既存の Exchange 2007 組織にインストールできます。 これにより、2010 または 2013 サーバー Exchange 1 つ以上をインストールし、移行を実行できます。|
|サーバー ハードウェア| サーバー ハードウェアの要件は、2007 Exchangeから変更されました。 ハードウェアに互換性があることを確認します。 詳細については、以下を参照してください。 <br/> [Exchange 2016 システム要件](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 システム要件](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 システム要件](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/> Exchangeパフォーマンスの大幅な向上と、新しいサーバーでのコンピューティング能力とストレージ容量の増加により、同じ数のメールボックスをサポートするために必要なサーバーが少なくなる可能性があります。|
|オペレーティング システムのバージョン| 各バージョンでサポートされているオペレーティング システムの最小バージョンは次のとおりです。 <br/> **Exchange 2016** - Windows Server 2012 <br/> **Exchange 2013** - Windows Server 2008 R2 SP1 <br/> **Exchange 2010** - Windows Server 2008 SP2 <br/> オペレーティング システムのサポートの詳細については[、サポートマトリックスExchange参照](/Exchange/plan-and-deploy/supportability-matrix)してください。|
|Active Directory フォレストの機能レベル| 各バージョンでサポートされている最小の Active Directory フォレスト機能レベルは次のとおりです。 <br/> **Exchange 2016** Windows Server 2008 R2 SP1 <br/> **Exchange 2013** Windows Server 2003 <br/> **Exchange 2010** Windows Server 2003 <br/> フォレストの機能レベルのサポートの詳細については[、サポートマトリックスExchange](/Exchange/plan-and-deploy/supportability-matrix)参照してください。|
|Office クライアント バージョン| 各バージョンでサポートされている最小Officeクライアント バージョンは次のとおりです。 <br/> **Exchange 2016** - Office 2010 (最新の更新プログラムを使用) <br/> **Exchange 2013** - Office 2007 SP3 <br/> **Exchange 2010** - Office 2003 <br/> Exchange [Supportability Matrix](/Exchange/plan-and-deploy/supportability-matrix) でOfficeクライアント サポートの詳細を確認してください。|

#### <a name="how-do-i-migrate"></a>移行操作方法?

電子メールをオンプレミスに保持することにした場合は、次のリソースを使用して移行を支援します。

- [Exchange 展開アシスタント](/exchange/exchange-deployment-assistant)

- Exchange [2016、2013](/Exchange/plan-and-deploy/active-directory/ad-schema-changes)、[2010](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help) の Active Directory スキーマの変更 [](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)

- [Exchange 2016、2013](/Exchange/plan-and-deploy/system-requirements)、[2010](/exchange/exchange-2013-system-requirements-exchange-2013-help) のシステム要件 [](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))

- [Exchange 2016、2013](/Exchange/plan-and-deploy/prerequisites)、[2010](/exchange/exchange-2013-prerequisites-exchange-2013-help) の前提条件 [](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))

## <a name="get-help"></a>ヘルプを参照する

Microsoft 365に移行する場合は、Microsoft FastTrack サービスを使用できる可能性があります。 FastTrackには、Microsoft 365への移行を可能な限りシームレスにするためのベスト プラクティス、ツール、リソースが用意されています。 何より、サポート エンジニアが、計画と設計から最後のメールボックスの移行まで、移行について説明します。 FastTrackの詳細については、「[Microsoft FastTrack](https://fasttrack.microsoft.com/)」を参照してください。

Microsoft 365への移行中に問題が発生し、FastTrackを使用していない場合、または新しいバージョンのExchange Serverへの移行を行っていない場合は、こちらにお問い合わせください。 使用できるリソースを次に示します。

- [テクニカル コミュニティ](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)

- [カスタマー サポート](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-topics"></a>関連項目

[Office 2007 のサーバーとクライアントのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
