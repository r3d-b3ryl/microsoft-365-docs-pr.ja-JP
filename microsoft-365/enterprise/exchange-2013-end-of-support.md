---
title: Exchange 2013 サポートロードマップの終了
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2013 は、2023 年 4 月にサポートが終了します。 この計画ロードマップを使用して、Exchange Online以降のバージョンのExchange Serverオンプレミスにアップグレードする準備をします。
ms.openlocfilehash: 0d0cf068ad018e710c6d8e861ac04acfd261def9
ms.sourcegitcommit: da6b3cb3b2ccfcdcd5091efce8290b6c486547db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/18/2022
ms.locfileid: "65468506"
---
# <a name="exchange-2013-end-of-support-roadmap"></a>Exchange 2013 サポートロードマップの終了

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Exchange Server 2013 は、**2023 年 4 月 11** 日にサポートが終了します。 2013 年Exchangeから 2019 年のMicrosoft 365、Office 365、またはExchangeへの移行をまだ開始していない場合は、計画を開始します。

## <a name="what-does-end-of-support-mean"></a>*サポート終了とは* どういう意味ですか?

ほとんどの Microsoft 製品には、新機能、バグ修正、セキュリティ修正などのサポート ライフサイクルがあります。 このライフサイクルは通常、製品の初期リリースから 10 年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Exchange 2013 は 2023 年 4 月 11 日にサポートの終了に達したため、Microsoft はこの日以降、次の情報を提供しなくなります。

- 発生する可能性がある問題のテクニカル サポート。
- サーバーの安定性と使いやすさに影響を与える可能性がある問題に関するバグ修正。
- サーバーがセキュリティ違反に対して脆弱になる可能性がある脆弱性に対するセキュリティ修正。
- タイム ゾーンの更新。

Exchange 2013 のインストールは、この日以降も引き続き実行されます。 ただし、上記の変更により、Exchange 2013 から 2019 Exchangeにできるだけ早く移行することを強くお勧めします。


## <a name="what-are-my-options"></a>使用できるオプション

オプションを調べ、移行計画を準備するのに最適な時期です。 次の操作を行うことができます:

- Microsoft 365に移行します。 カットオーバー、最小限のハイブリッド、または完全なハイブリッド移行を使用して、メールボックス、パブリック フォルダー、およびその他のデータを移行します。 次に、オンプレミスのExchange サーバーと Active Directory を削除します。
- 2013 Exchangeアップグレードします。 オンプレミス サーバーの Exchange 2019 に移行します。

> [!IMPORTANT]
> 組織がメールボックスをMicrosoft 365に移行することを選択したが、Azure AD Connectを使用して Active Directory のユーザー アカウントを管理し続ける予定の場合は、少なくとも 1 つの Microsoft Exchange サーバーをオンプレミスに保持する必要があります。 すべてのExchange サーバーを削除すると、権限のソースがオンプレミスの Active Directoryであるため、Exchange OnlineのExchange受信者に変更を加えることはできません。 このシナリオでは、次のオプションがあります。
>
>- *推奨：* メールボックスをMicrosoft 365に移行し、2023 年 4 月 11 日までに環境を Exchange 2019 にアップグレードします。 Exchange 2013 を使用して、Microsoft 365に接続し、メールボックスを移行します。 次に、Exchange 2013 から 2019 Exchangeにアップグレードし、Exchange 2013 を実行しているサーバーを使用停止します。
>- Exchange Onlineへの移行を完了し、2023 年 4 月 11 日までにオンプレミス サーバーをアップグレードできない場合は、Exchange 2013 から 2019 Exchangeにアップグレードしてから、Exchange 2019 を使用してメールボックスをMicrosoft 365に移行します。

Exchange Server 2013 のサポートが終了しないようにするために実行できる 3 つのパスを次に示します。

## <a name="migrate-to-microsoft-365"></a>Microsoft 365 に移行する

Microsoft 365への移行は、Exchange 2013 のデプロイを廃止するのに役立つ最も簡単なオプションです。 Microsoft 365への移行では、次のような古いテクノロジから現在の機能にシングル ホップを作成できます。

- データ回復性が高い大規模なメールボックス。
- スパム対策やマルウェア対策などのセキュリティ機能、 
- データ損失防止、アイテム保持ポリシー、In-Placeおよび訴訟ホールド、インプレース電子情報開示などのコンプライアンス機能。
- SharePoint Online、OneDrive、Teams、Power BI、その他のMicrosoft 365 サービスとの統合。
- 重点を置いた受信トレイ。そして
- 高度な分析とViva インサイト。

Microsoft 365では、新しい機能とエクスペリエンスも最初に取得されるため、組織ですぐに使用を開始できます。 また、次のことを心配する必要はありません。

- ハードウェアの購入と保守;
- サーバーを実行して冷却するために支払う。
- セキュリティ、製品、およびタイム ゾーンの修正に関するサーバーを最新の状態に保つ。
- コンプライアンス要件をサポートするためのサーバー ストレージとソフトウェアの保守。または
- 新しいバージョンのExchangeにアップグレードすると、常に最新バージョンにMicrosoft 365。

### <a name="how-should-i-migrate-to-microsoft-365"></a>Microsoft 365に移行するにはどうすればよいですか?

組織によっては、Microsoft 365にアクセスするためのいくつかのオプションがあります。 まず、次のようないくつかの点を考慮する必要があります。

- 移動する必要があるメールボックスの数。
- 移行を継続する期間。そして
- 移行中にオンプレミス環境とMicrosoft 365間のシームレスな統合が必要かどうか。

次の表に、移行オプションと、使用する方法を決定する最も重要な要因を示します。

<br>

****

|移行オプション|組織のサイズ|期間|
|---|---|---|
|カットオーバー移行|メールボックスが 150 個未満|1 週間以下|
|最小限のハイブリッド移行|メールボックスが 150 個未満|数週間以下|
|完全なハイブリッド移行|150 を超えるメールボックス|数週間以上|
|

次のセクションでは、これらのメソッドの概要について説明します。 詳細については、「 [移行パスの決定](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)」を参照してください。

### <a name="cutover-migration"></a>カットオーバー移行

一括移行では、すべてのメールボックス、配布グループ、連絡先などを、設定された日時にOffice 365に移行します。 完了したら、オンプレミスのExchange サーバーをシャットダウンし、Microsoft 365を排他的に使用し始めます。

一括移行は、メールボックスの数が少ない小規模な組織や、Microsoft 365を迅速に行い、他の方法の複雑さに対処したくない小規模な組織に適しています。 ただし、1 週間以内に完了する必要があります。 また、ユーザーはOutlookプロファイルを再構成する必要があります。 一括移行では最大 2,000 個のメールボックスを移行できますが、最大 150 個のメールボックスに移行することをお勧めします。 より多くの移行を試みると、期限までにすべてのメールボックスを転送する時間が不足する可能性があります。また、IT サポート スタッフは、ユーザーがOutlookを再構成するのに役立つ要求に圧倒される可能性があります。

一括移行について考慮すべき点を次に示します。

- Microsoft 365は、OUTLOOK Anywhere over TCP ポート 443 を使用して、Exchange 2013 サーバーに接続する必要があります。
- オンプレミスのすべてのメールボックスは、Microsoft 365に移動されます。
- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
- Microsoft 365で使用するExchange 2013 承認済みドメインは、サービス内の検証済みドメインとして追加する必要があります。
- 移行を開始してから完了フェーズを開始するまで、Microsoft 365はMicrosoft 365とオンプレミスのメールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスに電子メールが残される心配なく移行を完了できます。
- ユーザーは、Microsoft 365 アカウントの新しい一時パスワードを受け取ります。 メールボックスに初めてサインインするときに、それらを変更する必要があります。
- 移行する各ユーザー メールボックスのExchange Onlineを含むMicrosoft 365 ライセンスが必要です。
- ユーザーは、各デバイスに新しいOutlook プロファイルを設定し、もう一度電子メールをダウンロードする必要があります。 Outlookがダウンロードする電子メールの量は異なる場合があります。 詳細については、「[Outlookでオフラインで作業する](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)」を参照してください。

一括移行の詳細については、次を参照してください。

- [一括メール移行について知っておくべきこと](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [Office 365へのメールの一括移行を実行する](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>最小限のハイブリッド移行

最小限のハイブリッドまたは高速移行では、数週間以内に数百個のメールボックスをMicrosoft 365に移動します。 このメソッドでは、空き時間情報の共有予定表情報などの高度なハイブリッド移行機能はサポートされていません。

最小限のハイブリッド移行は、メールボックスをMicrosoft 365に移行する時間を増やす必要があるが、数週間以内に移行を完了する予定の組織に適しています。 複雑さの多くなく、より高度な *フル ハイブリッド移行* の利点の一部を得ることができます。 特定の時点で移行するメールボックスの数とメールボックスの数を制御できます。 Microsoft 365メールボックスは、オンプレミス アカウントのユーザー名とパスワードを使用して作成されます。 また、一括移行とは異なり、ユーザーはOutlookプロファイルを再作成する必要はありません。

最小限のハイブリッド移行について考慮する必要がある事項を次に示します。

- オンプレミスの Active Directory サーバーとMicrosoft 365間で 1 回限りのディレクトリ同期を実行する必要があります。
- ユーザーは、自分のメールボックスの前と同じユーザー名とパスワードを使用して、Microsoft 365 メールボックスにサインインできます。
- 移行する各ユーザー メールボックスのExchange Onlineを含むMicrosoft 365 ライセンスが必要です。
- ユーザーは、ほとんどのデバイスで新しいOutlook プロファイルを設定する必要はありませんが、古いAndroid電話の中には新しいプロファイルが必要な場合があります。 ユーザーは自分のメールを再ダウンロードする必要はありません。

詳細については、「[最小ハイブリッドを使用して、ExchangeメールボックスをすばやくOffice 365に移行する」を参照](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)してください。

### <a name="full-hybrid"></a>フル ハイブリッド

完全ハイブリッド移行では、数百、最大数万のメールボックスがあり、一部または全部をMicrosoft 365に移動します。 これらの移行は通常、より長期的であるため、ハイブリッド移行では次の処理を行うことができます。

- オンプレミスユーザーに、Microsoft 365のユーザーの空き時間情報の予定表情報を表示します。また、その逆も同様です。
- オンプレミスとMicrosoft 365の両方の受信者を含む統合グローバル アドレス一覧を参照してください。
- オンプレミスかMicrosoft 365かに関係なく、すべてのユーザーの完全なOutlook受信者プロパティを表示します。
- TLS と証明書を使用して、オンプレミスのExchange サーバーとOffice 365間の電子メール通信をセキュリティで保護します。
- オンプレミスのExchange サーバーとMicrosoft 365間で送信されたメッセージを内部として扱い、次の処理を行うことができます。
  - 内部メッセージをターゲットとするトランスポート エージェントとコンプライアンス エージェントによって適切に評価され、処理されます。
  - スパム対策フィルターをバイパスします。

完全なハイブリッド移行は、何か月以上ハイブリッド構成を維持する予定の組織に最適です。 このセクションで前述した機能に加えて、ディレクトリ同期、統合コンプライアンス機能の強化、およびオンライン メールボックスの移動を使用してメールボックスをMicrosoft 365との間で移動する機能を利用できます。 Microsoft 365は、オンプレミス組織の拡張機能になります。

フル ハイブリッド移行について考慮する必要がある事項:

- すべての組織に適しているわけではありません。 完全なハイブリッド移行の複雑さのために、数百個未満のメールボックスを持つ組織には、通常、関係する労力とコストを正当化する利点は見られません。 このような場合は、代わりにカットオーバーまたは最小限のハイブリッド移行を検討することをお勧めします。
- オンプレミスの Active Directory サーバーとMicrosoft 365間のAzure Active Directory (Azure AD) Connectを使用してディレクトリ同期を設定する必要があります。
- ユーザーは、ローカル ネットワークにサインインするときに使用するのと同じユーザー名とパスワードを使用して、自分のMicrosoft 365 メールボックスにサインインできます。 (この機能では、パスワード同期やActive Directory フェデレーション サービス (AD FS)を使用した Azure AD Connectが必要です)。
- 移行する各ユーザー メールボックスのExchange Onlineを含むMicrosoft 365 ライセンスが必要です。
- ユーザーは、ほとんどのデバイスで新しいOutlook プロファイルを設定する必要はありませんが、古いAndroid電話の中には新しいプロファイルが必要な場合があります。 ユーザーは自分のメールを再ダウンロードする必要はありません。

> [!IMPORTANT]
> 組織がメールボックスをMicrosoft 365に移行することを選択したが、Active Directory でユーザー アカウントを管理するために Azure AD Connectを維持する予定の場合は、少なくとも 1 つのExchange サーバーをオンプレミスに保持する必要があります。 すべてのExchange サーバーが削除された場合、Exchange受信者に変更を加えることはできません。 これは、権限のソースが Active Directory であり、そこで変更を加える必要があるためです。

完全なハイブリッド移行が適切に機能する場合は、次の便利なリソースを参照してください。

- [Exchange 展開アシスタント](/exchange/exchange-deployment-assistant)
- [Exchange Server のハイブリッド展開](/exchange/exchange-hybrid)
- [ハイブリッド構成ウィザード](/exchange/hybrid-configuration-wizard)
- [ハイブリッド構成ウィザードに関する FAQ](/exchange/hybrid-configuration-wizard-faqs)
- [ハイブリッド展開の前提条件](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>オンプレミスの新しいバージョンのExchange Serverにアップグレードする

Microsoft 365に完全に移行することで、最適な価値とユーザー エクスペリエンスを得られると強く考えています。 ただし、一部の組織では、一部のExchange サーバーをオンプレミスに保持する必要があることを理解しています。 これは、規制要件が原因である可能性があります。データが外部データセンターに格納されないことを保証するには、クラウドでは満たされない一意の設定または要件があるか、オンプレミスの Active Directory を引き続き使用するため、クラウド メールボックスを管理するExchangeが必要であるためです。 いずれの場合も、オンプレミスExchange維持する場合は、Exchange 2013 環境がアップグレードされていることを確認する必要があります。

最適なエクスペリエンスを得るには、残りのオンプレミス環境を 2019 Exchangeにアップグレードすることをお勧めします。 Exchange Server 2013 から Exchange Server 2019 に直接移動できるため、Exchange Server 2016 をインストールする必要はありません。 Exchange 2019 は、Microsoft 365で使用できるエクスペリエンスと最もよく一致しますが、一部の機能はMicrosoft 365でのみ使用できます。



****
Exchange 2013 のアップグレードについて知っておくべき重要な点を次に示します。

|アイテム|詳細情報|
|---|---|
|サポート終了日|Exchange 2013 と同様に、Exchangeの各バージョンには、独自のサポート終了日があります。 <p> Exchange 2013 - 2023 年 4 月 <p> 2023 年 4 月は、思ったよりずっと近いです。|
|Exchange 2019 への移行パス|Exchange 2013 から新しいバージョンへの移行パスは簡単です。 <p> Exchange 2019 を既存の Exchange 2013 組織にインストールします。 <p> サービスとデータを 2013 Exchangeから 2019 Exchangeに移動し、2013 サーバー Exchange使用停止します。|
|サーバー ハードウェア|サーバーハードウェアの要件は、2013 Exchangeから変更されました。 ハードウェアに互換性があることを確認します。 ハードウェア要件の詳細については、以下をご覧ください。 <p> [Exchange 2019 システム要件](/exchange/plan-and-deploy/system-requirements?view=exchserver-2019) <p>Exchangeのパフォーマンスが大幅に向上し、新しいサーバーのコンピューティング能力とストレージ容量が向上するため、同じ数のメールボックスをサポートするために必要なサーバーが少なくなる可能性があります。|
|オペレーティング システムのバージョン|Exchange 2019 でサポートされているオペレーティング システムの最小バージョンは、Server 2019 Windowsです。 Windows Server 2022 のサポートは近日公開予定です <p> オペレーティング システムのサポートの詳細については、[サポート可能性マトリックスExchange](/exchange/plan-and-deploy/supportability-matrix)参照してください。|
|Active Directory フォレストの機能レベル|サポートされている Active Directory フォレストの最小機能レベルは R2 Windows Server 2012です。 フォレストの機能レベルのサポートの詳細については、[Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix) を参照してください。|
|Office クライアント バージョン|サポートされている最小Officeクライアント バージョンも[、Exchange Supportability Matrix](/exchange/plan-and-deploy/supportability-matrix?view=exchserver-2019#clients) に記載されています。|
|

移行に役立つ次のリソースを使用します。

- [Exchange 展開アシスタント](/exchange/exchange-deployment-assistant)
- [Exchange 2019 の Active Directory スキーマの変更](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2019)
- [Exchange 2019 のシステム要件](/exchange/plan-and-deploy/system-requirements?view=exchserver-2019)


## <a name="what-if-i-need-help"></a>ヘルプが必要な場合はどうすればよいですか?

Microsoft 365に移行する場合は、Microsoft FastTrack サービスを使用できる可能性があります。 FastTrackには、Microsoft 365への移行を可能な限りシームレスにするためのベスト プラクティス、ツール、リソースが用意されています。 何より、サポート エンジニアが計画と設計から最後のメールボックスの移行までの手順を説明します。 FastTrackの詳細については、「[Microsoft FastTrack](https://fasttrack.microsoft.com/)」を参照してください。

Microsoft 365への移行中に問題が発生し、FastTrackを使用していない場合、または新しいバージョンのExchange Serverに移行する場合は、次のリソースを使用できます。

- [テクニカル コミュニティ](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [カスタマー サポート](https://support.microsoft.com/gp/support-options-for-business)


