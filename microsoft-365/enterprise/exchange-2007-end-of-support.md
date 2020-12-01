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
description: Exchange Server 2007 のサポート終了後のオプションについて説明し、「Microsoft 365、Office 365、または Exchange 2016 への移行の計画」を開始します。
ms.openlocfilehash: 3f0a5c8ef9765a184358b932548eaa2ae7c59adc
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519847"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 のサポート終了ロードマップ

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Exchange Server 2007 は、2017年4月にサポート終了になりました。 Exchange 2007 から Microsoft 365、Office 365、または Exchange 2016 への移行を開始していない場合は、計画を開始する時間になります。
  
## <a name="what-does-end-of-support-mean"></a>*サポート終了の* 意味

Exchange Server は、ほぼすべての Microsoft 製品と同様に、新機能、バグ修正、セキュリティ修正プログラムなどを提供するためのライフサイクルを備えています。 このライフサイクルは通常、製品の最初のリリースから10年間続きます。 このライフサイクルの終了は、製品のサポート終了と呼ばれます。 Exchange 2007 は、2017年4月11日にサポートの終了に達したため、Microsoft は提供しなくなりました。
  
- 発生する可能性のある問題のテクニカルサポート。
    
- サーバーの安定性と有用性に影響を与える可能性がある問題について、バグ修正が行われます。
    
- セキュリティ侵害に対してサーバーが脆弱になる可能性がある脆弱性に対するセキュリティ修正。
    
- タイム ゾーンの更新。
    
Exchange 2007 のインストールは、サポート終了日後も引き続き実行されます。 ただし、新しい更新やサポートがないため、できるだけ早く Exchange 2007 から移行することを強くお勧めします。
  
サポートの終了間近にある Office 2007 サーバーの詳細については、「 [Plan your upgrade From office 2007 servers and products](upgrade-from-office-2007-servers-and-products.md)」を参照してください。
  
## <a name="what-are-my-options"></a>使用できるオプション

次の操作を行うことができます:
  
- Microsoft 365 に移行するには、一括移行、段階的な移行、またはハイブリッド移行を使用します。
    
- Exchange 2007 サーバーをオンプレミスサーバー上の新しいバージョンの Exchange に移行します。
    
次のセクションでは、それぞれのオプションについて詳しく説明します。
  
### <a name="migrate-to-microsoft-365"></a>Microsoft 365 に移行する

メールを Microsoft 365 に移行することは、Exchange 2007 の展開を廃止するのに役立つ最良かつ簡単な方法です。 Microsoft 365 への移行を使用すると、次のような、10年から始まるテクノロジから最先端の機能までの単一ホップを作成できます。
  
- 保持ポリシー、In-Place および訴訟ホールド、インプレース電子情報開示などのコンプライアンス機能
    
- Microsoft 365 グループ
    
- 優先受信トレイ
    
- MyAnalytics
    
- 電子メール、予定表、連絡先などへのプログラムによるアクセスを可能にする REST Api
    
また、Microsoft 365 は、最初に新しい機能とエクスペリエンスを取得するので、ユーザーは通常、すぐに使用を開始することができます。 そして、次のことについて心配する必要はありません。
  
- ハードウェアを購入および保守する。
    
- サーバーの発熱と冷却にお支払いください。
    
- 常に最新のセキュリティ、製品、タイムゾーンを更新します。
    
- コンプライアンス要件をサポートするためのストレージとソフトウェアの管理。
    
- 新しいバージョンの Exchange にアップグレードします。 Microsoft 365 では、常に最新バージョンの Exchange を使用しています。
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>Microsoft 365 に移行する方法

移行オプションはいくつかあります。 次の点を考慮する必要があります。

- 移動する必要がある座席またはメールボックスの数。
- 移行を最後に実行する時間。
- 移行中にオンプレミスのインストールと Microsoft 365 との間でシームレスに統合する必要があるかどうか。

次の表に、移行オプションと、使用する方法を決定する最も重要な要素を示します。
  

|**移行オプション**|**組織の規模**|**Duration**|
|:-----|:-----|:-----|
|カットオーバー移行  <br/> |座席数が150未満  <br/> |1週間以内  <br/> |
|段階的な移行  <br/> |150を超える座席  <br/> |数週間  <br/> |
|完全なハイブリッド移行  <br/> |数百から数千の座席  <br/> |数か月以上  <br/> |
   
次のセクションでは、これらの方法の概要について説明します。 詳細については、「 [移行パスの決定](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)」を参照してください。 
  
#### <a name="cutover-migration"></a>カットオーバー移行

カットオーバー移行では、すべてのメールボックス、配布グループ、連絡先などを、事前に指定した日時に Microsoft 365 に移行します。 移行が完了したら、オンプレミスの Exchange サーバーをシャットダウンし、Microsoft 365 のみの使用を開始します。
  
メールボックス数の少ない小規模な組織では、一括移行は非常に役立ち、Microsoft 365 にすばやくアクセスして、他の方法のいくつかの複雑な処理を行わないようにしたいと考えています。 ただし、1週間以内に完了する必要があり、ユーザーは Outlook プロファイルを再構成する必要があります。 カットオーバー移行では最大2000のメールボックスを処理できますが、最大150のメールボックスを移行する場合は、これを使用することを強くお勧めします。 さらに移行しようとすると、期限までにすべてのメールボックスを移行するのに時間がかかり、ユーザーが Outlook を再構成するのを支援する要求に IT サポートスタッフが圧倒される可能性があります。
  
一括移行の実行を検討している場合は、次の点を考慮する必要があります。
  
- Microsoft 365 は、TCP ポート443で Outlook Anywhere を使用して Exchange 2007 サーバーに接続する必要があります。
    
- すべてのオンプレミスメールボックスは、Microsoft 365 に移動されます。
    
- ユーザーのメールボックスに対する読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
    
- Microsoft 365 で使用する Exchange 2007 の承認済みドメインは、サービスの確認済みドメインとして追加する必要があります。
    
- 移行を開始してから、完了フェーズを開始するまでの間、Microsoft 365 は定期的に Microsoft 365 とオンプレミスのメールボックスを同期します。 これにより、オンプレミスのメールボックスに残った電子メールを気にすることなく、移行を完了できます。
    
- ユーザーは、Microsoft 365 アカウントの新しい一時パスワードを受け取ります。 メールボックスに初めてサインインするときには、パスワードを変更する必要があります。
    
- 移行するユーザーメールボックスごとに、Exchange Online を含む Microsoft 365 ライセンスが必要になります。
    
- ユーザーは、それぞれのデバイスに新しい Outlook プロファイルを設定して、電子メールをもう一度ダウンロードする必要があります。 Outlook がダウンロードするメールの量は異なる場合があります。 詳細については、「 [オフラインで保持するメールの量を変更する](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)」を参照してください。
    
カットオーバー移行の詳細については、以下を参照してください。
  
- [カットオーバーメール移行について知っておくべきこと](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [メールのカットオーバー移行を実行する](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>段階的な移行

段階的な移行では、数百または数千のメールボックスが Microsoft 365 に移行する必要があり、移行を完了するのに1週間以上かかる必要があります。また、共有の空き時間予定表情報などの高度なハイブリッド移行機能は必要ありません。
  
段階的な移行は、メールボックスを Microsoft 365 に移行するのに時間がかかるようにする必要があり、数週間以内に移行を完了することを計画している組織に適しています。 メールボックスはバッチ処理で移行できます。 移行するメールボックスの数と数は、指定した時間に制御します。 同じ部署のユーザーのメールボックスをバッチ処理することもできます。たとえば、すべてのユーザーが同時に移動されていることを確認します。 または、最新のバッチまでエグゼクティブメールボックスを残しておくこともできます。 カットオーバー移行の場合と同様に、ユーザーは Outlook プロファイルを再作成する必要があります。
  
段階的な移行を検討している場合は、次の点を考慮する必要があります。
  
- Microsoft 365 は、TCP ポート443で Outlook Anywhere を使用して、Exchange 2007 サーバーに接続する必要があります。
    
- ユーザーのメールボックスに対する読み取りアクセス権を持つオンプレミスの管理者アカウントが必要です。
    
- Microsoft 365 で使用する予定の Exchange 2007 承認済みドメインは、検証済みドメインとしてサービスに追加する必要があります。
    
- バッチで移行する予定のメールボックスごとに、完全な名前と電子メールアドレスを使用して CSV ファイルを作成する必要があります。 移行するメールボックスごとに新しいパスワードを指定して、そのパスワードを各ユーザーに送信する必要もあります。 ユーザーが新しい Microsoft 365 メールボックスに初めてサインインするときに、パスワードを変更するように求めるメッセージが表示されます。
    
- 移行バッチを開始してから、完了フェーズを開始するまでの間、Microsoft 365 は、バッチに含まれている Microsoft 365 とオンプレミスのメールボックスを定期的に同期します。 これにより、オンプレミスのメールボックスに残った電子メールを気にすることなく、移行を完了できます。
    
- 移行するユーザーメールボックスごとに、Exchange Online を含む Microsoft 365 ライセンスが必要になります。
    
- ユーザーは、それぞれのデバイスに新しい Outlook プロファイルを設定して、電子メールをもう一度ダウンロードする必要があります。 Outlook がダウンロードするメールの量は異なる場合があります。 詳細については、「 [オフラインで保持するメールの量を変更する](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)」を参照してください。
    
段階的な移行の詳細については、以下を参照してください。
  
- [段階的なメールの移行について知っておくべきこと](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [メールの段階的な移行を実行する](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>完全なハイブリッド

完全なハイブリッド移行では、組織に多数のメールボックスがあり、それらのメールボックスの一部またはすべてを Microsoft 365 に移行する必要があります。 通常、これらの移行は長期間になるため、ハイブリッド移行によって次のことが可能になります。
  
- オンプレミスのユーザーに、Microsoft 365 のユーザーの予定表の空き時間情報を表示します。その逆も同様です。
    
- オンプレミスと Microsoft 365 の両方の受信者が含まれる統合グローバルアドレス一覧を参照してください。
    
- オンプレミスであるか Microsoft 365 であるかに関係なく、すべてのユーザーの完全な Outlook 受信者プロパティを表示します。
    
- オンプレミスの Exchange サーバーと Microsoft 365 との間で、TLS と証明書を使用して電子メール通信をセキュリティで保護します。
    
- オンプレミスの Exchange サーバーと Microsoft 365 間で送信されたメッセージを内部として処理し、次のことを可能にします。
    
  - 内部メッセージを対象とするトランスポートおよびコンプライアンスエージェントにより、適切に評価および処理されます。
    
  - スパム対策フィルターをバイパスします。
    
完全なハイブリッド移行は、数か月以上のハイブリッド構成にとどまることが予想される組織に最適です。 このセクションで前述した機能に加えて、ディレクトリ同期、統合されたコンプライアンス機能、およびオンラインメールボックスの移動を使用して、Microsoft 365 との間でメールボックスを移動する機能を利用できるようになります。 Microsoft 365 は、オンプレミスの組織の拡張機能になります。
  
完全なハイブリッド移行の実行を検討している場合は、次の点を考慮する必要があります。
  
- 完全なハイブリッド移行は、すべての種類の組織には適していません。 完全なハイブリッド移行は複雑であるため、数百のメールボックスを使用している組織では、通常、1つの設定に必要な労力とコストを正当化する利点は得られません。 このことが組織のように聞こえる場合は、代わりに一括移行または段階的な移行を検討することをお勧めします。
    
- 「ハイブリッドサーバー」として機能するように、Exchange 2007 組織に少なくとも1つの Exchange 2013 サーバーを展開する必要があります。 このサーバーは、Exchange 2007 サーバーに代わって Microsoft 365 と通信します。
    
- Microsoft 365 は、TCP ポート443で Outlook Anywhere を使用して、"ハイブリッドサーバー" に接続する必要があります。
    
- オンプレミスの Active Directory サーバーと Microsoft 365 との間で Azure Active Directory (Azure AD) 接続を使用してディレクトリ同期をセットアップする必要があります。
    
- ユーザーは、ローカルネットワークにサインインしたときと同じユーザー名とパスワードを使用して、自分の Microsoft 365 メールボックスにサインインできます。 (この機能には、パスワード同期や Active Directory フェデレーションサービスを使用した Azure AD Connect が必要です。)
    
- 移行するユーザーメールボックスごとに、Exchange Online を含む Microsoft 365 ライセンスが必要になります。
    
- ユーザーは、多くのデバイスで新しい Outlook プロファイルを設定する必要はありませんが、一部の古い Android 電話機では新しいプロファイルが必要になることがあります。 ユーザーはメールを再度ダウンロードする必要はありません。
    
完全なハイブリッド移行を自分で行う場合は、移行に役立つ次のリソースを参照してください。
  
- [Exchange 展開アシスタント](https://aka.ms/exdeploy)
    
- [Exchange Server のハイブリッド展開](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)
    
- [ハイブリッド構成ウィザード](https://technet.microsoft.com/library/hh529921%28v=exchg.150%29.aspx)
    
- [ハイブリッド構成ウィザードに関する FAQ](https://technet.microsoft.com/library/mt488940%28v=exchg.150%29.aspx)
    
- [ハイブリッド展開の前提条件](https://technet.microsoft.com/library/hh534377%28v=exchg.150%29.aspx)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>新しいバージョンの Exchange Server に移行する

Microsoft 365 に移行することによって、最高の価値とユーザーの利便性を実現できると確信しています。 また、一部の組織ではメールをオンプレミスで保持する必要があることも理解しています。 これは、規制要件により、データが別の国にあるデータセンターに格納されていないこと、または類似していることが原因である可能性があります。 メールをオンプレミスで保持することを選択した場合は、exchange 2007 環境を Exchange 2010、Exchange 2013、または Exchange 2016 に移行できます。
  
Microsoft 365 に移行できない場合は、Exchange 2016 に移行することをお勧めします。 Exchange 2016 には、以前のリリースの Exchange のすべての機能が含まれています。 また、microsoft 365 で利用できる機能に最も近いものもありますが、一部の機能は Microsoft 365 でのみ利用可能です。 不足しているもののいくつかを確認してください。
  
|**Exchange リリース**|**機能**|
|:-----|:-----|
|Exchange 2010  <br/> | アクセス制御の Role-Based (Acl を使用しないアクセス許可)  <br/>  Outlook Web App メールボックス ポリシー  <br/>  組織間で空き時間情報を共有し、予定表を委任する機能  <br/> |
|Exchange 2013  <br/> | *Exchange 2010 の機能*  <br/>  サーバーの役割の数を3に減らしたシンプルなアーキテクチャ (メールボックス、クライアントアクセス、エッジトランスポート)  <br/>  機密情報を漏洩させないようにするデータ損失防止ポリシー (DLP)  <br/>  Outlook Web App の操作性の向上  <br/> |
|Exchange 2016  <br/> | *Exchange 2013 の機能*  <br/>  メールボックスとエッジトランスポートだけのサーバーの役割をさらに簡素化する  <br/>  SharePoint との統合と共に DLP が向上しました。  <br/>  データベースの復元性の向上  <br/>  オンラインドキュメントのコラボレーション |
   
#### <a name="which-version-should-i-migrate-to"></a>移行する必要があるのはどのバージョンですか?

最初に Exchange 2016 に移行することを前提とすることをお勧めします。 次に、以下の情報を使用して、前提条件を確認するか、Exchange 2016 を除外します。 何らかの理由で Exchange 2016 に移行できない場合は、Exchange 2013 で同じ手順を実行します。
  
|**考慮事項**|**詳細情報**|
|:-----|:-----|
|サポート終了日  <br/> | Exchange 2007 と同様に、Exchange の各バージョンには、サポート終了日が含まれています。  <br/> *Exchange 2010* 年1月2020  <br/> *Exchange 2013* -2023 年4月  <br/> *Exchange 2016* 年10月2025  <br/>  以前はサポートが終了してから、もう一度移行を実行する必要があります。<br/> |
|Exchange 2010 および2013への移行パス。  <br/> |ここでは、Exchange 2010 または Exchange 2013 に移行するための一般的なフェーズを示します。  <br/> -既存の Exchange 2007 組織に Exchange 2010 または2013をインストールします。 <br/>-サービスとその他のインフラストラクチャを Exchange 2010 または2013に移動します。<br/>-メールボックスとパブリックフォルダーを Exchange 2010 または2013に移動します。<br/>-残りの Exchange 2007 サーバーを使用停止にします。 |
|Exchange 2016 への移行パス  <br/> |ここでは、Exchange 2016 への移行の一般的なフェーズを示します。  <br/> -既存の Exchange 2007 組織に Exchange 2013 をインストールします。<br/>-サービスとその他のインフラストラクチャを Exchange 2013 に移動します。<br/>-メールボックスとパブリックフォルダーを Exchange 2013 に移動します。<br/>-残りの Exchange 2007 サーバーを使用停止にします。<br/>-既存の Exchange 2013 組織に Exchange 2016 をインストールします。<br/>-メールボックス、パブリックフォルダー、サービス、およびその他のインフラストラクチャを Exchange 2016 に移動します (順序は関係ありません)。 残りの Exchange 2013 サーバーを使用停止にします。<br/><br/> **注:** Exchange 2013 から Exchange 2016 への移行は簡単です。 2つのバージョンのハードウェア要件はほぼ同じで、これらのバージョンは非常に互換性があります。 そのため、Exchange 2013 用に購入したサーバーを再構築して、Exchange 2016 をインストールすることができます。 オンラインメールボックスの移動の場合、ユーザーのメールボックスがサーバーから移動された後、Exchange 2016 で再構築した後に、メールボックスがサーバーから移動されたことに気付かないこともありません。           |
|バージョンの共存  <br/> | 移行先  <br/> **Exchange 2016:** Exchange 2007 サーバーを含む組織に exchange 2016 をインストールすることはできません。 最初に Exchange 2010 または2013に移行する必要があります (Exchange 2013 を推奨)、すべての Exchange 2007 サーバーを削除して、Exchange 2016 に移行します。  <br/> **Exchange 2010 または exchange 2013:** 既存の Exchange 2007 組織に Exchange 2010 または Exchange 2013 をインストールすることができます。 これにより、1つ以上の Exchange 2010 または2013サーバーをインストールして、移行を実行することができます。  <br/> |
|サーバー ハードウェア  <br/> | サーバーハードウェア要件が Exchange 2007 から変更されました。 ハードウェアに互換性があることを確認してください。 詳細については、以下を参照してください。  <br/> [Exchange 2016 のシステム要件](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx) <br/> [Exchange 2013 のシステム要件](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx) <br/> [Exchange 2010 のシステム要件](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx) <br/>  Exchange のパフォーマンスが大幅に向上し、新しいサーバーでのコンピューティングの処理能力と記憶域容量が増加したことにより、同じ数のメールボックスをサポートするために必要なサーバー数が少なくなる可能性があることがわかります。  <br/> |
|オペレーティング システムのバージョン  <br/> | 各バージョンでサポートされているオペレーティングシステムの最小バージョンは次のとおりです。  <br/> **Exchange 2016** -Windows Server 2012  <br/> **Exchange 2013** -Windows Server 2008 R2 SP1  <br/> **Exchange 2010** -Windows SERVER 2008 SP2  <br/>  オペレーティングシステムのサポートの詳細については、「 [Exchange サポートのマトリックス](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)」を参照してください。  <br/> |
|Active Directory フォレストの機能レベル  <br/> | 各バージョンのサポートされている最小 Active Directory フォレストの機能レベルは次のとおりです。  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  フォレストの機能レベルのサポートの詳細については、「 [Exchange サポートのマトリックス](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)」を参照してください。  <br/> |
|Office クライアントのバージョン  <br/> | 各バージョンでサポートされている最小 Office クライアントバージョンは次のとおりです。  <br/> **Exchange 2016** -Office 2010 (最新の更新プログラム)  <br/> **Exchange 2013** -OFFICE 2007 SP3  <br/> **Exchange 2010** -Office 2003  <br/>  Office クライアントサポートの詳細については、「 [Exchange サポートのマトリックス](https://technet.microsoft.com/library/ff728623%28v=exchg.150%29.aspx)」を参照してください。  <br/> |
   
#### <a name="how-do-i-migrate"></a>移行方法

メールをオンプレミスで保持することにした場合は、次のリソースを使用して移行に役立てることができます。
  
- [Exchange 展開アシスタント](https://aka.ms/exdeploy)
    
- Exchange [2016](https://technet.microsoft.com/library/bb738144%28v=exchg.160%29.aspx)、 [2013](https://technet.microsoft.com/library/bb738144%28v=exchg.150%29.aspx)、 [2010](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401)の Active Directory スキーマの変更
    
- Exchange [2016](https://technet.microsoft.com/library/aa996719%28v=exchg.160%29.aspx)、 [2013](https://technet.microsoft.com/library/aa996719%28v=exchg.150%29.aspx)、 [2010](https://technet.microsoft.com/library/aa996719%28v=exchg.141%29.aspx)のシステム要件
    
- Exchange [2016](https://technet.microsoft.com/library/bb691354%28v=exchg.160%29.aspx)、 [2013](https://technet.microsoft.com/library/bb691354%28v=exchg.150%29.aspx)、 [2010](https://technet.microsoft.com/library/bb691354%28v=exchg.141%29.aspx)の前提条件
    
## <a name="get-help"></a>ヘルプを参照する

Microsoft 365 に移行している場合は、Microsoft FastTrack サービスを使用することができます。 FastTrack は、Microsoft 365 への移行を可能な限りシームレスに行うためのベストプラクティス、ツール、およびリソースを提供します。 どのような場合も、最新のメールボックスを移行するすべての方法を計画し、設計することによって、サポートエンジニアから移行を進めていくことができます。 FastTrack の詳細については、「 [Microsoft FastTrack](https://fasttrack.microsoft.com/)」を参照してください。
  
Microsoft 365 への移行中に、FastTrack または新しいバージョンの Exchange Server への移行を使用していないときに問題が発生した場合は、こちらを参照してください。 使用できるリソースを次に示します。
  
- [テクニカル コミュニティ](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [カスタマー サポート](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>関連トピック

[Office 2007 サーバーおよびクライアントのアップグレードに役立つリソース](upgrade-from-office-2007-servers-and-products.md)
