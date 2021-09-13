---
title: Exchange 2007 のサポート終了ロードマップ
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 2007 Exchange Server サポートが終了した後のオプションについて説明し、Microsoft 365、Office 365、または Exchange 2016 への移行の計画を開始します。
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218564"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Exchange Server 2007 年 4 月にサポートが終了しました。 Exchange 2007 から Microsoft 365、Office 365、または Exchange 2016 への移行を開始していない場合は、計画を開始します。
  
## <a name="what-does-end-of-support-mean"></a>サポート終了 *とはどういう意味* ですか?

Exchange Serverほぼすべての Microsoft 製品と同様に、サポート ライフサイクルが提供され、その間に新機能、バグ修正、セキュリティ修正プログラムが提供されます。 このライフサイクルは、通常、製品の最初のリリースから 10 年間続く。 このライフサイクルの終了は、製品のサポート終了と呼ばれる。 2007 Exchange 2017 年 4 月 11 日にサポートが終了して以来、Microsoft は次の機能を提供しなくなりました。
  
- 発生する可能性のある問題に対するテクニカル サポート。
    
- サーバーの安定性と使いやすさに影響を与える可能性がある問題のバグ修正。
    
- サーバーがセキュリティ侵害に対して脆弱になる可能性のある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
2007 Exchangeのインストールは、サポート終了日後も実行されます。 ただし、新しい更新プログラムやサポートはないので、できるだけ早く 2007 Exchange移行することを強く推奨します。
  
サポートの終了に近Office 2007 サーバーの詳細については、「Plan your upgrade [from Office 2007 サーバー](upgrade-from-office-2007-servers-and-products.md)と製品」を参照してください。
  
## <a name="what-are-my-options"></a>使用できるオプション

次の操作を実行できます。
  
- カットオーバー、Microsoft 365、またはハイブリッド移行を使用して、ユーザーに移行します。
    
- 2007 Exchangeをオンプレミス サーバー上の新しいバージョンExchangeに移行します。
    
以下のセクションでは、各オプションについて詳しく説明します。
  
### <a name="migrate-to-microsoft-365"></a>Microsoft 365 に移行する

メールを 2007 Microsoft 365に移行する方法は、2007 年の展開を廃止するのにExchange最も簡単なオプションです。 Microsoft 365への移行では、10 年のテクノロジから以下を含む最新の機能への単一ホップを作成できます。
  
- 保持ポリシー、In-Place訴訟ホールド、インプレイス電子情報開示などのコンプライアンス機能
    
- Microsoft 365 グループ
    
- 優先受信トレイ
    
- MyAnalytics
    
- 電子メール、予定表、連絡先などへのプログラムによるアクセス用の REST API
    
Microsoft 365新機能やエクスペリエンスも最初に取得します。そのため、ユーザーとユーザーは通常、それらをすぐ使い始めできます。 また、次のことを心配する必要はありません。
  
- ハードウェアの購入と保守。
    
- サーバーの熱と冷却に対する支払い。
    
- セキュリティ、製品、およびタイム ゾーンの修正を最新の状態に保つ。
    
- コンプライアンス要件をサポートするためのストレージとソフトウェアの維持。
    
- 新しいバージョンのサーバーにアップグレードExchange。 このMicrosoft 365を使用すると、常に最新バージョンの Exchange。
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>ユーザーに移行するMicrosoft 365?

いくつかの移行オプションがあります。 次のようないくつかの点を考慮する必要があります。

- 移動する必要があるシートまたはメールボックスの数。
- 移行を実行する期間。
- 移行中にオンプレミスのインストールとサーバー間のシームレスな統合が必要Microsoft 365かどうか。

次の表に、移行オプションと、使用する方法を決定する最も重要な要素を示します。
  

|**移行オプション**|**組織のサイズ**|**Duration**|
|:-----|:-----|:-----|
|カットオーバー移行  <br/> |シート数が 150 未満  <br/> |1 週間以下  <br/> |
|段階的な移行  <br/> |150 席以上  <br/> |数週間  <br/> |
|完全なハイブリッド移行  <br/> |数百から数千のシート  <br/> |数か月以上  <br/> |
   
以下のセクションでは、これらのメソッドの概要について説明します。 詳細については、「移行パスを [決定する」を参照してください](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)。 
  
#### <a name="cutover-migration"></a>カットオーバー移行

カットオーバー移行では、すべてのメールボックス、配布グループ、連絡先など、事前に選択された日時Microsoft 365に移行します。 移行が完了したら、オンプレミスのサーバーをシャットダウンし、Exchange専用Microsoft 365開始します。
  
カットオーバー移行は、多くのメールボックスを持たなかったり、Microsoft 365 にすばやくアクセスしたい、他の方法の複雑な一部に対処したくない小規模な組織に最適です。 ただし、1 週間以下で完了する必要があります。ユーザーはユーザーのプロファイルを再構成Outlook必要があります。 カットオーバー移行では最大 2,000 のメールボックスを処理できますが、最大 150 のメールボックスを移行するために使用することを強く推奨します。 より多くの移行を試みた場合、期限前にすべてのメールボックスを転送する時間が切れる可能性があります。また、IT サポート スタッフは、ユーザーが Outlook を再構成するための要求に圧倒される可能性があります。
  
一切の移行を検討している場合は、次の点を考慮してください。
  
- Microsoft 365 2007 サーバーに接続するには、TCP ポート 443 Exchange Anywhere を使用Outlook 2007 サーバーに接続する必要があります。
    
- すべてのオンプレミス のメールボックスは、すべてのメールボックスにMicrosoft 365。
    
- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
    
- Exchangeで使用する 2007 のドメインをMicrosoft 365サービスに検証済みドメインとして追加する必要があります。
    
- 移行を開始して完了フェーズを開始する間に、Microsoft 365メールボックスとMicrosoft 365を定期的に同期します。 これにより、オンプレミスのメールボックスにメールが残る心配なしに移行を完了できます。
    
- ユーザーは、自分のアカウントの新しい一時的なパスワードMicrosoft 365します。 メールボックスに初めてサインインするときに、パスワードを変更する必要があります。
    
- 移行する各ユーザー メールボックスMicrosoft 365をExchange Onlineライセンスが必要です。
    
- ユーザーは、各デバイスで新しいOutlookプロファイルを設定し、電子メールを再度ダウンロードする必要があります。 ダウンロードするメールのOutlook異なる場合があります。 詳細については、「オフラインで保持 [するメールの量を変更する」を参照してください](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
カットオーバー移行の詳細については、以下を参照してください。
  
- [メールの一切の移行について知る必要がある情報](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [メールのカットオーバー移行を実行する](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>段階的な移行

ステージ移行では、Microsoft 365 に移行する数百または数千のメールボックスを持ち、移行を完了するには 1 週間以上かかる必要があります。また、共有の空き時間情報のような高度なハイブリッド移行機能は必要とされません。
  
ステージ移行は、メールボックスを Microsoft 365 に移行する必要があるが、数週間以内に移行を完了する予定の組織に最適です。 メールボックスはバッチで移行できます。 一度に移行するメールボックスの数とメールボックスの数を制御します。 たとえば、同じ部署のユーザーのメールボックスをバッチ処理して、すべてのユーザーが同時に移動される可能性があります。 または、最後のバッチまでエグゼクティブ メールボックスを残す場合があります。 カットオーバー移行と同様に、ユーザーはユーザーのプロファイルを再作成Outlook必要があります。
  
ステージ移行の実行を検討している場合は、次の点を考慮する必要があります。
  
- Microsoft 365 2007 サーバーに接続するには、TCP ポート 443 Exchange Anywhere を使用Outlook 2007 サーバーに接続する必要があります。
    
- ユーザーのメールボックスへの読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
    
- Exchangeで使用する予定の 2007 のドメインをMicrosoft 365サービスに検証済みドメインとして追加する必要があります。
    
- バッチで移行する予定の各メールボックスの完全な名前と電子メール アドレスを含む CSV ファイルを作成する必要があります。 また、移行するメールボックスごとに新しいパスワードを含め、そのパスワードを各ユーザーに送信する必要があります。 ユーザーは、新しいメールボックスに初めてサインインした場合にパスワードを変更するように求Microsoft 365されます。
    
- 移行バッチを開始して完了フェーズを開始する間、Microsoft 365 はバッチに含まれる Microsoft 365 メールボックスとオンプレミス メールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスにメールが残る心配なしに移行を完了できます。
    
- 移行する各ユーザー メールボックスMicrosoft 365をExchange Onlineライセンスが必要です。
    
- ユーザーは、各デバイスで新しいOutlookプロファイルを設定し、電子メールを再度ダウンロードする必要があります。 ダウンロードするメールのOutlook異なる場合があります。 詳細については、「オフラインで保持 [するメールの量を変更する」を参照してください](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)。
    
ステージ移行の詳細については、以下を参照してください。
  
- [電子メールのステージ移行について知る必要がある情報](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [電子メールのステージ移行を実行する](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>フル ハイブリッド

完全なハイブリッド移行では、組織には数百、最大数万のメールボックスが含め、一部またはすべてのメールボックスを Microsoft 365 に移動する必要があります。 通常、これらの移行は長期的な移行なので、ハイブリッド移行によって次の作業が可能になります。
  
- オンプレミス のユーザーに、ユーザーの空き時間情報を表示し、その逆Microsoft 365を表示します。
    
- オンプレミスとユーザーの両方の受信者を含む統合グローバル アドレス一覧をMicrosoft 365。
    
- オンプレミスまたはOutlookに関係なく、すべてのユーザーの完全な受信者プロパティを表示Microsoft 365。
    
- TLS と証明書を使用して、オンプレミスExchangeサーバーとMicrosoft 365メール通信をセキュリティで保護します。
    
- 社内サーバーとサーバー間で送信されるExchangeを内部Microsoft 365として扱い、次の処理を可能にします。
    
  - 内部メッセージを対象とするトランスポートおよびコンプライアンス エージェントによって適切に評価され、処理されます。
    
  - スパム対策フィルターをバイパスします。
    
完全なハイブリッド移行は、何か月以上ハイブリッド構成にとどまる必要がある組織に最適です。 このセクションの前に示した機能と、ディレクトリ同期、より統合されたコンプライアンス機能、およびオンライン メールボックスの移動を使用して Microsoft 365 との間でメールボックスを移動する機能を取得します。 Microsoft 365オンプレミス組織の拡張機能になります。
  
完全なハイブリッド移行を検討している場合は、次の点を検討してください。
  
- 完全なハイブリッド移行は、すべての種類の組織に適しているのではない。 完全なハイブリッド移行の複雑さのため、数百未満のメールボックスを持つ組織では、通常、1 つをセットアップするために必要な労力とコストを正当化する利点は表示されません。 組織のように聞こえる場合は、代わりにカットオーバーまたはステージ移行を検討することをお勧めします。
    
- "ハイブリッド サーバー" として機能するには、Exchange 2013 組織に少なくとも 1 つの Exchange 2013 サーバーを展開する必要があります。 このサーバーは、2007 Microsoft 365サーバーに代わってExchange通信します。
    
- Microsoft 365 TCP ポート 443 上の Anywhere を使用してOutlook"ハイブリッド サーバー" に接続する必要があります。
    
- オンプレミスの Active Directory サーバーとサーバー間の Azure Active Directory (Azure AD) Connect を使用してディレクトリ同期を設定する必要Microsoft 365。
    
- ユーザーは、ローカル ネットワークにサインインするMicrosoft 365と同じユーザー名とパスワードを使用して、自分のメールボックスにサインインできます。 (この機能では、パスワード同期AD Connect Active Directory フェデレーション サービスを使用して Azure サーバーを使用する必要があります)。
    
- 移行する各ユーザー メールボックスMicrosoft 365をExchange Onlineライセンスが必要です。
    
- 一部の古い Android 携帯電話では新しいプロファイルが必要になる場合Outlook、ほとんどのデバイスで新しいプロファイルをセットアップする必要があります。 ユーザーは自分のメールを再ダウンロードする必要がなされます。
    
完全なハイブリッド移行が適切に行う場合は、移行に役立つ次のリソースを参照してください。
  
- [Exchange展開アシスタント](/exchange/exchange-deployment-assistant)
    
- [Exchange Server のハイブリッド展開](/exchange/exchange-hybrid)
    
- [ハイブリッド構成ウィザード](/exchange/hybrid-configuration-wizard)
    
- [ハイブリッド構成ウィザードに関する FAQ](/exchange/hybrid-configuration-wizard-faqs)
    
- [ハイブリッド展開の前提条件](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>新しいバージョンのサーバーに移行Exchange Server

弊社は、お客様が最適な価値とユーザー エクスペリエンスを実現できると強く考Microsoft 365。 ただし、一部の組織では電子メールをオンプレミスに保持する必要がある場合もあります。 これは、規制要件が理由で、データが他の国にあるデータセンターに保存されていないか、または類似していることを保証するために発生する可能性があります。 メールをオンプレミスに保持する場合は、Exchange 2007 環境を Exchange 2010、Exchange 2013、または Exchange 2016 に移行できます。
  
移行できない場合は、Microsoft 365 2016 に移行Exchange勧めします。 Exchange 2016 には、以前のリリースのすべての機能が含Exchange。 また、一部の機能は Microsoft 365 でのみ使用できるが、Microsoft 365。 不足しているいくつかの情報を確認してください。
  
|**Exchangeリリース**|**機能**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Basedアクセス制御 (ACL のないアクセス許可)  <br/>  Outlook Web App メールボックス ポリシー  <br/>  組織間で空き時間情報を共有し、予定表を委任する機能  <br/> |
|Exchange 2013  <br/> | *2010 Exchange ..の機能。*  <br/>  サーバーの役割の数を 3 に減らした簡略化されたアーキテクチャ (メールボックス、クライアント アクセス、エッジ トランスポート)  <br/>  機密情報の漏洩防止に役立つデータ損失防止ポリシー (DLP)  <br/>  改善されたOutlook Web Appエクスペリエンス  <br/> |
|Exchange 2016  <br/> | *2013 Exchange ..の機能。*  <br/>  メールボックスとエッジ トランスポートに対するサーバーの役割の簡素化  <br/>  DLP の強化と、データの統合SharePoint  <br/>  データベースの復元性の向上  <br/>  オンライン ドキュメントの共同作業 |
   
#### <a name="which-version-should-i-migrate-to"></a>どのバージョンに移行する必要がありますか?

最初は、2016 年から 2016 年Exchangeすることをお勧めします。 次に、次の情報を使用して前提を確認するか、2016 年Exchangeします。 何らかの理由で Exchange 2016 に移行できない場合は、Exchange 2013 などと同じプロセスを実行します。
  
|**考慮事項**|**詳細情報**|
|:-----|:-----|
|サポート終了日  <br/> | 2007 Exchangeと同様に、各バージョンExchangeサポート終了日が設定されています。  <br/> *Exchange 2010* - 2020 年 1 月  <br/> *Exchange 2013* - 2023 年 4 月  <br/> *Exchange 2016* - 2025 年 10 月  <br/>  サポートが終了する前に、別の移行を実行する必要が早く行う必要があります。<br/> |
|2010 Exchange 2013 への移行パス。  <br/> |2010 年または 2013 年Exchange移行Exchange次に示します。  <br/> - 2010 Exchange 2013 を既存の 2007 組織Exchangeインストールします。 <br/>- サービスと他のインフラストラクチャを 2010 または 2013 Exchangeに移動します。<br/>- メールボックスとパブリック フォルダーを 2010 または 2013 Exchangeに移動します。<br/>- 2007 サーバー Exchange使用を停止します。 |
|2016 年Exchange移行パス  <br/> |2016 年に移行する一般的なExchange次に示します。  <br/> - 2013 Exchange 2007 組織に 2013 Exchangeインストールします。<br/>- サービスと他のインフラストラクチャを 2013 年Exchangeします。<br/>- メールボックスとパブリック フォルダーを 2013 年Exchange移動します。<br/>- 2007 サーバー Exchange使用を停止します。<br/>- 2016 Exchange 2013 組織に 2016 Exchangeインストールします。<br/>- メールボックス、パブリック フォルダー、サービス、その他のインフラストラクチャを 2016 年Exchangeに移動します (順序は関係ありません)。 2013 サーバー Exchange使用を停止します。<br/><br/> **注:** 2013 Exchangeから 2016 Exchangeへの移行は簡単です。 2 つのバージョンはほぼ同じハードウェア要件を持ち、これらのバージョンは非常に互換性があります。 そのため、2013 年に購入したサーバーをExchangeし、2016 Exchangeインストールできます。 オンライン メールボックスの移動の場合、ほとんどのユーザーは、メールボックスがサーバーから移動され、2016 年に 2016 年に再構築された後に戻Exchangeされません。           |
|バージョンの共存  <br/> | ..に移行する場合。  <br/> **Exchange 2016:** Exchange 2016 は、2007 サーバーを含む組織Exchangeできません。 まず、Exchange 2010 または 2013 に移行する必要があります (Exchange 2013 を強く推奨します)、Exchange 2007 のすべてのサーバーを削除してから、Exchange 2016 に移行します。  <br/> **Exchange 2010 または Exchange 2013:** 2010 または Exchange 2013 Exchange 2007 組織にインストールExchangeできます。 これにより、2010 または 2013 Exchange 1 つ以上のサーバーをインストールし、移行を実行できます。  <br/> |
|サーバー ハードウェア  <br/> | サーバーのハードウェア要件が 2007 年Exchangeされています。 ハードウェアが互換性を持つかどうかを確認します。 詳細については、以下を参照してください。  <br/> [Exchange 2016 システム要件](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 システム要件](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 システム要件](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  Exchange のパフォーマンスが大幅に向上し、新しいサーバーの処理能力とストレージ容量が増加すると、同じ数のメールボックスをサポートするために必要なサーバー数が少ない可能性があります。  <br/> |
|オペレーティング システムのバージョン  <br/> | 各バージョンでサポートされるオペレーティング システムの最小バージョンは次のとおりです。  <br/> **Exchange 2016** - Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange 2010** - Windows Server 2008 SP2  <br/>  オペレーティング システムのサポートの詳細については、「サポートExchange[マトリックス」を参照してください](/Exchange/plan-and-deploy/supportability-matrix)。  <br/> |
|Active Directory フォレストの機能レベル  <br/> | 各バージョンでサポートされる Active Directory フォレストの最小機能レベルは次のとおりです。  <br/> **Exchange 2016 Windows** Server 2008 R2 SP1  <br/> **Exchange 2013 Windows** Server 2003  <br/> **Exchange 2010 Windows** Server 2003  <br/>  フォレストの機能レベルのサポートの詳細については、「サポートExchange[マトリックス」を参照してください](/Exchange/plan-and-deploy/supportability-matrix)。  <br/> |
|Officeのバージョン  <br/> | 各バージョンでサポートOfficeの最小バージョンは次のとおりです。  <br/> **Exchange 2016** - Office 2010 (最新の更新プログラム付き)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  クライアント サポートの詳細については、「サポートOfficeマトリックス」[をExchange参照してください](/Exchange/plan-and-deploy/supportability-matrix)。  <br/> |
   
#### <a name="how-do-i-migrate"></a>移行方法

メールをオンプレミスに保持することを決定した場合は、次のリソースを使用して移行に役立ちます。
  
- [Exchange展開アシスタント](/exchange/exchange-deployment-assistant)
    
- [2016 年 、2013 年、2010](/Exchange/plan-and-deploy/active-directory/ad-schema-changes)年の Active Directory スキーマの変更点Exchange [2016](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help)年[](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)
    
- 2016 年[2016](/Exchange/plan-and-deploy/system-requirements)Exchange [2013 、 2010](/exchange/exchange-2013-system-requirements-exchange-2013-help)年のシステム[要件](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141))
    
- [2016 年Exchange 2013](/Exchange/plan-and-deploy/prerequisites)年[、2010](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))年[の](/exchange/exchange-2013-prerequisites-exchange-2013-help)前提条件
    
## <a name="get-help"></a>ヘルプを参照する

移行する場合は、microsoft Microsoft 365 サービスを使用する資格FastTrackがあります。 FastTrack、ベスト プラクティス、ツール、およびリソースを提供して、移行を可能な限りシームレスMicrosoft 365作成します。 何より、サポート エンジニアは、計画と設計から最後のメールボックスの移行まで、移行について説明します。 詳細については、「Microsoft FastTrack」[を参照FastTrack。](https://fasttrack.microsoft.com/)
  
Microsoft 365 への移行中に問題が発生し、FastTrack を使用していない場合、または新しいバージョンの Exchange Server への移行を行う場合は、ここにお手伝いします。 使用できるリソースを次に示します。
  
- [テクニカル コミュニティ](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [カスタマー サポート](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>関連項目

[2007 年のサーバー Officeアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)