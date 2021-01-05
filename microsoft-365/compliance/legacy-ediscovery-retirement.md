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
description: In-Place電子情報開示とIn-Place保留 (および対応する PowerShell コマンドレット) は、2020 年上半期に廃止されます。 このSearch-Mailbox Advanced eDiscovery v1.0 も同じ期間に廃止されます。
ms.openlocfilehash: a40cc67b29e33d61d6750792f6a773622a73f678
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750880"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>従来の電子情報開示ツールの廃止

> [!IMPORTANT]
> Microsoft は、公衆の健康状況を評価しています。お客様に対する影響を理解しています。 私たちは、強力なパートナーであり、責任を持つグローバル市民でありしたいと考えています。 直面している多くの負担の 1 つを軽減するために、この記事で説明する従来の電子情報開示ツールの予定されたサポート期間を 3 か月遅らせる予定です。 **更新された終了日を以下に示します。**

長年にわたり、Microsoft は Exchange Online から電子メール コンテンツを検索、プレビュー、エクスポートできる電子情報開示ツールを提供してきました。 ただし、これらのツールは、SharePoint Online や Microsoft 365 グループなどの他の Microsoft 365 サービスで Exchange 以外のコンテンツを検索する効果的な方法を提供しなくなりました。 この問題に対処するために、Microsoft はさまざまな Microsoft 365 コンテンツの検索に役立つ他の電子情報開示ツールを提供しています。 また、Microsoft 365 コンプライアンス センターに最新かつ強力な電子情報開示機能を組み込む取[り組みにも取り組み続け、](https://compliance.microsoft.com) これにより、組織は Exchange Online を含む多くの Microsoft 365 サービスのコンテンツに対する法的、内部的、その他のドキュメント要求に対応できます。

この Microsoft 365 コンプライアンス センターの電子情報開示機能の新機能および強化された結果、Exchange Online と Microsoft 365 の電子メール コンテンツの検索に関連する次の電子情報開示関連の機能は廃止されます。

- Exchange 管理センターの[インプレース電子情報開示](https://docs.microsoft.com/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- 電子情報開示と In-Place 保持をサポートする Exchange Online Power In-Place Shell コマンドレット (これらのコマンドレットは、まとめて **-MailboxSearch* コマンドレットとして識別されます)。 これには、次のコマンドレットが含まれます。

  - [New-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Get-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/get-mailboxsearch)コマンドレットと[Remove-MailboxSearch](https://docs.microsoft.com/powershell/module/exchange/remove-mailboxsearch)コマンドレットは、他の ****-MailboxSearch**_ コマンドレットが廃止された後に使用できます。このコマンドレットを使用すると、他の電子情報開示および保持ツールへの移行に役立ちます。 ただし、特定の日付 (下記を参照) が終了すると、Microsoft サポートはこれら 2 つのコマンドレットをサポートしなくなりました。

- Exchange Online PowerShell の [Search-Mailbox](https://docs.microsoft.com/powershell/module/exchange/search-mailbox) コマンドレット。

- Exchange Web Services API での次の操作。

   - [GetSearchableMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](https://docs.microsoft.com/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Office 365 Advanced eDiscovery v1.0](office-365-advanced-ediscovery.md)は、Office 365 セキュリティ & コンプライアンス センターのコア電子情報開示ケースを通じてアクセスされる Advanced eDiscovery の最初のバージョンです。 Advanced eDiscovery v1.0 のサポートがサポートされなしても、コア電子情報開示ケースを作成および管理する機能に影響はありません。

> [!NOTE]
> 廃止される電子情報開示機能は、クラウドベースのバージョンの Microsoft 365 および Office 365 にのみ適用されます。 Exchange と SharePoint のオンプレミス バージョンの電子情報開示機能は、今後の通知まで引き続きサポートされます。

この記事の以下のセクションでは、廃止される各機能に関するガイダンスを提供します。 この情報には、廃止されたツールの代わりに使用できるタイムラインや代替ツールが含まれています。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>In-Place Exchange 管理センターIn-Place電子情報開示と電子情報開示の保留 

2017 年 7 月 1 日の最初の発表と同様に、Exchange 管理センター (EAC) の In-Place 電子情報開示 & 保持機能は廃止されます。 EAC In-Place電子情報開示&保留リスト] ページを使用すると、Exchange Online からコンテンツを検索、保持、およびエクスポートできます。 In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、自分または他の電子情報開示管理者がコンテンツを確認し、法律、規制、および公開要求で利用できるようすることができます。

これらの機能 (検索結果を探索メールボックスにコピーする機能を除く) はすべて [、Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) コンプライアンス センターのコンテンツ検索、電子情報開示、および Advanced eDiscovery ツール (幅広い Microsoft 365 サービスの機能、信頼性、サポートが強化されたツール) で利用できるようなったため、これらのツールはできるだけ早く使用を開始することをお勧めします。 これらの他の電子情報開示ツールへの移行を支援するために、次の表に、電子情報開示と保持の代わりに使用できるツールIn-Place示In-Placeします。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline-for-retirement"></a>退職のタイムライン

- 2020 年 7 月 1 日: 新しい検索と保留リストを作成できないが、既存の検索の実行、編集、および削除は自分のリスクで行える。 Microsoft サポートは、EAC In-Place電子情報開示&保留を無効にしました。

- 2020 年 10 月 1 日: eAC の In-Place 電子情報開示 & 保留機能は読み取り専用モードになります。 これにより、可能な操作は、既存の検索および保留リストの削除のみになります。

### <a name="alternative-tools"></a>代替ツール

次の表に、廃止される既存の機能を置き換える場合に使用できるその他のツールを示します。

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
<td>法的な目的での検索、エクスポート、および保留</td>
<td>Microsoft 365 コンプライアンス センターのコア電子情報開示ケース </td>
<td><p>コア電子情報開示ケースの機能を使用すると、電子情報開示と電子情報開示In-Place保留リストをIn-Placeできます。 エクスポートできるものには、次のようなものがあります。</p>
<ul>
<li>
<p>検索の規模は数百万の場所に拡大</p>
</li>
<li>
<p>コンテンツの検索、エクスポート、保留に関する信頼性の向上</p>
</li>
<li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループ、および Office 365 アプリケーションに保存されているその他のコンテンツの検索</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保持の目的で保持する</td>
<td>Microsoft 365 コンプライアンス センターのアイテム保持ポリシー</td>
<td><p>アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて、保持期間が経過した後に削除できます。 その他の機能は次のとおりです。</p>
<ul>
<li>
<p>組織全体へのポリシーの適用 </p>
</li><li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、および Office 365 グループなどの特定のコンテンツの場所にポリシーを適用する</p></li>
<li>
<p>特定のユーザーにポリシーを適用する</p></li></ul>
<p>詳細については、「アイテム保持ポリシー <a href="https://docs.microsoft.com/microsoft-365/compliance/retention-policies"> と保持ラベルについて」を参照してください</a>。</td>
</tr>
<tr class="odd">
<td>確認のために電子メール検索結果を探索メールボックスにコピーする</td><td>Advanced eDiscovery v2.0 のレビュー セット</td>
<td><p>Microsoft 365 のコンテンツを簡単に確認できます。 レビュー セットには、レビューに必要な時間とデータの量を減らすのに役立つ多くの大きな機能があります。次の機能があります。</p>
<ul>
<li><p>レビュー セットで高速検索クエリを実行し、コンテンツをフィルター処理する</p></li>
<li><p>レビュー セット内のコンテンツを分析するこれには、電子メールのスレッド化、ほぼ重複した検出、テーマの分析、予測コーディングが含まれます。</p></li>
<li><p>レビュー セット内のドキュメントをタグ付けする</p></li>
<li><p>弁護士依頼人特権コンテンツの識別に役立つタグ付けの提案</p></li></ul>
<p>詳細については、「<a href="https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365 の Advanced eDiscovery ソリューションの概要</a>」を参照してください。</p>
<p>
<p>または、検索結果を PST ファイルにエクスポートし、Microsoft 365 インポート サービスを使用して PST を探索メールボックスにインポートすることもできます。 For step-by-step instruction, see <a href="https://docs.microsoft.com/microsoft-365/compliance/use-network-upload-to-import-pst-files">Use network upload to import PST files to Office 365</a>.
</tr>
<tr class=even>
  <td>1 つのメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>別のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など)、そのユーザーに元従業員のメールボックスへのアクセス許可を割り当て推奨します。 そのため、メールボックス アイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てる必要があります。</td>
  
  </tr>
<tr class="odd">
<td>[回復可能なアイテム] フォルダーからアイテムを復元する</td>
  <td><a href="https://docs.microsoft.com/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>アイテムの削除済みアイテムの保持期間が経過しない<i></i>限り、メールボックス内の完全に削除されたアイテム (回復可能な削除済みアイテムとも呼ばれる) を復元できます。 詳細については <a href="https://docs.microsoft.com/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">、「Exchange Online の回復可能なアイテム フォルダー」を参照してください</a>。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>インプレース電子情報開示とインプレース ホールドに関するよくある質問

_ *I use the copy search results functionality of In-Place eDiscovery & Holds in the EAC to copy search results to a discovery mailbox for review by attorneys.現在、どのようなオプションがありますか?**

現在、この機能をレプリケートする方法は 2 種類あります。 1 つ目は [、Advanced eDiscovery v2.0 のレビュー セットを使用する方法です](https://docs.microsoft.com/microsoft-365/compliance/view-documents-in-review-set)。 レビュー セットには、ドキュメントの高速検索、タグ付け、電子メールのスレッド処理、重複するグループ化に近い、テーマ分析、予測コーディングなど、従来のレビュー ツールに表示される機能と同じ機能が多数備備されています。 引き続き確認のために探索メールボックスを使用する場合、2 つ目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの PST インポート機能を使用して [PST](use-network-upload-to-import-pst-files.md) ファイルを探索メールボックスにインポートする方法です。

**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御する方法**

また、Microsoft 365 コンプライアンス[](set-up-compliance-boundaries.md)センターは、コンプライアンスの境界を使用して、電子情報開示マネージャーが検索できるコンテンツの場所を制御します。 コンプライアンスの境界は、政府機関の境界内に存在する必要がある政府機関や、地理的な下手を尊重するために必要な多国籍企業で役立ちます。

**現在の検索と保留を Microsoft 365 コンプライアンス センターに移動する方法**

PowerShell を使用して、In-Place検索と保留を EAC から移行できます。 手順については [、「EAC から Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2114224)コンプライアンス センターへの検索と保留の移行」を参照してください。

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch コマンドレット

Exchange 管理センターで 2017 年 7 月 1 日に発表された最初の通知に基づいて、In-Place 電子情報開示 & の保持機能と対応する **\* -MailboxSearch** コマンドレットは廃止されます。 これらのコマンドレットを使用すると、ユーザーは、法的、規制、および公的な要求のためにメールボックスの内容を検索、保持、およびエクスポートできます。

これらの機能は [<span class="underline">、Microsoft 365</span>](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) コンプライアンス センターと Office 365 セキュリティ & コンプライアンス センターの PowerShell で利用できます。パフォーマンスとスケーラビリティが向上したため、これらの強化されたコマンドレットを使用する必要があります。 これらのコマンドレットには[<span class="underline">、-ComplianceCase、-ComplianceSearch、-CaseHoldPolicy、-CaseHoldRule、 \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)および[<span class="underline"> \* -ComplianceSearchAction が含まれます</span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)。 [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy) [<span class="underline"> \* </span>](https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule)

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: **New-MailboxSearch** を使用して新しい In-Place 電子情報開示検索と In-Place 保留リストを作成することはできませんが、コマンドレットを使用して、既存の検索と保持を実行、編集、および削除することができます。 Microsoft サポートは、これらの種類の検索と保留リストに対するサポートを提供しなくなりました。

- 2020 年 10 月 1 日: 前に説明したように、EAC の In-Place 電子情報開示 & 保留機能は読み取り専用モードになります。 つまり **、New-MailboxSearch、Start-MailboxSearch、****または Set-MailboxSearch** コマンドレットを使用することはできません。  既存の検索と保留リストのみを取得および削除できます。

### <a name="alternative-tools"></a>代替ツール

次の表に、廃止される既存の機能を置き換える場合に使用できるその他のツールを示します。

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
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。 New-、Get-、および<strong>Start-ComplianceSearch</strong>コマンドレット<strong></strong>を使用して<strong></strong>、新しい検索を作成し、検索の見積もりを表示できます。 その後 <strong>、New-ComplianceSearchAction コマンドレット</strong> を使用して検索結果をエクスポートできます。 これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センターのコア電子情報開示ツールを使用する必要があります。</p>
<p>
<p><strong>注:</strong>これらのコマンドレットを使用して、コア電子情報開示ケースに関連付けされていない検索を作成する場合、これらの検索は Microsoft 365<strong></strong>コンプライアンス センターの [コンテンツ検索] ページに表示されます。</p></td>
</tr>
<tr class="even">
<td>メールボックス内のコンテンツを保持する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>Microsoft 365 コンプライアンス センターの保留は、ComplianceCase に関連付けられている必要があります。 まず、コンプライアンス ケースを作成し、次に CaseHoldPolicy と CaseHoldRule を作成します。</p>
<p><strong>注:</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成され、CaseHoldPolicy に関連付けられるまで、ホールドは操作できません。 詳細については、コマンドレットのドキュメントを参照してください。</p></td>
</tr>
<tr class="odd">
<td>検索結果を探索メールボックスにコピーする</td>
<td>なし</td>
<td>この機能は、すべての Microsoft 365 サービスにアクセスできないので、直接置き換えはありません。 代替ソリューションについては、以下の FAQ を参照してください。</td>
</tr>
  <tr class=even>
  <td>1 つのメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>別のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など)、そのユーザーに元従業員のメールボックスへのアクセス許可を割り当て推奨します。 そのため、メールボックス アイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てる必要があります。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>***-MailboxSearch コマンドレットに関する** FAQ

**コピー検索を使用して、他の電子情報開示や法的調査のために、電子メール メッセージまたはインスタント メッセージをエクスポートします。これらのコマンドレットが廃止された後、他にどのようなオプションがありますか?**

[<span class="underline">Microsoft Graph API</span>](https://developer.microsoft.com/en-us/graph)は、-MailboxSearch コマンドレットを使用する方法よりもはるかに回復力があり、拡張性に優れた、分析などの目的でデータを **\*** 抽出するための多くの方法を提供します。

**検索と保留を Microsoft 365 コンプライアンス センターに移行する方法**

PowerShell スクリプトを使用In-Place Exchange 管理センターから電子情報開示の検索と保留を移行できます。 詳細については、「従来の電子情報開示の検索と保留を [Microsoft 365](migrate-legacy-eDiscovery-searches-and-holds.md)コンプライアンス センターに移行する」を参照してください。

**コマンドレットが廃止された後でも、検索を削除または取得できますか?**

はい。検索を作成および変更する機能は削除しますが **、Get-MailboxSearch** と **Remove-MailboxSearch** は、さらに通知されるまで引き続き使用できます。 ただし、これらのコマンドレットの使用は、終了日後にユーザー自身のリスクにさらされ、Microsoft サポートはサポートを提供できなくなりました。

## <a name="search-mailbox-cmdlet"></a>Search-Mailboxコマンドレット

Exchange Online PowerShell の **Search-Mailbox** コマンドレットは、2018 年からコマンドレット出力の警告で最初に発表されたので廃止されます。 **Search-Mailbox コマンドレットは**、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを削除するために使用されています。 Office 365 Security & Compliance Center PowerShell で **New-ComplianceSearch** コマンドレットと **New-ComplianceSearchAction** コマンドレットを使用して、コンテンツの検索と削除を開始することをお勧めします。 組み込みのセキュリティ エクスペリエンスのために [<span class="underline">、Microsoft 365 のセキュリティ</span>](https://docs.microsoft.com/microsoft-365/security/) 機能は、電子メールや他の多くの Microsoft サービスに対して堅牢な脅威保護を提供します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

-  2020 年 7 月 1 日: **Search-Mailbox** コマンドレットは使用できなくなったので、Microsoft サポートはサポートを提供しなくなりました。

### <a name="alternative-tools"></a>代替ツール

次の表に、廃止される既存の機能を置き換える場合に使用できるその他のツールを示します。

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
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索とエクスポートに役立ちます。 New-、Get-、および<strong>Start-ComplianceSearch</strong>コマンドレット<strong></strong>を使用して<strong></strong>、新しい検索を作成し、検索の見積もりを表示できます。 次に <strong>、New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。 これらの検索結果をローカル コンピューターにダウンロードするには、Microsoft 365 コンプライアンス センターのコア電子情報開示ツールを使用する必要があります。</p></p>
</td>
</tr>
<tr class="even">
<td>メールボックスからバルク メールを削除する</td>
<td><p><a href="https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes?view=o365-worldwide"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></p>
<p></p></td>
<td><p>管理者は、アイテムをユーザーのアーカイブ メールボックスに自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</p>
</td>
</tr>
<tr class="even">
<td>検索結果を探索メールボックスにコピーする</td>
<td> </td>
<td>この機能は、すべての Microsoft 365 サービスにアクセスできないので、直接置き換えはありません。 代替ソリューションについては <strong>、「*-MailboxSearch コマンドレット</strong> 」セクションの FAQ を参照してください。 </td>
</tr>
<tr class=odd>
  <td>1 つのメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
  <td>別のユーザーの電子メールへのアクセス権をユーザーに付与するには (従業員が組織を離れ、別のユーザーに元従業員の電子メールへのアクセス権を付与する必要がある場合など)、そのユーザーに元従業員のメールボックスへのアクセス許可を割り当て推奨します。 そのため、メールボックス アイテムを別のユーザーのメールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てる必要があります。</td>
</tr>
<tr class=even>
  <td>メールボックスからメッセージを消去する</td>
<td><p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは、コンテンツの検索と削除に役立ちます。 <strong>New-ComplianceSearch</strong>コマンドレットと<strong>New-ComplianceSearch</strong>コマンドレットを使用して検索を作成して実行し<strong>、New-ComplianceSearchAction -Purge -PurgeType</strong>コマンドを使用してコンテンツを削除できます。 詳細については、「メッセージの検索 <a href="https://docs.microsoft.com/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">と削除」を参照してください</span></a>。</p>
</td>
</tr>
<tr class="odd"> 
<td>メールボックスからメッセージを消去する</td>
<td><a href="https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスへのアクセス許可の割り当て</a></td>
<td>メールボックスからメッセージを削除するには、従業員のメールボックスにアクセスするための管理者権限を割り当てる必要があります。 Outlook の組み込みの検索および表示機能を利用して、必要に応じてメッセージを削除およびリサイクルできます。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web サービス API の操作

Exchange Web サービス API のこれらの操作は、Exchange 管理センターの In-Place 電子情報開示 & 保留リスト機能と、Exchange Online PowerShell の対応する **\* -MailboxSearch** コマンドレットによって使用されます。 また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、および GetHoldOnMailboxes 操作は利用できなくなりました。また、Microsoft サポートはサポートを提供しなくなりました。

## <a name="advanced-ediscovery-v10"></a>Advanced eDiscovery v1.0

Advanced eDiscovery v1.0 は、Advanced eDiscovery への切り替えボタンをクリックしてコアの電子情報開示ケースで利用できる Advanced **eDiscovery** のバージョンで廃止されます。 その機能は、Microsoft 365 コンプライアンス センターの新しい [Advanced eDiscovery](https://aka.ms/edisco) ソリューションに置き換えられた。

組織が Advanced eDiscovery v1.0 を使用しているかどうかを確認するには、次のコマンドを実行します。

1. [Office 365 セキュリティ/コンプライアンス センター&します](https://protection.office.com)。

2. セキュリティ/コンプライアンス センターの左側のナビゲーション ウィンドウで&電子情報開示の>をクリックし、Core 電子情報開示ケースを開きます。

3. [Advanced **eDiscovery** に切り替える] ボタンが表示された場合、それをクリックすると 1.0 バージョンの Advanced eDiscovery に移動し、廃止されます。 コア電子情報開示でケースを作成および管理する機能は影響を受け取らない。 Advanced eDiscovery v1.0 で ([Advanced **eDiscovery** に切り替える] をクリックして) ケース データを追加および分析する機能だけが廃止されます。

Microsoft 365 の新しい Advanced eDiscovery ソリューション *(Advanced eDiscovery v2.0* とも呼ばれる) は、元のソリューションのすべての機能を提供しますが、現在では、他の Microsoft 365 サービスのコンテンツを識別し、そのコンテンツを収集し、レビュー担当者が高速検索クエリ、タグ付け、分析機能を利用して関連ドキュメントを作成できるレビュー セットに追加するカストディアン ベースのアプローチが含まれています。 Advanced eDiscovery には、Microsoft と Microsoft 以外の両方のファイルの種類の処理とネイティブ ビューアーが改善されました。ファイルの種類の完全な一覧が [ここに](https://docs.microsoft.com/microsoft-365/compliance/supported-filetypes-ediscovery20) 記載され、サポートされているメタデータ フィールドがここに [含まれています](https://docs.microsoft.com/microsoft-365/compliance/document-metadata-fields-in-advanced-ediscovery)。 また、新しい Advanced eDiscovery ソリューションは強力な保管担当者保留管理機能を提供します。この管理機能を使用すると、さまざまなサービスのコンテンツに保留を適用し、保留をユーザーに通知し、保管担当者の応答を追跡できます。

Advanced eDiscovery v2.0 へのアクセス

1. [Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) にアクセスします。

2. Microsoft 365 コンプライアンス センターの左側のナビゲーション ウィンドウで、[**すべてを表示**] をクリックし、**[eDiscovery] > [Advanced]** をクリックします。

現時点では、電子情報開示ワークフローの新しい Advanced eDiscovery 機能への移行を開始することをお勧めします。 必要に応じて、コンテンツをエクスポートしてオフラインで保存することで、Advanced eDiscovery 1.0 ケースをアーカイブできます。 既存のケースでは、2020 年 12 月 31 日まで Advanced eDiscovery v1.0 に引き続きアクセスすることができますが、2020 年 10 月 1 日以降、Microsoft サポートはサポートを提供し続けなかった。 詳細については、次のタイムラインを参照してください。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365 および Microsoft 365 Enterprise 組織

- Office 365 および Microsoft 365 Education 組織

- Office 365 および Microsoft 365 Government 組織これには、GCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: 新しい Advanced eDiscovery v1.0 ケースを作成できない。

- 2020 年 10 月 1 日: 新しいデータ (Advanced eDiscovery の検索結果を準備する) をケースに追加できない。 既存のケースでは、自分のリスクでデータの操作を続行できます。 Microsoft サポートはサポートを提供しなくなりました。 

- 2020 年 12 月 31 日: Advanced eDiscovery v1.0 ケースにアクセスできない。

### <a name="alternative-tools"></a>代替ツール

Microsoft 365 コンプライアンス センターの Advanced [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) ソリューション。
