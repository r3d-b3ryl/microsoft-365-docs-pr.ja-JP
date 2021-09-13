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
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: In-Placeの電子情報開示とIn-Placeホールド (および対応する PowerShell コマンドレット Exchange Online) は、2020 年前半に廃止されます。 また、Search-Mailbox v1.0 Advanced eDiscoveryおよび v1.0 も同じ期間に廃止されます。
ms.openlocfilehash: 16a43122ce16a134a6068f78dadea02ac8605625
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59179943"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>従来の電子情報開示ツールの廃止

> [!IMPORTANT]
> この記事で説明する従来の電子情報開示ツールの機能は、Microsoft 365 サービスから削除されたか、まだ使用できますが、サポートされなくなりました。 引き続き使用可能な機能は、予告なしに削除される可能性があります。 これらのレガシ ツールを引き続き使用している場合は、Microsoft 365 コンプライアンス センター またはこの記事で説明する代替手段の 1 つで、電子情報開示ツールへの移行を検討してください。

長年にわたり、Microsoft は電子情報開示ツールを提供し、電子情報開示ツールを使用して、電子メール コンテンツを検索、プレビュー、およびエクスポートExchange Online。 ただし、これらのツールは、Exchange Online や Microsoft 365 グループなどの他の SharePoint Microsoft 365 サービスで非 Exchange コンテンツを検索する効果的な方法を提供しなくなりました。 この問題に対処するために、Microsoft はさまざまなコンテンツを検索するのに役立つその他の電子情報開示Microsoft 365しています。 また、最新かつ強力な電子情報開示機能を最新の電子情報開示機能に組み込む[Microsoft 365 コンプライアンス センター。](https://compliance.microsoft.com) これにより、組織は、コンテンツに関する法的、内部的、その他のドキュメント要求に、Microsoft 365サービスを含む多くのExchange Online。

Microsoft 365 コンプライアンス センター でこの新しく改善された電子情報開示機能の結果、Exchange Online および Microsoft 365 の電子メール コンテンツの検索に関連する次の電子情報開示関連の機能が廃止されました。

- Exchange 管理センターの[インプレース電子情報開示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- 電子Exchange Onlineおよび In-Place 保持をサポートする power In-Place Shell コマンドレット (これらのコマンドレットは、 **-MailboxSearch* コマンドレットとしてまとめて識別されます)。 これには、次のコマンドレットが含まれます。

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch)コマンドレットと[Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch)コマンドレットは、他の ****-MailboxSearch*** コマンドレットが廃止された後に使用できます。 ただし、特定の日付 (以下に引用) が終了すると、Microsoft サポートはこれら 2 つのコマンドレットをサポートしなくなりました。

- Exchange Online PowerShell の [Search-Mailbox](/powershell/module/exchange/search-mailbox) コマンドレット。

- Exchange Web Services API での次の操作。

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md)は、Advanced eDiscovery の Core 電子情報開示ケースを通じてアクセスされる最初のバージョンMicrosoft 365 コンプライアンス センター。 v1.0 のAdvanced eDiscoveryは、コア電子情報開示ケースを作成および管理する機能には影響を与えかねない。

> [!NOTE]
> 廃止される電子情報開示機能は、クラウド ベースのバージョンの Microsoft 365およびOffice 365。 オンプレミスバージョンの電子情報開示機能は、ExchangeおよびSharePointまで引き続きサポートされます。

この記事の以下のセクションでは、廃止される各機能に関するガイダンスを提供します。 この情報には、廃止されたツールの代わりに使用できるタイムラインや代替ツールが含まれています。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place管理センターIn-Place電子情報開示とExchange保持 

2017 年 7 月 1 日の当初の発表と同様に、In-Place 管理センター (EAC) の Exchange In-Place 電子情報開示 & 保留機能は廃止されます。 EAC In-Place [&保持] ページでは、コンテンツを検索、保持、およびエクスポートExchange Online。 In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、ユーザーまたは他の電子情報開示管理者がコンテンツを確認し、法的、規制、およびパブリック要求に対して利用可能にできます。

これらの機能 (検索結果を探索メールボックスにコピーする場合を除く) はすべて[、Microsoft 365 コンプライアンス センター](./microsoft-365-compliance-center.md)のコンテンツ検索、電子情報開示、および Advanced eDiscovery ツールで利用できます (機能、信頼性、および幅広い Microsoft 365 サービスのサポートが強化されています)、できるだけ早くこれらのツールの使用を開始することをお勧めします。 これらの他の電子情報開示ツールへの移行を支援するために、以下の表に、電子情報開示と電子情報開示の保持ではなくIn-PlaceツールIn-Place示します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365およびMicrosoft 365 Enterprise組織

- Office 365およびMicrosoft 365 Education組織

- Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。

- Office 365 Germany

### <a name="timeline-for-retirement"></a>退職のタイムライン

- 2020 年 7 月 1 日: 新しい検索と保留リストを作成できますが、既存の検索の実行、編集、および削除は、自分のリスクで行います。 Microsoft サポートは、EAC In-Place保持&電子情報開示を使用しなくなりました。

- 2020 年 10 月 1 日: In-Place電子情報開示 & EAC の保持機能は、読み取り専用モードになります。 これにより、可能な操作は、既存の検索および保留リストの削除のみになります。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換える他のツールについて説明します。

<table>
<thead>
<tr class="header">
<th>機能</th>
<th>代替ツール</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>法的な目的で検索、エクスポート、ホールドする</td>
<td>電子情報開示のコア ケース (Microsoft 365 コンプライアンス センター </td>
<td><p>コアの電子情報開示ケースの機能を使用すると、電子情報開示と保留リストのIn-PlaceパリティIn-Placeします。 エクスポートできるものには、次のようなものがあります。</p>
<ul>
<li>
<p>検索は数百万の場所に拡大縮小されます。</p>
</li>
<li>
<p>コンテンツの検索、エクスポート、および保留に関する信頼性の向上</p>
</li>
<li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、Office 365 アプリケーションに保存されている他のコンテンツの検索</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保持の目的で保持する</td>
<td>アイテム保持ポリシーのMicrosoft 365 コンプライアンス センター</td>
<td><p>アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて保持期間が経過した後に削除できます。 その他の機能は次のとおりです。</p>
<ul>
<li>
<p>組織全体にポリシーを適用する </p>
</li><li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Office 365 グループなどの特定のコンテンツの場所にポリシーを適用する</p></li>
<li>
<p>特定のユーザーにポリシーを適用する</p></li></ul>
<p>詳細については、「アイテム保持ポリシー <a href="/microsoft-365/compliance/retention-policies"> と保持ラベルについて」を参照してください</a>。</td>
</tr>
<tr class="odd">
<td>確認のために電子メール検索結果を探索メールボックスにコピーする</td><td>v2.0 でAdvanced eDiscoveryを確認する</td>
<td><p>サイト内のコンテンツMicrosoft 365簡単に確認できます。 レビュー セットには、次を含む、レビューに必要な時間とデータの削減に役立つ多くの機能があります。</p>
<ul>
<li><p>レビュー セットで高速検索クエリを実行し、コンテンツをフィルター処理する</p></li>
<li><p>レビュー セット内のコンテンツを分析する。これには、電子メール スレッド、重複に近い検出、テーマ分析、予測コーディングが含まれます。</p></li>
<li><p>レビュー セット内のドキュメントをタグ付けする</p></li>
<li><p>弁護士クライアント特権コンテンツの識別に役立つタグ付け提案</p></li></ul>
<p>詳細については、「<a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</p>
<p>
<p>または、検索結果を PST ファイルにエクスポートし、Microsoft 365インポート サービスを使用して、PST を探索メールボックスにインポートすることもできます。 手順については、「ネットワーク アップロードを使用して PST ファイルをインポートしてファイルをインポートする」を<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">参照</a>Office 365。
</tr>
<tr class=even>
  <td>1 つのメールボックスから別のメールボックスへのメッセージのコピー</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするために必要なアクセス許可をユーザーに割り当てるだけで問題ありません。</td>
  
  </tr>
<tr class="odd">
<td>回復可能なアイテム フォルダーからアイテムを復元する</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>アイテムの削除済みアイテムの保持期間が経過しない<i></i>限り、メールボックス内の完全に削除されたアイテム (ソフト削除済みアイテムとも呼ばれる) を復元できます。 詳細については、「回復可能な<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">アイテム フォルダー」を参照Exchange Online。</a></td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>インプレース電子情報開示とインプレース ホールドに関するよくある質問

**EAC で電子情報開示 In-Place保持&検索結果のコピー機能を使用して、弁護士によるレビューのために検索結果を探索メールボックスにコピーします。どのようなオプションがありますか?**

今日、この機能をレプリケートする方法は 2 通りあります。 1 つ目は[、v2.0](./view-documents-in-review-set.md)のレビュー セットAdvanced eDiscovery使用します。 レビュー セットには、ドキュメントの高速検索、タグ付け、メール スレッド、重複グループ化に近い、テーマ分析、予測コーディングなど、従来のレビュー ツールに表示される機能の多くがあります。 引き続き確認のために探索メールボックスを使用する場合、2 番目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの [PST](use-network-upload-to-import-pst-files.md) インポート機能を使用して、PST ファイルを探索メールボックスにインポートします。

**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御する方法**

またMicrosoft 365 コンプライアンス センターコンプライアンスの境界[を](set-up-compliance-boundaries.md)使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。 コンプライアンスの境界は、政府機関の境界内にとどまる必要がある政府機関や、地理的な下宿主を尊重するために必要な多国籍企業で役立ちます。

**現在の検索とホールドを現在の検索先に移動Microsoft 365 コンプライアンス センター?**

PowerShell を使用して電子情報開示In-Place EAC から電子情報開示の検索と保持を移行できます。 手順については、「検索と保持を EAC からサーバーに移行する」[を参照Microsoft 365 コンプライアンス センター。](./migrate-legacy-ediscovery-searches-and-holds.md)

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch コマンドレット

Exchange 管理センターで 2017 年 7 月 1 日に発表された元の通知に基づいて、In-Place 電子情報開示 & ホールド機能と対応する **\* -MailboxSearch** コマンドレットは廃止されます。 これらのコマンドレットを使用すると、ユーザーは、法的、規制、およびパブリック要求のためにメールボックス コンテンツを検索、保持、およびエクスポートできます。

これらの機能は、パフォーマンスとスケーラビリティが向上した Microsoft 365 コンプライアンス センター および[<span class="underline">Office 365</span>](./microsoft-365-compliance-center.md)セキュリティ & コンプライアンス センター PowerShell で利用できる機能なので、これらの強化されたコマンドレットを使用する必要があります。 これらのコマンドレットには[<span class="underline"> \* 、-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline">、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule、 \* </span>](/powershell/module/exchange/get-compliancesearch)[<span class="underline"> \* および -ComplianceSearchAction が含まれます</span>](/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdrule)

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365およびMicrosoft 365 Enterprise組織

- Office 365およびMicrosoft 365 Education組織

- Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: **New-MailboxSearch** を使用して新しい In-Place 電子情報開示検索と In-Place 保留リストを作成することはできませんが、コマンドレットを使用して既存の検索と保持を実行、編集、および削除することができます。 Microsoft サポートは、このような種類の検索と保留に関するサポートを提供しなくなりました。

- 2020 年 10 月 1 日: 前に述べたように、eAC の In-Place 電子情報開示 & Holds 機能は読み取り専用モードになります。 つまり **、New-MailboxSearch** コマンドレット **、Start-MailboxSearch** コマンドレット、 **または Set-MailboxSearch** コマンドレットを使用することはできません。 既存の検索と保留リストのみを取得および削除できます。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換える他のツールについて説明します。

<table>
<thead>
<tr class="header">
<th>機能</th>
<th>代替ツール</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>検索とエクスポート</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。 新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。 次に <strong>、New-ComplianceSearchAction</strong> コマンドレットを使用して検索結果をエクスポートできます。 これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センター電子情報開示のコア ツールを使用する必要があります。</p>
<p>
<p><strong>注:</strong>これらのコマンドレットを使用して、コアの電子情報開示ケースに関連付けされていない検索を作成する場合、これらの検索は、Microsoft 365 コンプライアンス センター の [<strong></strong>コンテンツ検索] ページに表示されます。</p></td>
</tr>
<tr class="even">
<td>メールボックス内のコンテンツを保持する</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>コンプライアンス ケースにMicrosoft 365 コンプライアンス センターする必要があります。 まず、コンプライアンス ケースを作成し、CaseHoldPolicy と CaseHoldRule を作成します。</p>
<p><strong>注:</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成され CaseHoldPolicy に関連付けられるまで、ホールドは操作不能になります。 詳細については、コマンドレットのドキュメントを参照してください。</p></td>
</tr>
<tr class="odd">
<td>検索結果を探索メールボックスにコピーする</td>
<td>なし</td>
<td>この機能は、すべてのサービスにアクセスできるMicrosoft 365はありません。 代替ソリューションについては、以下の FAQ を参照してください。</td>
</tr>
  <tr class=even>
  <td>1 つのメールボックスから別のメールボックスへのメッセージのコピー</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>***-MailboxSearch コマンドレットに関する** よくある質問

**コピー検索を使用して、他の電子情報開示および法的調査のために電子メール メッセージまたはインスタント メッセージをエクスポートします。これらのコマンドレットが廃止された後、他にどのようなオプションがありますか?**

[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)には、-MailboxSearch コマンドレットを使用するよりもはるかに回復性と拡張性を備えた分析などの目的でデータを抽出するためのメソッドが多数用意 **\*** されています。

**検索と保持を移行する方法をMicrosoft 365 コンプライアンス センター?**

PowerShell スクリプトを使用して、In-Placeから電子情報開示の検索と保持Exchange移行できます。 詳細については、「従来の電子情報開示の検索と保持を移行[する」を参照Microsoft 365 コンプライアンス センター。](migrate-legacy-eDiscovery-searches-and-holds.md)

**コマンドレットが廃止された後も、検索を削除または取得できますか?**

はい、検索を作成および変更する機能は削除しますが **、Get-MailboxSearch と Remove-MailboxSearch** は、詳細な通知が表示されるまで引き続き使用できます。 ただし、これらのコマンドレットの使用は、退職日後に自身のリスクにさらされ、Microsoft サポートはサポートを提供できなくなりました。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox コマンドレット

PowerShell **の Search-Mailbox** コマンドレットExchange Online、2018 年からコマンドレット出力の警告で最初に発表されたので廃止されます。 **Search-Mailbox コマンドレット** は、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを削除するために使用されています。 コンテンツを検索および削除するには、Office 365 セキュリティ & コンプライアンス センター PowerShell の **New-ComplianceSearch** コマンドレットと **New-ComplianceSearchAction** コマンドレットの使用を開始することをお勧めします。 組み込みのセキュリティ エクスペリエンスでは、電子メール[<span class="underline">Microsoft 365</span>](../security/index.yml)他の多くのセキュリティ機能に対する堅牢な脅威保護が提供Microsoft サービス。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365およびMicrosoft 365 Enterprise組織

- Office 365およびMicrosoft 365 Education組織

- Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

-  2020 年 7 月 1 日: **Search-Mailbox** コマンドレットは使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換える他のツールについて説明します。

<table>
<thead>
<tr class="header">
<th>機能</th>
<th>代替ツール</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>メールボックスを検索する</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。 新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。 次に <strong>、New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。 これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センター電子情報開示のコア ツールを使用する必要があります。</p></p>
</td>
</tr>
<tr class="even">
<td>メールボックスから一括メールを削除する</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></p>
<p></p></td>
<td><p>管理者は、ユーザーのアーカイブ メールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</p>
</td>
</tr>
<tr class="even">
<td>検索結果を探索メールボックスにコピーする</td>
<td> </td>
<td>この機能は、すべてのサービスにアクセスできるMicrosoft 365はありません。 代替ソリューションについては <strong>、「*-MailboxSearch コマンドレット</strong> 」の「FAQ」を参照してください。 </td>
</tr>
<tr class=odd>
  <td>1 つのメールボックスから別のメールボックスへのメッセージのコピー</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。 したがって、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</td>
</tr>
<tr class=even>
  <td>メールボックスからメッセージを削除する</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索と削除に役立ちます。 <strong>New-ComplianceSearch</strong>コマンドレットと<strong>New-ComplianceSearch</strong>コマンドレットを使用して検索を作成して実行し<strong>、New-ComplianceSearchAction -Purge -PurgeType</strong>コマンドを使用してコンテンツを削除できます。 詳細については、「メッセージの検索と <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">削除」を参照してください</span></a>。</p>
</td>
</tr>
<tr class="odd"> 
<td>メールボックスからメッセージを削除する</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
<td>メールボックスからメッセージを削除するには、管理者のアクセス許可を割り当て、従業員のメールボックスにアクセスします。 メッセージは、必要に応じて削除およびリサイクルできます。この機能は、Outlook。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>ExchangeWeb サービス API の操作

Exchange Web Services API のこれらの操作は、Exchange 管理センターの In-Place 電子情報開示 & 保留機能と、Exchange Online PowerShell の対応する **\* -MailboxSearch** コマンドレットによって使用されます。 また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365およびMicrosoft 365 Enterprise組織

- Office 365およびMicrosoft 365 Education組織

- Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作は使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0 は、コアの電子情報開示ケースで使用できる Advanced eDiscovery のバージョンで、[Advanced eDiscovery に切り替える] を **クリック** して使用できません。 その機能は、新しいソリューション Advanced eDiscovery[に](./ediscovery.md)置き換Microsoft 365 コンプライアンス センター。

組織で v1.0 を使用Advanced eDiscoveryするには、次のコマンドを実行します。

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。

2. コンプライアンス センターの左側のナビゲーション ウィンドウで、[電子情報開示] >コア] **をクリックし、Core** 電子情報開示ケースを開きます。

3. [デバイスに切り替Advanced eDiscovery] ボタン **が表示** された場合は、クリックすると 1.0 バージョンの Advanced eDiscovery に移動します。これは廃止されます。 Core eDiscovery でケースを作成および管理する機能は影響を受け取らない。 v1.0 でケース データを追加および分析する機能 (Advanced eDiscovery に切り替 **える)** をクリックAdvanced eDiscovery削除されます。

Microsoft 365 の新しい Advanced eDiscovery ソリューション *(Advanced eDiscovery v2.0* とも呼ばれる) は、元のソリューションのすべての機能を提供しますが、他の Microsoft 365 サービスのコンテンツを識別し、そのコンテンツを収集し、レビュー担当者が迅速な検索クエリ、タグ付け、分析機能を活用して関連ドキュメントを作成できるレビュー セットに追加するカストディアンベースのアプローチが含まれています。 Advanced eDiscovery、Microsoft と Microsoft 以外のファイルの種類の両方の処理とネイティブ ビューアーが追加されました。ファイルの種類の完全な一覧は[次](./supported-filetypes-ediscovery20.md)のとおりです。サポートされているメタデータ フィールドは次[のとおりです](./document-metadata-fields-in-advanced-ediscovery.md)。 また、新しい Advanced eDiscovery ソリューションでは、強力な保管担当者が管理機能を提供し、さまざまなサービスのコンテンツにホールドを適用し、保留リストのユーザーに通知し、保管担当者の応答を追跡できます(すべて Advanced eDiscovery ケース内)。

Advanced eDiscovery v2.0 へのアクセス

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。

2. Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。

この時点で、電子情報開示ワークフローを新しい電子情報開示機能に移行Advanced eDiscovery勧めします。 必要に応じて、コンテンツをエクスポートAdvanced eDiscoveryオフラインで保存することで、1.0 ケースをアーカイブできます。 2020 年 12 月 31 日まで、既存のケースでは引き続き Advanced eDiscovery v1.0 にアクセスすることができますが、Microsoft サポートは 2020 年 10 月 1 日以降はサポートを提供しない予定です。 詳細については、次のタイムラインを参照してください。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365およびMicrosoft 365 Enterprise組織

- Office 365およびMicrosoft 365 Education組織

- Office 365およびMicrosoft 365組織。これには、GCC、GCC、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: v1.0 の新しいAdvanced eDiscovery作成できない。

- 2020 年 10 月 1 日: 新しいデータを追加できない (Advanced eDiscovery の検索結果を準備する) 場合。 既存のケースのデータを自分のリスクで引き続き操作できます。 Microsoft サポートはサポートを提供しなくなりました。 

- 2020 年 12 月 31 日: v1.0 のケースAdvanced eDiscoveryアクセスできない。

### <a name="alternative-tools"></a>代替ツール

この[Advanced eDiscoveryソリューション](./overview-ediscovery-20.md)Microsoft 365 コンプライアンス センター。