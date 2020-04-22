---
title: 従来の電子情報開示ツールの廃止
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Exchange Online のインプレース電子情報開示とインプレース保持 (および対応する PowerShell コマンドレット) は、2020の前半で廃止されます。 検索メールボックスコマンドレットと Advanced eDiscovery v 1.0 も、同じ期間内に廃止されます。
ms.openlocfilehash: 23ff43dfc2131073425deb947aee41662e30616a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635571"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>従来の電子情報開示ツールの廃止

> [!IMPORTANT]
> Microsoft は、衛生衛生状況を評価しており、お客様に対する影響について理解しています。 Sdl は、強力なパートナーと責任を持つグローバル市民を求めています。 お客様が直面している多くの状況の1つを簡単にするために、この記事で説明した従来の電子情報開示ツールを3か月で延期する予定です。 **更新された退職日は次のように反映されます。**

長年、Microsoft では、Exchange Online からの電子メールコンテンツの検索、プレビュー、およびエクスポートを可能にする電子情報開示ツールを提供しています。 ただし、これらのツールでは、SharePoint Online や Microsoft 365 グループなど、他の Microsoft 365 services の Exchange 以外のコンテンツを効率的に検索する方法は提供されなくなりました。 このことを説明するために、Microsoft は、さまざまな Microsoft 365 コンテンツを検索するのに役立つその他の電子情報開示ツールを提供しています。 また、マイクロソフトは、 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)で最新の強力な電子情報開示機能を組み込むために努力してきました。 これにより、組織は、Exchange Online などの多くの Microsoft 365 サービスにわたって、法的、社内、およびその他のコンテンツに関するドキュメント要求に対応することができます。

この新しい電子情報開示機能の結果として、Microsoft 365 コンプライアンスセンターでは、Exchange Online および Microsoft 365 での電子メールコンテンツの検索に関連する以下の電子情報開示関連の機能を廃止しています。

- Exchange 管理センターの[インプレース電子情報開示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- インプレース電子情報開示とインプレース保持をサポートする Exchange Online の PowerShell コマンドレット (これらのコマンドレットは、*get-mailboxsearch*コマンドレットと総称して識別されます)。 これには、次のコマンドレットが含まれます。

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-mailboxsearch)

   > [!NOTE]
   > [Get-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-mailboxsearch)および[get-mailboxsearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/remove-mailboxsearch)コマンドレットは、他の * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * * を破棄した後で使用可能に ただし、特定の日付 (後述) の Microsoft サポートは、これら2つのコマンドレットをサポートしなくなります。

- Exchange Online PowerShell の [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/search-mailbox?view=exchange-ps) コマンドレット。

- Exchange Web Services API での次の操作。

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- Office [365 Advanced ediscovery v 1.0](office-365-advanced-ediscovery.md)。これは、Office 365 セキュリティ & コンプライアンスセンターの主要な電子情報開示ケースによってアクセスされる、高度な電子情報開示の最初のバージョンです。 高度な電子情報開示 v2.0 の廃止は、コア電子情報開示ケースの作成と管理の能力に影響を与えません。

> [!NOTE]
> 廃止される電子情報開示の機能は、クラウドベースのバージョンの Microsoft 365 および Office 365 にのみ適用されます。 オンプレミスバージョンの Exchange と SharePoint の電子情報開示機能は、今後の通知まで引き続きサポートされます。

この記事の以下のセクションでは、廃止される各機能についてのガイダンスを提供します。 この情報は、廃止ツールの代わりに使用できるタイムラインおよび代替ツールを含みます。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Exchange 管理センターでのインプレース電子情報開示とインプレース保持 

2017年7月1日の元のアナウンスによると、Exchange 管理センター (EAC) のインプレース電子情報開示 & 保持機能は廃止されています。 インプレース電子情報開示 & は、Exchange Online からコンテンツを検索、保持、およびエクスポートするための EAC のページが含まれています。 インプレース電子情報開示では、検索結果を証拠開示用メールボックスにコピーして、自分または他の電子情報開示マネージャーがコンテンツをレビューし、法律、規制、およびパブリック要求に対して使用できるようにすることもできます。

これらのすべての機能 (検索結果を証拠開示用メールボックスにコピーする場合を除く) は、 [microsoft 365 コンプライアンスセンター](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)のコンテンツ検索、電子情報開示、および高度な電子情報開示ツールで利用できるようになりました (強化された機能、信頼性、および幅広い microsoft 365 サービスのサポート)。 他の電子情報開示ツールへの移行を支援するために、以下の表に、インプレース電子情報開示とインプレース保持の代わりに使用できるツールを示します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 と Microsoft 365 エンタープライズ組織

- Office 365 および Microsoft 365 エデュケーション組織

- Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline-for-retirement"></a>定年後のタイムライン

- 2020年7月1日: 新しい検索と保持を作成することはできませんが、既存の検索の実行、編集、および削除は、自分の責任で行うことができます。 Microsoft サポートは、EAC でのインプレース電子情報開示 & 保持を中止します。

- 2020年10月1日: インプレース電子情報開示 & は、EAC の機能を読み取り専用モードで保持します。 これにより、可能な操作は、既存の検索および保留リストの削除のみになります。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。

<table>
<thead>
<tr class="header">
<th><strong>機能</strong></th>
<th><strong>代替ツール</strong></th>
<th><strong>コメント</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>法的な目的のための検索、エクスポート、保持</td>
<td>Microsoft 365 コンプライアンスセンターのコア電子情報開示ケース </td>
<td><p>コア電子情報開示ケースの機能を使用すると、インプレース電子情報開示とインプレース保持に機能パリティが提供されます。 エクスポートできるものには、次のようなものがあります。</p>
<ul>
<li>
<p>数百万の場所への検索を拡大/縮小</p>
</li>
<li>
<p>コンテンツの検索、エクスポート、および配置の信頼性が向上します。</p>
</li>
<li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、Office 365 アプリケーションに格納されているその他のコンテンツのコンテンツを検索する</p></li></ul>
<p>詳細については、「 <a href="https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations">Office 365 で法的調査を管理</a>する」を参照してください。</td>
</tr>
<tr class="even">
<td>保持の目的で保持</td>
<td>Microsoft 365 コンプライアンスセンターのアイテム保持ポリシー</td>
<td><p>保持ポリシーを使用してコンテンツを保持できます。必要に応じて、保存期間の期限が切れた後にアイテムを削除します。 その他の機能は次のとおりです。</p>
<ul>
<li>
<p>組織全体へのポリシーの適用 </p>
</li><li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Office 365 グループなどの特定のコンテンツの場所へのポリシーの適用</p></li>
<li>
<p>特定のユーザーへのポリシーの適用</p></li></ul>
<p>詳細については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies">アイテム保持ポリシーの概要</a>」を参照してください。</td>
</tr>
<tr class="odd">
<td>レビューのために電子メール検索結果を証拠開示用メールボックスにコピーする</td><td>上級電子情報開示の設定を確認する v2.0 v 2.0</td>
<td><p>Microsoft 365 のコンテンツを確認するのは、これよりも簡単ではありません。 レビューセットには、次のような時間とデータを減らすために役立つさまざまな機能があります。</p>
<ul>
<li><p>クイック検索クエリを実行して、レビューセット内のコンテンツをフィルター処理する</p></li>
<li><p>レビューセットのコンテンツを分析する。これには、電子メールスレッド処理、ほぼ重複した検出、テーマの分析、および予測コーディングが含まれます。</p></li>
<li><p>レビュー セット内のドキュメントをタグ付けする</p></li>
<li><p>弁護士クライアント権限の内容を識別するのに役立つ提案のタグ付け</p></li></ul>
<p>詳細については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</p>
<p>
<p>または、検索結果を PST ファイルにエクスポートし、Microsoft 365 インポートサービスを使用して Pst を探索メールボックスにインポートすることもできます。 詳細な手順については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">ネットワークアップロードを使用して PST ファイルを Office 365 にインポートする</a>」を参照してください。
</tr>
<tr class=even>
  <td>あるメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールにアクセスできるようにする (従業員が組織を離れたときに、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など) には、元従業員のメールボックスにアクセスするためのアクセス許可を割り当てることをお勧めします。 そのため、メールボックスアイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーするのではなく、移動元のメールボックスにアクセスするためのユーザー権限のみを割り当てます。</td>
  
  </tr>
<tr class="odd">
<td>回復可能なアイテムフォルダーからアイテムを復元する</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/mailboxes/Restore-RecoverableItems">復元-回復した Ableitems</td>
  <td>アイテムの削除済みアイテムの保存期間が期限切れになっていない限り、メールボックス内の完全に削除されたアイテム (<i>回復可能な</i>アイテムとも呼ばれる) を復元することができます。 詳細については、「 <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Online の回復可能なアイテムフォルダー</a>」を参照してください。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>インプレース電子情報開示とインプレース ホールドに関するよくある質問

**EAC のインプレース電子情報開示 & 保持のコピー検索結果機能を使用して、弁護士によるレビューのために検索結果を証拠開示用メールボックスにコピーします。現在、どのようなオプションがありますか?**

現在、この機能をレプリケートする方法は2つあります。 最初に、 [Advanced eDiscovery v2.0 のレビューセット](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)を使用します。 レビューセットには、ドキュメントの高速検索、タグ付け、電子メールのスレッド処理、グループの複製、テーマの分析、予測コーディングなど、従来のレビューツールで提供されている機能の多くがあります。 引き続き証拠開示用メールボックスをレビュー用に使用する場合、2番目のオプションは、Microsoft コンプライアンスセンターの[pst インポート機能](use-network-upload-to-import-pst-files.md)を使用して、検索結果を pst ファイルにエクスポートし、その pst ファイルを探索メールボックスにインポートすることです。

**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御するにはどうすればよいですか?**

また、Microsoft 365 コンプライアンスセンターは、[コンプライアンスの境界](set-up-compliance-boundaries.md)を使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。 コンプライアンスの境界は、地域の boarders を尊重するために必要とされる政府機関または多国籍企業内にとどまる必要がある政府機関にとって便利です。

**現在の検索と保持を Microsoft 365 コンプライアンスセンターに移動するにはどうすればよいですか?**

PowerShell を使用して、インプレース電子情報開示検索とホールドを EAC から移行することができます。 手順については、「 [Migrate 検索と保持を EAC から Microsoft 365 コンプライアンスセンターに移行する」を](https://go.microsoft.com/fwlink/?linkid=2114224)参照してください。

## <a name="-mailboxsearch-cmdlets"></a>\*-Get-mailboxsearch コマンドレット

Exchange 管理センターで2017年7月1日に発表された元の通知に従って、インプレース電子情報開示 & は機能を保持し、 ** \*get-mailboxsearch**コマンドレットは廃止されます。 これらのコマンドレットを使用すると、ユーザーは法律、規制、およびパブリックの要求について、メールボックスのコンテンツを検索、保持、エクスポートすることができます。

これらの機能は、パフォーマンスとスケーラビリティが向上した[<span class="underline">Microsoft 365 コンプライアンスセンター</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center)および Office 365 Security & コンプライアンスセンターの PowerShell で利用できるようになったため、これらの強化されたコマンドレットを使用する必要があります。 これらのコマンドレットには、 [<span class="underline"> \*-get-compliancecase</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase)、 [<span class="underline"> \*-new-compliancesearch</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch)、 [<span class="underline"> \*-CaseHoldPolicy</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy)、 [<span class="underline"> \*-new-caseholdrule</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule)、および[<span class="underline"> \*-new-compliancesearchaction</span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction)があります。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 と Microsoft 365 エンタープライズ組織

- Office 365 および Microsoft 365 エデュケーション組織

- Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020年7月1日: **get-mailboxsearch**を使用してインプレース電子情報開示検索とインプレース保持を新たに作成することはできませんが、コマンドレットを使用して、既存の検索を実行、編集、および削除することができます。 Microsoft サポートでは、これらの種類の検索と保留リストのサポートが提供されなくなりました。

- 2020年10月1日: 前述したように、インプレース電子情報開示 & は EAC の機能を読み取り専用モードで保持します。 これはまた、 **get-mailboxsearch**、 **get-mailboxsearch**、または**get-mailboxsearch**コマンドレットを使用できないことを意味します。 既存の検索と保持を取得して削除することはできません。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。

<table>
<thead>
<tr class="header">
<th><strong>機能</strong></th>
<th><strong>代替ツール</strong></th>
<th><strong>コメント</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>検索とエクスポート</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch"><span class="underline">*-New-compliancesearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>New-compliancesearch および New-compliancesearchaction コマンドレットは、コンテンツの検索とエクスポートを支援するために連携しています。 <strong>新しい検索</strong><strong>を作成</strong>し、 <strong>new-compliancesearch</strong>コマンドレットを使用して検索の推定値を表示することができます。 その後、 <strong>new-compliancesearchaction</strong>コマンドレットを使用して、検索結果をエクスポートできます。 引き続き、Microsoft 365 コンプライアンスセンターのコア電子情報開示ツールを使用して、それらの検索結果をローカルコンピューターにダウンロードする必要があります。</p>
<p>
<p><strong>注:</strong>これらのコマンドレットを使用して、コア電子情報開示ケースに関連付けられていない検索を作成すると、これらの検索は Microsoft 365 コンプライアンスセンターの [<strong>コンテンツ検索</strong>] ページに配置されます。</p></td>
</tr>
<tr class="even">
<td>メールボックス内のコンテンツを保持する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-caseholdrule"><span class="underline">*-New-caseholdrule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-ediscovery/get-compliancecase"><span class="underline">*-Get-compliancecase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 コンプライアンスセンターのホールドは、Get-compliancecase に関連付けられている必要があります。 最初に、コンプライアンスケースを作成し、CaseHoldPolicy と New-caseholdrule を作成します。</p>
<p><strong>注:</strong>New-caseholdrule を作成せずに CaseHoldPolicy を作成すると、New-caseholdrule が作成されて CaseHoldPolicy に関連付けられるまで、保留が操作不能になります。 詳細については、コマンドレットのドキュメントを参照してください。</p></td>
</tr>
<tr class="odd">
<td>検索結果を探索メールボックスにコピーする</td>
<td>なし</td>
<td>この機能は、Microsoft 365 のすべてのサービスへのアクセスを提供しないので、直接交換することはできません。 代替ソリューションについては、以下の FAQ を参照してください。</td>
</tr>
  <tr class=even>
  <td>あるメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールにアクセスできるようにする (従業員が組織を離れたときに、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など) には、元従業員のメールボックスにアクセスするためのアクセス許可を割り当てることをお勧めします。 そのため、メールボックスアイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーするのではなく、移動元のメールボックスにアクセスするためのユーザー権限のみを割り当てます。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>Get-mailboxsearch コマンドレットについて**の**faq

**コピー検索を使用して、他の電子情報開示や法的調査を目的とした電子メールメッセージまたはインスタントメッセージをエクスポートします。これらのコマンドレットが廃止された後に、他にどのようなオプションがありますか?**

[<span class="underline">Microsoft Graph api</span>](https://developer.microsoft.com/en-us/graph)には、 ** \*get-mailboxsearch**コマンドレットを使用するよりも復元性と拡張性が高いため、分析用のデータを抽出するためのさまざまな方法が用意されています。

**Microsoft 365 コンプライアンスセンターに、検索と保持を移行する方法を教えてください。**

PowerShell スクリプトを使用すると、Exchange 管理センターからインプレース電子情報開示の検索と保持を移行することができます。 詳細については、「 [Microsoft 365 コンプライアンスセンターへの従来の電子情報開示検索と保持の移行](migrate-legacy-eDiscovery-searches-and-holds.md)」を参照してください。

**コマンドレットが廃止された後でも、検索を削除または取得することはできますか?**

はい。検索を作成および変更する機能を削除していますが、さらに通知されるまで**get-mailboxsearch**を使用して、 **get-mailboxsearch を削除**することもできます。 ただし、これらのコマンドレットを使用することは、退職後にお客様の責任があります。

## <a name="search-mailbox-cmdlet"></a>検索-メールボックスコマンドレット

Exchange Online PowerShell の**Search メールボックス**コマンドレットは、2018で開始されるコマンドレットの出力で、最初に通知されたとおりに廃止されています。 最初は、**検索-メールボックス**コマンドレットを使用して、ユーザーのメールボックスを検索し、悪意のあるコンテンツを削除しました。 コンテンツを検索して削除するには、Office 365 セキュリティ & コンプライアンスセンターの PowerShell で**new-compliancesearch**および**new-compliancesearchaction**コマンドレットの使用を開始することをお勧めします。 組み込みのセキュリティ機能については、 [<span class="underline">microsoft 365 のセキュリティ機能</span>](https://docs.microsoft.com/microsoft-365/security/)により、電子メールやその他の多くの microsoft サービスに対する堅牢な脅威保護が提供されます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 と Microsoft 365 エンタープライズ組織

- Office 365 および Microsoft 365 エデュケーション組織

- Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

-  2020年7月1日:**検索-メールボックス**コマンドレットが使用できなくなり、Microsoft サポートからサポートが提供されなくなります。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。

<table>
<thead>
<tr class="header">
<th><strong>機能</strong></th>
<th><strong>代替ツール</strong></th>
<th><strong>コメント</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>メールボックスを検索する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-New-compliancesearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></a></p></td>
<td><p>New-compliancesearch および New-compliancesearchaction コマンドレットは、コンテンツの検索とエクスポートを支援するために連携しています。 <strong>新しい検索</strong><strong>を作成</strong>し、 <strong>new-compliancesearch</strong>コマンドレットを使用して検索の推定値を表示することができます。 その後、 <strong>new-compliancesearchaction</strong>コマンドを使用して検索結果をエクスポートできます。 引き続き、Microsoft 365 コンプライアンスセンターのコア電子情報開示ツールを使用して、それらの検索結果をローカルコンピューターにダウンロードする必要があります。</p></p>
</td>
</tr>
<tr class="even">
<td>メールボックスからメッセージを削除する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearch?view=exchange-ps"><span class="underline">*-New-compliancesearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/get-compliancesearchaction?view=exchange-ps"><span class="underline">*-New-compliancesearchaction</span></a></p>
<p></p></td>
<td><p>New-compliancesearch および New-compliancesearchaction コマンドレットは、コンテンツの検索と削除を支援するために連携しています。 <strong>New-compliancesearch</strong>および<strong>new-compliancesearch</strong>コマンドレットを使用して検索を作成して実行することができます。その後、 <strong>new-compliancesearchaction</strong>コマンドを使用してコンテンツを削除できます。 詳細については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">メッセージを検索して削除する</span></a>」を参照してください。</p>
</td>
</tr>
<tr class="odd">
<td>メールボックスからバルクメールを削除する</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></p>
<p></p></td>
<td><p>管理者は、ユーザーのアーカイブメールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブポリシーと削除ポリシーを作成できます。</p>
</td>
</tr>
<tr class="even">
<td>検索結果を探索メールボックスにコピーする</td>
<td> </td>
<td>この機能は、Microsoft 365 のすべてのサービスへのアクセスを提供しないので、直接交換することはできません。 代替ソリューションについては、「 <strong>get-mailboxsearch コマンドレット</strong>」セクションの faq を参照してください。 </td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web サービス API の操作

Exchange Web サービス API のこれらの操作は、exchange 管理センターのインプレース電子情報開示 & 保持機能、および** \*** exchange Online PowerShell の get-mailboxsearch コマンドレットで使用されます。 また、他の従来の電子情報開示ツールを撤去する際にも廃止されます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 と Microsoft 365 エンタープライズ組織

- Office 365 および Microsoft 365 エデュケーション組織

- Office 365 および Microsoft 365 Government 組織。これには GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020年7月1日: GetSearchableMailboxes ボックス、Searchemail メールボックス、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作を使用できなくなり、Microsoft サポートからサポートが提供されなくなります。

## <a name="advanced-ediscovery-v10"></a>高度な電子情報開示 v2.0 v 1.0

Advanced eDiscovery v2.0 は、[ **Advanced ediscovery に切り替え**] をクリックすることで、コア電子情報開示のケースで利用可能なアドバンスト ediscovery のバージョンで、廃止される予定です。 この機能は、Microsoft 365 コンプライアンスセンターの新しい[高度な電子情報開示ソリューション](https://aka.ms/edisco)に置き換えられました。

組織が Advanced eDiscovery v2.0 を使用しているかどうかを判断するには、次のようにします。

1. [Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)に移動します。

2. セキュリティ & コンプライアンスセンターの左側のナビゲーションウィンドウで、[電子情報開示 **> 電子**情報開示] をクリックし、コア電子情報開示ケースを開きます。

3. [**高度な電子情報開示に切り替え**] ボタンが表示されている場合は、それをクリックすると、[advanced ediscovery] の1.0 バージョンに移動します。これは廃止されています。 コア電子情報開示でケースを作成して管理する機能は影響を受けません。 高度な電子情報開示のサポート案件データを追加および分析する機能 ([ **Advanced ediscovery への切り替え**] をクリックする) は廃止されています。

Microsoft 365 の新しい高度な電子情報開示ソリューション (*上級電子情報開示*v2.0 とも呼ばれる) は、元のソリューションのすべての機能を提供していますが、他の Microsoft 365 サービスのコンテンツを特定し、そのコンテンツを収集して、レビュー担当者が fast search クエリ、タグ付け、および分析機能を利用して関連するドキュメントを選別できる 上級電子情報開示では、Microsoft および Microsoft 以外のファイルの種類の処理機能とネイティブビューアーが向上しています。[ここ](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20)では、ファイルの種類の完全なリストと、サポートされているメタデータフィールドについて[説明します](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。 また、新しい高度な電子情報開示ソリューションは、強力な電子情報開示ケース内で、さまざまなサービスのコンテンツに保持を適用したり、保留リストのユーザーに通知したり、保管担当者応答を追跡したりする強力な保管担当者ホールド管理機能を提供します。

Advanced eDiscovery v2.0 にアクセスするには、次のようにします。

1. [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com)に移動します。

2. Microsoft 365 コンプライアンスセンターの左側のナビゲーションウィンドウで、[**すべて表示**] をクリックし、[**電子情報開示 > 詳細**] をクリックします。

現時点では、新しい高度な電子情報開示の機能への電子情報開示ワークフローの移行を開始することをお勧めします。 既存のケースでは引き続き Advanced eDiscovery v2.0 にアクセスできますが、Microsoft サポートでは、2020年10月1日以降のサポートは提供されません。 詳細については、次のタイムラインを参照してください。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 と Microsoft 365 エンタープライズ組織

- Office 365 および Microsoft 365 エデュケーション組織

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020年7月1日: 新しい Advanced eDiscovery v2.0 のケースを作成することはできません。

- 2020年10月1日: 新しいデータ (高度な電子情報開示の検索結果を準備する) をいつでも追加することはできません。 既存のケースでは、ユーザー自身のリスクで引き続きデータを操作できます。 Microsoft サポートからサポートが提供されなくなります。 

### <a name="alternative-tools"></a>代替ツール

Microsoft 365 コンプライアンスセンターの[高度な電子情報開示ソリューション](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20)。