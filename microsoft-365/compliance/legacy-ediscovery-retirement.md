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
description: In-Placeの電子情報開示In-Place保持 (および対応する PowerShell コマンドレット) は、2020 年前半に廃止されます。 またSearch-Mailboxコマンドレットと Advanced eDiscovery v1.0 も同じ期間に廃止されます。
ms.openlocfilehash: 48a20b9e73c5379325afb715a86c4945385fd0b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50903607"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>従来の電子情報開示ツールの廃止

> [!IMPORTANT]
> Microsoft は、公衆衛生の状況を評価し、これがお客様に与える影響を理解しています。 強いパートナーであり、責任あるグローバル市民でありたく思っています。 直面している多くの負担の 1 つを軽減するために、この記事で説明する従来の電子情報開示ツールの予定退職を 3 か月遅らせる予定です。 **更新された退職日は、以下に反映されます。**

Microsoft は長年にわたり、Exchange Online から電子メール コンテンツを検索、プレビュー、エクスポートできる電子情報開示ツールを提供してきました。 ただし、これらのツールは、SharePoint Online や Microsoft 365 グループなどの他の Microsoft 365 サービスで Exchange 以外のコンテンツを検索する効果的な方法を提供しなくなりました。 この問題に対処するために、Microsoft はさまざまな Microsoft 365 コンテンツを検索するのに役立つその他の電子情報開示ツールを提供しています。 また [、Microsoft 365](https://compliance.microsoft.com)コンプライアンス センターに最新かつ強力な電子情報開示機能を組み込む作業を行っています。 これにより、組織は Exchange Online を含む多くの Microsoft 365 サービスのコンテンツに対する法的、内部的、その他のドキュメント要求に対応できます。

Microsoft 365 コンプライアンス センターでこの新しく強化された電子情報開示機能の結果、Exchange Online および Microsoft 365 での電子メール コンテンツの検索に関連する次の電子情報開示関連の機能が廃止されます。

- Exchange 管理センターの[インプレース電子情報開示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- Exchange Online PowerShell コマンドレットは、電子情報開示In-Placeおよび In-Place保持をサポートします (これらのコマンドレットは、 **-MailboxSearch* コマンドレットとしてまとめて識別されます)。 これには、次のコマンドレットが含まれます。

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

- [Office 365 Advanced eDiscovery v1.0](./overview-ediscovery-20.md)は、Office 365 セキュリティ & コンプライアンス センターの Core 電子情報開示ケースを通じてアクセスされる Advanced eDiscovery の最初のバージョンです。 Advanced eDiscovery v1.0 の使用を取り除いても、コア電子情報開示ケースを作成および管理する機能には影響はありません。

> [!NOTE]
> 廃止される電子情報開示機能は、Microsoft 365 および 365 のクラウドベースのバージョンにのみOfficeされます。 オンプレミスバージョンの Exchange と SharePoint の電子情報開示機能は、今後の通知まで引き続きサポートされます。

この記事の以下のセクションでは、廃止される各機能に関するガイダンスを提供します。 この情報には、廃止されたツールの代わりに使用できるタイムラインや代替ツールが含まれています。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place Exchange 管理センターIn-Place電子情報開示と電子情報開示の保持 

2017 年 7 月 1 日の当初の発表と同様に、exchange 管理センター (EAC) の In-Place 電子情報開示 & 保留機能は廃止されます。 EAC In-Place [&保持] ページでは、Exchange Online からコンテンツを検索、保持、およびエクスポートできます。 In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、ユーザーまたは他の電子情報開示管理者がコンテンツを確認し、法的、規制、およびパブリック要求に対して利用可能にできます。

これらの機能 (検索結果を探索メールボックスにコピーする場合を除く) はすべて [、Microsoft 365](./microsoft-365-compliance-center.md) コンプライアンス センターのコンテンツ検索ツール、電子情報開示ツール、高度な電子情報開示ツール (Microsoft 365 サービスの機能、信頼性、およびサポートが強化された) で利用できますので、できるだけ早くこれらのツールの使用を開始することをお勧めします。 これらの他の電子情報開示ツールへの移行を支援するために、以下の表に、電子情報開示と電子情報開示の保持ではなくIn-PlaceツールIn-Place示します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 政府機関。これには、GCC、GCC High、DoD が含まれます。

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
<td>Microsoft 365 コンプライアンス センターの主要な電子情報開示ケース </td>
<td><p>コアの電子情報開示ケースの機能を使用すると、電子情報開示と保留リストのIn-PlaceパリティIn-Placeします。 エクスポートできるものには、次のようなものがあります。</p>
<ul>
<li>
<p>検索は数百万の場所に拡大縮小されます。</p>
</li>
<li>
<p>コンテンツの検索、エクスポート、および保留に関する信頼性の向上</p>
</li>
<li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、および Office 365 アプリケーションに保存されているその他のコンテンツの検索</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保持の目的で保持する</td>
<td>Microsoft 365 コンプライアンス センターの保持ポリシー</td>
<td><p>アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて保持期間が経過した後に削除できます。 その他の機能は次のとおりです。</p>
<ul>
<li>
<p>組織全体にポリシーを適用する </p>
</li><li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、および 365 グループなどの特定のコンテンツOffice適用する</p></li>
<li>
<p>特定のユーザーにポリシーを適用する</p></li></ul>
<p>詳細については、「アイテム保持ポリシー <a href="/microsoft-365/compliance/retention-policies"> と保持ラベルについて」を参照してください</a>。</td>
</tr>
<tr class="odd">
<td>確認のために電子メール検索結果を探索メールボックスにコピーする</td><td>Advanced eDiscovery v2.0 のレビュー セット</td>
<td><p>Microsoft 365 のコンテンツを簡単に確認できます。 レビュー セットには、次を含む、レビューに必要な時間とデータの削減に役立つ多くの機能があります。</p>
<ul>
<li><p>レビュー セットで高速検索クエリを実行し、コンテンツをフィルター処理する</p></li>
<li><p>レビュー セット内のコンテンツを分析する。これには、電子メール スレッド、重複に近い検出、テーマ分析、予測コーディングが含まれます。</p></li>
<li><p>レビュー セット内のドキュメントをタグ付けする</p></li>
<li><p>弁護士クライアント特権コンテンツの識別に役立つタグ付け提案</p></li></ul>
<p>詳細については、「<a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</p>
<p>
<p>または、検索結果を PST ファイルにエクスポートし、Microsoft 365 Import Service を使用して PST を探索メールボックスにインポートすることもできます。 詳細な手順については、「ネットワーク アップロードを使用して PST ファイルを <a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">365</a>にインポートするOffice参照してください。
</tr>
<tr class=even>
  <td>1 つのメールボックスから別のメールボックスへのメッセージのコピー</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</td>
  
  </tr>
<tr class="odd">
<td>回復可能なアイテム フォルダーからアイテムを復元する</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>アイテムの削除済みアイテムの保持期間が経過しない<i></i>限り、メールボックス内の完全に削除されたアイテム (ソフト削除済みアイテムとも呼ばれる) を復元できます。 詳細については <a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">、「Exchange Online の回復可能なアイテム フォルダー」を参照してください</a>。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>インプレース電子情報開示とインプレース ホールドに関するよくある質問

**EAC で電子情報開示 In-Place保持&検索結果のコピー機能を使用して、弁護士によるレビューのために検索結果を探索メールボックスにコピーします。どのようなオプションがありますか?**

今日、この機能をレプリケートする方法は 2 通りあります。 1 つ目は、Advanced [eDiscovery v2.0 のレビュー セットを使用する方法です](./view-documents-in-review-set.md)。 レビュー セットには、ドキュメントの高速検索、タグ付け、メール スレッド、重複グループ化に近い、テーマ分析、予測コーディングなど、従来のレビュー ツールに表示される機能の多くがあります。 引き続き確認のために探索メールボックスを使用する場合、2 番目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの [PST](use-network-upload-to-import-pst-files.md) インポート機能を使用して、PST ファイルを探索メールボックスにインポートします。

**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御する方法**

Microsoft 365 コンプライアンス センター[](set-up-compliance-boundaries.md)では、コンプライアンスの境界を使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。 コンプライアンスの境界は、政府機関の境界内にとどまる必要がある政府機関や、地理的な下宿主を尊重するために必要な多国籍企業で役立ちます。

**現在の検索と保持を Microsoft 365 コンプライアンス センターに移動する方法**

PowerShell を使用して電子情報開示In-Place EAC から電子情報開示の検索と保持を移行できます。 手順については、「検索とホールドを EAC から [Microsoft 365](./migrate-legacy-ediscovery-searches-and-holds.md)コンプライアンス センターに移行する」を参照してください。

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch コマンドレット

Exchange 管理センターで 2017 年 7 月 1 日に発表された元の通知に基づいて、In-Place 電子情報開示 & ホールド機能と対応する **\* -MailboxSearch** コマンドレットは廃止されます。 これらのコマンドレットを使用すると、ユーザーは、法的、規制、およびパブリック要求のためにメールボックス コンテンツを検索、保持、およびエクスポートできます。

これらの機能は [<span class="underline">、Microsoft 365</span>](./microsoft-365-compliance-center.md) コンプライアンス センターと Office 365 セキュリティ & コンプライアンス センター PowerShell で使用できる機能であり、パフォーマンスとスケーラビリティが向上していますので、これらの強化されたコマンドレットを使用する必要があります。 これらのコマンドレットには[<span class="underline"> \* 、-ComplianceCase</span>](/powershell/module/exchange/get-compliancecase) [<span class="underline">、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule、 \* </span>](/powershell/module/exchange/get-compliancesearch)[<span class="underline"> \* および -ComplianceSearchAction が含まれます</span>](/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](/powershell/module/exchange/get-caseholdrule)

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 政府機関。これには、GCC、GCC High、DoD が含まれます。

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
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。 新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。 次に <strong>、New-ComplianceSearchAction</strong> コマンドレットを使用して検索結果をエクスポートできます。 Microsoft 365 コンプライアンス センターのコア電子情報開示ツールを使用して、それらの検索結果をローカル コンピューターにダウンロードする必要があります。</p>
<p>
<p><strong>注:</strong>これらのコマンドレットを使用して、コアの電子情報開示ケースに関連付けされていない検索を作成する場合、これらの検索は Microsoft 365 コンプライアンス センターの [コンテンツ検索] ページに表示されます。 <strong></strong></p></td>
</tr>
<tr class="even">
<td>メールボックス内のコンテンツを保持する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 コンプライアンス センターの保持は、ComplianceCase に関連付けられている必要があります。 まず、コンプライアンス ケースを作成し、CaseHoldPolicy と CaseHoldRule を作成します。</p>
<p><strong>注:</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成され CaseHoldPolicy に関連付けられるまで、ホールドは操作不能になります。 詳細については、コマンドレットのドキュメントを参照してください。</p></td>
</tr>
<tr class="odd">
<td>検索結果を探索メールボックスにコピーする</td>
<td>なし</td>
<td>この機能は、すべての Microsoft 365 サービスへのアクセスを提供していないので、直接置き換えはありません。 代替ソリューションについては、以下の FAQ を参照してください。</td>
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

[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)には、-MailboxSearch コマンドレットを使用するよりもはるかに回復性と拡張性を備えた分析などの目的でデータを抽出するためのメソッド **\*** が多数用意されています。

**検索と保持を Microsoft 365 コンプライアンス センターに移行する方法**

PowerShell スクリプトを使用In-Place Exchange 管理センターから電子情報開示の検索と保持を移行できます。 詳細については、「従来の電子情報開示の検索と保持を [Microsoft 365 コンプライアンス センター](migrate-legacy-eDiscovery-searches-and-holds.md)に移行する」を参照してください。

**コマンドレットが廃止された後も、検索を削除または取得できますか?**

はい、検索を作成および変更する機能は削除しますが **、Get-MailboxSearch と Remove-MailboxSearch** は、詳細な通知が表示されるまで引き続き使用できます。 ただし、これらのコマンドレットの使用は、退職日後に自身のリスクにさらされ、Microsoft サポートはサポートを提供できなくなりました。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox コマンドレット

Exchange Online PowerShell の **Search-Mailbox** コマンドレットは、2018 年からコマンドレット出力の警告で最初に発表されたので廃止されます。 **Search-Mailbox コマンドレット** は、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを削除するために使用されています。 コンテンツを検索および削除するには、Office 365 セキュリティ & コンプライアンス センター PowerShell の **New-ComplianceSearch** コマンドレットと **New-ComplianceSearchAction** コマンドレットの使用を開始することをお勧めします。 組み込みのセキュリティ エクスペリエンスのために [<span class="underline">、Microsoft 365</span>](../security/index.yml) セキュリティ機能は、電子メールや他の多くの Microsoft サービスに堅牢な脅威保護を提供します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 政府機関。これには、GCC、GCC High、DoD が含まれます。

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
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></a></p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。 新しい検索を作成し、検索見積もりを表示するには<strong>、New-、Get-、</strong><strong>および</strong> <strong>Start-ComplianceSearch</strong>コマンドレットを使用します。 次に <strong>、New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。 Microsoft 365 コンプライアンス センターのコア電子情報開示ツールを使用して、それらの検索結果をローカル コンピューターにダウンロードする必要があります。</p></p>
</td>
</tr>
<tr class="even">
<td>メールボックスから一括メールを削除する</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></p>
<p></p></td>
<td><p>管理者は、ユーザーのアーカイブ メールボックスにアイテムを自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</p>
</td>
</tr>
<tr class="even">
<td>検索結果を探索メールボックスにコピーする</td>
<td> </td>
<td>この機能は、すべての Microsoft 365 サービスへのアクセスを提供していないので、直接置き換えはありません。 代替ソリューションについては <strong>、「*-MailboxSearch コマンドレット</strong> 」の「FAQ」を参照してください。 </td>
</tr>
<tr class=odd>
  <td>1 つのメールボックスから別のメールボックスへのメッセージのコピー</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>他のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、他のユーザーに元従業員のメールへのアクセス権を与える必要がある場合など)、そのユーザーに元従業員のメールボックスにアクセスするためのアクセス許可を割り当てる必要があります。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのユーザーアクセス許可を割り当てるだけ。</td>
</tr>
<tr class=even>
  <td>メールボックスからメッセージを削除する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索と削除に役立ちます。 <strong>New-ComplianceSearch</strong>コマンドレットと<strong>New-ComplianceSearch</strong>コマンドレットを使用して検索を作成して実行し<strong>、New-ComplianceSearchAction -Purge -PurgeType</strong>コマンドを使用してコンテンツを削除できます。 詳細については、「メッセージの検索と <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">削除」を参照してください</span></a>。</p>
</td>
</tr>
<tr class="odd"> 
<td>メールボックスからメッセージを削除する</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
<td>メールボックスからメッセージを削除するには、管理者のアクセス許可を割り当て、従業員のメールボックスにアクセスします。 Outlook に組み込みの検索機能と表示機能を利用して、必要に応じてメッセージを削除してリサイクルできます。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web Services API 操作

Exchange Web Services API のこれらの操作は、Exchange 管理センターの In-Place 電子情報開示 & 保持機能と、Exchange Online PowerShell の対応する **\* -MailboxSearch** コマンドレットによって使用されます。 また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 政府機関。これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作は使用できなくなりました。Microsoft サポートはサポートを提供しなくなりました。

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

[高度な電子情報開示に切り替える] をクリックして、コアの電子情報開示ケースで使用できる高度な電子情報開示のバージョンである Advanced **eDiscovery** v1.0 は廃止されています。 その機能は、Microsoft 365 コンプライアンス センターの新しい Advanced [eDiscovery](./ediscovery.md) ソリューションに置き換えされました。

組織が Advanced eDiscovery v1.0 を使用しているかどうかを確認するには、次のコマンドを実行します。

1. [Office 365 セキュリティ/コンプライアンス センター](https://protection.office.com)に移動します。

2. セキュリティ コンプライアンス センターの左側のナビゲーション ウィンドウ&、[電子情報開示>] をクリックし、コア電子情報開示ケースを開きます。 

3. [高度な電子情報開示に切 **り** 替える] ボタンが表示された場合、それをクリックすると、1.0 バージョンの Advanced eDiscovery に移動し、廃止されます。 Core eDiscovery でケースを作成および管理する機能は影響を受け取らない。 Advanced eDiscovery v1.0 ([高度な電子情報開示に切り替える **]** をクリックして) でケース データを追加および分析する機能だけが廃止されています。

Microsoft 365 の新しい Advanced eDiscovery ソリューション (Advanced *eDiscovery v2.0* とも呼ばれる) は、元のソリューションのすべての機能を提供しますが、現在では、他の Microsoft 365 サービス内のコンテンツを識別し、そのコンテンツを収集し、レビュー担当者が迅速な検索クエリ、タグ付け、分析機能を利用して関連ドキュメントを作成するのに役立つレビュー セットに追加するカストディアンベースのアプローチが含まれています。 高度な電子情報開示には、Microsoft と Microsoft 以外のファイルの種類の処理とネイティブ ビューアーの両方が含まれる、ファイルの種類の完全な一覧が [ここに](./supported-filetypes-ediscovery20.md) 表示され、サポートされているメタデータ フィールドがここに [表示されます](./document-metadata-fields-in-advanced-ediscovery.md)。 また、新しい Advanced eDiscovery ソリューションは、強力な保管担当者保持管理機能を提供します。これにより、さまざまなサービス内のコンテンツにホールドを適用し、ユーザーにホールドを通知し、保管担当者の応答を追跡できます(すべて Advanced eDiscovery ケース内)。

Advanced eDiscovery v2.0 へのアクセス

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。

2. Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。

現時点では、電子情報開示ワークフローを新しい高度な電子情報開示機能に移行することをお勧めします。 必要に応じて、コンテンツをエクスポートしてオフラインで保存することで、Advanced eDiscovery 1.0 ケースをアーカイブできます。 既存のケースでは、2020 年 12 月 31 日まで Advanced eDiscovery v1.0 にアクセスすることができますが、Microsoft サポートは 2020 年 10 月 1 日以降はサポートを提供しない予定です。 詳細については、次のタイムラインを参照してください。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 政府機関。これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: 新しい Advanced eDiscovery v1.0 ケースを作成できない。

- 2020 年 10 月 1 日: 新しいデータ (高度な電子情報開示の検索結果を準備する) を任意のケースに追加できない。 既存のケースのデータを自分のリスクで引き続き操作できます。 Microsoft サポートはサポートを提供しなくなりました。 

- 2020 年 12 月 31 日: Advanced eDiscovery v1.0 ケースにアクセスできない。

### <a name="alternative-tools"></a>代替ツール

Microsoft [](./overview-ediscovery-20.md) 365 コンプライアンス センターの高度な電子情報開示ソリューション。