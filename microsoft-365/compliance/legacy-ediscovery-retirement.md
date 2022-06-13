---
title: 従来の電子情報開示ツールが廃止されました
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: admindeeplinkCOMPLIANCE
description: Exchange OnlineのIn-Place電子情報開示とIn-Placeホールド (および対応する PowerShell コマンドレット) は、2020 年前半に廃止されます。 Search-Mailbox コマンドレットと Microsoft Purview 電子情報開示 (プレミアム) v1.0 も同じ期間内に廃止されます。
ms.openlocfilehash: 36883f7edae391ff3461d5d6c135112a4f058671
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012286"
---
# <a name="retirement-of-legacy-ediscovery-tools"></a>従来の電子情報開示ツールの廃止

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

> [!IMPORTANT]
> この記事で説明する従来の電子情報開示ツールの機能は、Microsoft 365 サービスから削除されたか、引き続き使用できますが、サポートされなくなりました。 引き続き使用可能な機能は、予告なしに削除される可能性があります。 これらのレガシ ツールのいずれかを引き続き使用している場合は、Microsoft Purview コンプライアンス ポータルまたはこの記事で説明する代替ツールの 1 つで電子情報開示ツールに移行することを検討してください。

長年にわたり、Microsoft は電子情報開示ツールを提供してきました。このツールを使用すると、Exchange Onlineから電子メール コンテンツを検索、プレビュー、エクスポートできます。 ただし、これらのツールは、SharePoint Online やMicrosoft 365 グループなど、他のMicrosoft 365 サービス内の非Exchange コンテンツを検索する効果的な方法を提供しなくなりました。 これに対処するために、Microsoft では、さまざまなMicrosoft 365コンテンツを検索するのに役立つ他の電子情報開示ツールを提供しています。 また、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">コンプライアンス ポータル</a>に最新かつ強力な電子情報開示機能を組み込むために努力してきました。 これにより、組織は、Exchange Onlineを含む多くのMicrosoft 365 サービスにわたって、コンテンツに対する法的、内部、その他のドキュメント要求に対応できます。

コンプライアンス ポータルでのこの新機能と改善された電子情報開示機能の結果として、Exchange OnlineおよびMicrosoft 365での電子メール コンテンツの検索に関連する次の電子情報開示関連の機能が廃止されます。

- Exchange 管理センターの[インプレース電子情報開示](/exchange/security-and-compliance/in-place-ediscovery/in-place-ediscovery)および[インプレース ホールド](/exchange/security-and-compliance/create-or-remove-in-place-holds)。

- 電子情報開示とIn-Place保留をサポートする In-Place Exchange Online PowerShell コマンドレット (これらのコマンドレットは、まとめて **-MailboxSearch* コマンドレットとして識別されます)。 これには、次のコマンドレットが含まれます。

  - [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)

  - [Start-MailboxSearch](/powershell/module/exchange/start-mailboxsearch)

  - [Stop-MailboxSearch](/powershell/module/exchange/stop-mailboxsearch)

  - [Set-MailboxSearch](/powershell/module/exchange/set-mailboxsearch)

   > [!NOTE]
   > [Get-MailboxSearch](/powershell/module/exchange/get-mailboxsearch) コマンドレットと [Remove-MailboxSearch](/powershell/module/exchange/remove-mailboxsearch) コマンドレットは、他の ****-MailboxSearch*** コマンドレットが廃止された後に使用できるため、他の電子情報開示および保持ツールへの移行に役立ちます。 ただし、特定の日付 (以下に引用) の後、Microsoft サポートはこれら 2 つのコマンドレットをサポートしなくなります。

- Exchange Online PowerShell の [Search-Mailbox](/powershell/module/exchange/search-mailbox) コマンドレット。

- Exchange Web Services API での次の操作。

   - [GetSearchableMailboxes](/exchange/client-developer/web-service-reference/getsearchablemailboxes-operation)

   - [SearchMailboxes](/exchange/client-developer/web-service-reference/searchmailboxes-operation)
   
   - [SetHoldOnMailboxes](/exchange/client-developer/web-service-reference/setholdonmailboxes-operation)

   - [GetHoldOnMailboxes](/exchange/client-developer/web-service-reference/getholdonmailboxes-operation)

- [Microsoft Purview 電子情報開示 (プレミアム) v1.0](./overview-ediscovery-20.md)。これは、コンプライアンス ポータルの Microsoft Purview 電子情報開示 (Standard) ケースを通じてアクセスされる電子情報開示 (プレミアム) の最初のバージョンです。 電子情報開示 (プレミアム) v1.0 の廃止は、電子情報開示 (Standard) ケースを作成および管理する機能には影響しません。

> [!NOTE]
> 廃止される電子情報開示機能は、クラウドベースのバージョンのMicrosoft 365とOffice 365にのみ適用されます。 オンプレミスバージョンのExchangeとSharePointの電子情報開示機能は、今後の通知まで引き続きサポートされます。

この記事の次のセクションでは、廃止される各機能に関するガイダンスを提供します。 廃止されたツールの代わりに使用できるタイムラインや代替ツールを含むこの情報。

## <a name="in-place-ediscovery-and-in-place-holds-in-the-exchange-admin-center"></a>Exchange管理センターで電子情報開示とIn-Place保留をIn-Placeする 

2017 年 7 月 1 日の元のお知らせに従って、Exchange管理センター (EAC) のIn-Place電子情報開示&保留機能は廃止されます。 EAC の [In-Place電子情報開示&保留] ページでは、Exchange Onlineからコンテンツを検索、保持、エクスポートできます。 In-Place電子情報開示を使用すると、検索結果を探索メールボックスにコピーして、自分や他の電子情報開示マネージャーがコンテンツを確認し、法的、規制上、および公的な要求に利用できるようにします。

これらのすべての機能 (検索結果を探索メールボックスにコピーする場合を除く) は、[コンプライアンス ポータル](./microsoft-365-compliance-center.md)のコンテンツ検索、電子情報開示、電子情報開示 (プレミアム) ツールで利用できるようになったため (機能、信頼性、および幅広いMicrosoft 365 サービスのサポートが強化されているため)、できるだけ早くこれらのツールの使用を開始することをお勧めします。 これらの他の電子情報開示ツールへの移行を支援するために、次の表に、電子情報開示とIn-Place保留の代わりに使用できるツールIn-Place示します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365組織とMicrosoft 365 Enterprise組織

- Office 365組織とMicrosoft 365 Education組織

- 政府機関Office 365およびMicrosoft 365。これにはGCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline-for-retirement"></a>退職のタイムライン

- 2020 年 7 月 1 日: 新しい検索と保留を作成することはできませんが、既存の検索は自分の責任で実行、編集、削除できます。 Microsoft サポートは、EAC で電子情報開示&保留をIn-Placeしなくなります。

- 2020 年 10 月 1 日: EAC のIn-Place電子情報開示&保留機能は読み取り専用モードになります。 これにより、可能な操作は、既存の検索および保留リストの削除のみになります。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。

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
<td>法的目的で検索、エクスポート、保持する</td>
<td>コンプライアンス ポータルでの電子情報開示 (Standard) ケース </td>
<td><p>電子情報開示 (Standard) ケースの機能を使用すると、電子情報開示とIn-Place保留をIn-Placeする機能パリティが提供されます。 エクスポートできるものには、次のようなものがあります。</p>
<ul>
<li>
<p>検索は数百万の場所にスケーリングされます</p>
</li>
<li>
<p>コンテンツの検索、エクスポート、および保留の信頼性の向上</p>
</li>
<li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Yammer グループ、Microsoft 365 グループのコンテンツの検索、およびOffice 365 アプリケーションに格納されているその他のコンテンツ</p></li></ul>
</td>
</tr>
<tr class="even">
<td>保持を目的として保持する</td>
<td>コンプライアンス ポータルのアイテム保持ポリシー</td>
<td><p>アイテム保持ポリシーを使用してコンテンツを保持し、必要に応じて保持期間が切れた後に削除することができます。 その他の機能は次のとおりです。</p>
<ul>
<li>
<p>組織全体にポリシーを適用する </p>
</li><li>
<p>Exchange Online、SharePoint Online、OneDrive for Business、Skype for Business、Microsoft Teams、Office 365 グループなどの特定のコンテンツの場所にポリシーを適用する</p></li>
<li>
<p>特定のユーザーにポリシーを適用する</p></li></ul>
<p>詳細については、「 <a href="/microsoft-365/compliance/retention-policies"> アイテム保持ポリシーと保持ラベルの詳細</a>」を参照してください。</td>
</tr>
<tr class="odd">
<td>電子メール検索結果を探索メールボックスにコピーして確認する</td><td>電子情報開示 (プレミアム) v2.0 でセットを確認する</td>
<td><p>Microsoft 365のコンテンツの確認は、これまでになく簡単になりました。 レビュー セットには、次のような、確認に必要な時間とデータの量を減らすのに役立つ優れた機能が多数用意されています。</p>
<ul>
<li><p>高速検索クエリを実行し、レビュー セット内のコンテンツをフィルター処理する</p></li>
<li><p>レビュー セット内のコンテンツを分析する。これには、電子メール スレッディング、ほぼ重複する検出、テーマ分析、予測コーディングが含まれます。</p></li>
<li><p>レビュー セット内のドキュメントをタグ付けする</p></li>
<li><p>弁護士クライアントの特権コンテンツを識別するのに役立つタグ付けの提案</p></li></ul>
<p>詳細については、<a href="/microsoft-365/compliance/overview-ediscovery-20">Microsoft 365の電子情報開示 (プレミアム) ソリューションの概要に関するページを</a>参照してください。</p>
<p>
<p>または、検索結果を PST ファイルにエクスポートし、Microsoft 365 Import サービスを使用して、検出メールボックスに PST をインポートすることもできます。 詳細な手順については、「<a href="/microsoft-365/compliance/use-network-upload-to-import-pst-files">ネットワーク アップロードを使用して PST ファイルをOffice 365にインポートする」を</a>参照してください。
</tr>
<tr class=even>
  <td>1 つのメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスにアクセス許可を割り当てる</a></td>
  <td>ユーザーに別のユーザーのメールへのアクセス権を付与するには (たとえば、従業員が組織を離れ、別のユーザーに元の従業員のメールへのアクセス権を付与する必要がある場合など)、元従業員のメールボックスにアクセスするためのアクセス許可をそのユーザーに割り当てることをお勧めします。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするために必要なアクセス許可をユーザーに割り当てるだけです。</td>
  
  </tr>
<tr class="odd">
<td>回復可能なアイテム フォルダーからアイテムを復元する</td>
  <td><a href="/powershell/module/exchange/Restore-RecoverableItems">Restore-RecoverableItems</td>
  <td>アイテムの削除済みアイテムの保持期間が経過していない限り、メールボックス内の完全に <i>削除されたアイテム (論理的に削除された</i> アイテムとも呼ばれます) を復元できます。 詳細については、「<a href="/Exchange/security-and-compliance/recoverable-items-folder/recoverable-items-folder">Exchange Onlineの回復可能なアイテム フォルダー</a>」を参照してください。</td>
</tr>
</tbody>
</table>

### <a name="faqs-about-in-place-ediscovery-and-in-place-holds"></a>インプレース電子情報開示とインプレース ホールドに関するよくある質問

**電子情報開示& EAC で保持するIn-Placeの検索結果のコピー機能を使用して、代理人による確認のために検索結果を探索メールボックスにコピーします。現在、どのようなオプションがありますか?**

この機能を現在レプリケートするには、2 つの方法があります。 1 つ目は、[電子情報開示 (プレミアム) v2.0 でレビュー セット](./view-documents-in-review-set.md)を使用します。 レビュー セットには、ドキュメントの高速検索、タグ付け、電子メール スレッド、ほぼ重複するグループ化、テーマ分析、予測コーディングなど、従来のレビュー ツールと同じ機能の多くがあります。 探索メールボックスを確認に使用する場合、2 番目のオプションは、検索結果を PST ファイルにエクスポートし、Microsoft コンプライアンス センターの PST [インポート機能](use-network-upload-to-import-pst-files.md) を使用して PST ファイルを探索メールボックスにインポートすることです。

**電子情報開示マネージャーが新しいツールを使用して検索できるコンテンツの場所 (メールボックスやサイトなど) を制御操作方法。**

コンプライアンス ポータルでは、 [コンプライアンス境界](set-up-compliance-boundaries.md) を使用して、電子情報開示マネージャーが検索できるコンテンツの場所も制御します。 コンプライアンスの境界は、政府機関の境界内に留まる必要がある政府機関や、地理的な境界を尊重するために必要な多国籍企業で役立ちます。

**現在の検索と保留を Microsoft Purview コンプライアンス ポータルに移動するにはどうすればよいですか?**

PowerShell を使用して、EAC から電子情報開示の検索と保留In-Place移行できます。 手順については、「 [EAC からコンプライアンス ポータルへの検索と保留の移行](./migrate-legacy-ediscovery-searches-and-holds.md)」を参照してください。

## <a name="-mailboxsearch-cmdlets"></a>\*-MailboxSearch コマンドレット

Exchange管理センターで 2017 年 7 月 1 日に発表された当初の通知に従って、In-Place電子情報開示&保留機能と対応する **\*-MailboxSearch** コマンドレットは廃止されます。 これらのコマンドレットを使用すると、ユーザーは、法的要求、規制、およびパブリック要求に対してメールボックス コンテンツを検索、保持、およびエクスポートできます。

これらの機能は[<span class="underline">、コンプライアンス ポータル</span>](./microsoft-365-compliance-center.md)とOffice 365 セキュリティ &コンプライアンス PowerShell で、パフォーマンスとスケーラビリティが向上しているため、これらの改善されたコマンドレットを使用する必要があります。 これらのコマンドレットには、-ComplianceCase、[<span class="underline">\*-ComplianceSearch</span>](/powershell/module/exchange/get-compliancesearch)、[<span class="underline">\*-CaseHoldPolicy</span>](/powershell/module/exchange/get-caseholdpolicy)、[<span class="underline">\*-CaseHoldRule</span>](/powershell/module/exchange/get-caseholdrule)、[<span class="underline">\*-ComplianceSearchAction が</span>](/powershell/module/exchange/get-compliancesearchaction)含[<span class="underline">\*</span>](/powershell/module/exchange/get-compliancecase)まれます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365組織とMicrosoft 365 Enterprise組織

- Office 365組織とMicrosoft 365 Education組織

- 政府機関Office 365およびMicrosoft 365。これにはGCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: **New-MailboxSearch** を使用して新しいIn-Place電子情報開示検索とIn-Place保留を作成することはできませんが、コマンドレットを使用して既存の検索と保持を実行、編集、削除することは、ご自身の責任で行うことができます。 Microsoft サポートは、このような種類の検索と保留のサポートを提供しなくなりました。

- 2020 年 10 月 1 日: 前述のように、EAC の電子情報開示&保留機能In-Placeは読み取り専用モードになります。 つまり、**New-MailboxSearch、Start-MailboxSearch**、または **Set-MailboxSearch** コマンドレットを使用することはできません。 取得および削除できるのは、既存の検索と保留のみです。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。

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
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは連携して、コンテンツの検索とエクスポートに役立ちます。 New、<strong>Get-</strong>、<strong>Start-ComplianceSearch</strong> コマンドレットを使用して、<strong></strong>新しい検索を作成し、検索の見積もりを表示できます。 次に、 <strong>New-ComplianceSearchAction</strong> コマンドレットを使用して検索結果をエクスポートできます。 コンプライアンス ポータルで電子情報開示 (Standard) ツールを使用して、それらの検索結果をローカル コンピューターにダウンロードする必要があります。</p>
<p>
<p><strong>メモ：</strong> これらのコマンドレットを使用して電子情報開示 (Standard) ケースに関連付けられていない検索を作成する場合、これらの検索はコンプライアンス ポータルの <strong>[コンテンツ検索</strong> ] ページにあります。</p></td>
</tr>
<tr class="even">
<td>メールボックス内のコンテンツを保持する</td>
<td><p><a href="/powershell/module/exchange/get-caseholdpolicy"><span class="underline">*-CaseHoldPolicy</span></a></p>
<p><a href="/powershell/module/exchange/get-caseholdrule"><span class="underline">*-CaseHoldRule</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancecase"><span class="underline">*-ComplianceCase</span></a></p>
<p> </p></td>
<td><p>コンプライアンス ポータルの保留は、ComplianceCase に関連付ける必要があります。 まず、コンプライアンス ケースを作成し、CaseHoldPolicy と CaseHoldRule を作成します。</p>
<p><strong>メモ：</strong> CaseHoldRule を作成せずに CaseHoldPolicy を作成すると、CaseHoldRule が作成されて CaseHoldPolicy に関連付けられるまでホールドが操作不能になります。 詳細については、コマンドレットのドキュメントを参照してください。</p></td>
</tr>
<tr class="odd">
<td>検索結果を探索メールボックスにコピーする</td>
<td>なし</td>
<td>この機能は、すべてのMicrosoft 365 サービスにアクセスできるわけではないため、直接置き換える必要はありません。 代替ソリューションについては、以下の FAQ を参照してください。</td>
</tr>
  <tr class=even>
  <td>1 つのメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスにアクセス許可を割り当てる</a></td>
  <td>ユーザーに別のユーザーのメールへのアクセス権を付与するには (たとえば、従業員が組織を離れ、別のユーザーに元の従業員のメールへのアクセス権を付与する必要がある場合など)、元従業員のメールボックスにアクセスするためのアクセス許可をそのユーザーに割り当てることをお勧めします。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てるだけです。</td>
  
  </tr>

</tbody>
</table>

### <a name="faqs-about--mailboxsearch-cmdlets"></a>***-MailboxSearch** コマンドレットに関する FAQ

**他の電子情報開示や法的調査を目的として、検索コピーを使用して電子メール メッセージまたはインスタント メッセージをエクスポートします。これらのコマンドレットが廃止された後、他にはどのようなオプションがありますか?**

[<span class="underline">Microsoft Graph API には</span>](https://developer.microsoft.com/en-us/graph)、**-MailboxSearch コマンドレットを使用するよりもはるかに回復性と拡張性を備えた分析やその他の目的でデータを\*** 抽出するためのさまざまな方法が用意されています。

**検索と保留をコンプライアンス ポータルに移行するにはどうすればよいですか?**

PowerShell スクリプトを使用して、Exchange管理センターから電子情報開示の検索と保留In-Place移行できます。 詳細については、「 [従来の電子情報開示の検索と保留をコンプライアンス ポータルに移行する」を参照してください](migrate-legacy-eDiscovery-searches-and-holds.md)。

**コマンドレットが廃止された後も、検索を削除または取得できますか?**

はい。検索を作成および変更する機能は削除されていますが、 **Get-MailboxSearch** と **Remove-MailboxSearch** は、今後の通知まで引き続き使用できます。 ただし、これらのコマンドレットの使用は、廃止日の後に自己責任で行われ、Microsoft サポートはサポートを提供できなくなります。

## <a name="search-mailbox-cmdlet"></a>Search-Mailbox コマンドレット

Exchange Online PowerShell の **Search-Mailbox** コマンドレットは、2018 年からコマンドレット出力の警告で最初に発表されたものとして廃止されます。 **Search-Mailbox** コマンドレットは、もともとユーザーのメールボックスを検索し、悪意のあるコンテンツを消去するために使用されていました。 コンテンツを検索および消去するには、**Office 365** Security & Compliance PowerShell の **New-ComplianceSearch コマンドレットと New-ComplianceSearchAction** コマンドレットの使用を開始することをお勧めします。 組み込みのセキュリティ エクスペリエンスのために、[<span class="underline">Microsoft 365 セキュリティ機能</span>](../security/index.yml)は、電子メールやその他の多くのMicrosoft サービスに対して堅牢な脅威保護を提供します。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365組織とMicrosoft 365 Enterprise組織

- Office 365組織とMicrosoft 365 Education組織

- 政府機関Office 365およびMicrosoft 365。これにはGCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

-  2020 年 7 月 1 日: **Search-Mailbox** コマンドレットは使用できなくなり、Microsoft サポートサポートは提供されなくなります。

### <a name="alternative-tools"></a>代替ツール

次の表では、廃止される既存の機能を置き換えるために使用できるその他のツールについて説明します。

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
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは連携して、コンテンツの検索とエクスポートに役立ちます。 New、<strong>Get-</strong>、<strong>Start-ComplianceSearch</strong> コマンドレットを使用して、<strong></strong>新しい検索を作成し、検索の見積もりを表示できます。 次に、 <strong>New-ComplianceSearchAction -Export</strong> コマンドを使用して検索結果をエクスポートできます。 コンプライアンス ポータルで電子情報開示 (Standard) ツールを使用して、それらの検索結果をローカル コンピューターにダウンロードする必要があります。</p></p>
</td>
</tr>
<tr class="even">
<td>メールボックスから一括メールを削除する</td>
<td><p><a href="/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes"><span class="underline">メールボックスのアーカイブと削除ポリシーを設定する</span></a></p>
<p></p></td>
<td><p>管理者は、アイテムをユーザーのアーカイブ メールボックスに自動的に移動し、メールボックスからアイテムを自動的に削除するアーカイブおよび削除ポリシーを作成できます。</p>
</td>
</tr>
<tr class="even">
<td>検索結果を探索メールボックスにコピーする</td>
<td> </td>
<td>この機能は、すべてのMicrosoft 365 サービスにアクセスできるわけではないため、直接置き換える必要はありません。 代替ソリューションについては、「 <strong>*-MailboxSearch コマンドレット</strong> 」セクションの FAQ を参照してください。 </td>
</tr>
<tr class=odd>
  <td>1 つのメールボックスから別のメールボックスにメッセージをコピーする</td>
  <td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスにアクセス許可を割り当てる</a></td>
  <td>ユーザーに別のユーザーのメールへのアクセス権を付与するには (たとえば、従業員が組織を離れ、別のユーザーに元の従業員のメールへのアクセス権を付与する必要がある場合など)、元従業員のメールボックスにアクセスするためのアクセス許可をそのユーザーに割り当てることをお勧めします。 そのため、メールボックス アイテムを別のユーザー メールボックスまたは共有メールボックスにコピーする代わりに、ソース メールボックスにアクセスするためのアクセス許可をユーザーに割り当てるだけです。</td>
</tr>
<tr class=even>
  <td>メールボックスからメッセージを消去する</td>
<td><p><a href="/powershell/module/exchange/get-compliancesearch"><span class="underline">*-ComplianceSearch</span></a></p>
<p><a href="/powershell/module/exchange/get-compliancesearchaction"><span class="underline">*-ComplianceSearchAction</span></a></p>
<p></p></td>
<td><p>ComplianceSearch コマンドレットと ComplianceSearchAction コマンドレットは連携して、コンテンツの検索と消去に役立ちます。 <strong>New-ComplianceSearch コマンドレットと New-ComplianceSearch</strong> コマンドレットを使用して検索を作成して実行し、<strong>New-ComplianceSearchAction -Purge -PurgeType</strong> コマンドを使用してコンテンツを消去できます。<strong></strong> 詳細については、「 <a href="/microsoft-365/compliance/search-for-and-delete-messages-in-your-organization"><span class="underline">メッセージの検索と削除</span></a>」を参照してください。</p>
</td>
</tr>
<tr class="odd"> 
<td>メールボックスからメッセージを消去する</td>
<td><a href="/exchange/recipients-in-exchange-online/manage-permissions-for-recipients">メールボックスにアクセス許可を割り当てる</a></td>
<td>メールボックスからメッセージを消去するには、管理者のアクセス許可を割り当てて従業員のメールボックスにアクセスします。 Outlookに組み込まれている検索機能と表示機能を利用して、必要に応じてメッセージを削除およびリサイクルできます。</td>
</tr>
</tbody>
</table>

## <a name="exchange-web-services-api-operations"></a>Exchange Web Services API 操作

Exchange Web Services API のこれらの操作は、Exchange管理センターのIn-Place電子情報開示&保留機能と、対応する **\*powerShell の -MailboxSearch** コマンドレットによって使用Exchange Online。 また、他の従来の電子情報開示ツールの廃止の一環として廃止されます。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365組織とMicrosoft 365 Enterprise組織

- Office 365組織とMicrosoft 365 Education組織

- 政府機関Office 365およびMicrosoft 365。これにはGCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: GetSearchableMailboxes、SearchMailboxes、SetHoldOnMailboxes、GetHoldOnMailboxes の各操作は使用できなくなり、Microsoft サポートサポートは提供されなくなります。

## <a name="ediscovery-premium-v10"></a>電子情報開示 (プレミアム) v1.0

電子情報開示 (プレミアム) v1.0 は、電子情報開示に切り替える (プレミアム) をクリックして電子情報開示 (Standard) ケースで使用できる **電子情報開示 (プレミアム**) のバージョンです。 その機能は、コンプライアンス ポータルの新しい[電子情報開示 (プレミアム) ソリューション](./ediscovery.md)に置き換えられました。

組織が電子情報開示 (プレミアム) v1.0 を使用しているかどうかを確認するには、

1. コンプライアンス ポータルに移動し、 **電子情報開示** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2174007" target="_blank">**コア**</a>を選択し、電子情報開示 (Standard) ケースを開きます。

1. [**電子情報開示に切り替える (プレミアム)]** ボタンが表示されたら、それをクリックすると、1.0 バージョンの電子情報開示 (プレミアム) に移行します。このバージョンは廃止されます。 電子情報開示 (Standard) でケースを作成および管理する機能は影響を受けることはありません。 電子情報開示 (プレミアム) v1.0 でケース データを追加および分析する機能 ([**電子情報開示に切り替える (プレミアム)]** をクリックする機能のみが廃止されます。

Microsoft 365の新しい電子情報開示 (プレミアム) ソリューション (*電子情報開示 (プレミアム) v2.0* とも呼ばれます) は、元のソリューションのすべての機能を提供しますが、他のMicrosoft 365のコンテンツを識別するカストディアンベースのアプローチが含まれています サービスを収集し、そのコンテンツを収集し、レビュー セットに追加して、レビュー担当者が高速検索クエリ、タグ付け、分析機能を利用して、関連するドキュメントをカリングできるようにします。 電子情報開示 (プレミアム) には、Microsoft と Microsoft 以外の両方のファイルの種類の処理とネイティブ ビューアーが強化されました。ファイルの種類の完全な一覧が[ここに](./supported-filetypes-ediscovery20.md)表示され、サポートされているメタデータ フィールドが[ここに表示](./document-metadata-fields-in-advanced-ediscovery.md)されます。 また、新しい電子情報開示 (プレミアム) ソリューションは、さまざまなサービスのコンテンツに保留を適用したり、保留をユーザーに通知したり、電子情報開示 (プレミアム) ケース内で管理担当者の応答を追跡したりできる強力なカストディアン保留管理機能を提供します。

電子情報開示 (Premium) v2.0 にアクセスするには:

コンプライアンス ポータルに移動し、 **電子情報開示** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2174006" target="_blank">**の詳細設定**</a>を選択し、電子情報開示 (Standard) ケースを開きます。

現時点では、電子情報開示ワークフローを新しい電子情報開示 (プレミアム) 機能に移行することをお勧めします。 必要に応じて、コンテンツをエクスポートしてオフラインで保存することで、電子情報開示 (プレミアム) 1.0 ケースをアーカイブできます。 既存のケースでは 2020 年 12 月 31 日まで電子情報開示 (プレミアム) v1.0 にアクセスできますが、Microsoft サポートは 2020 年 10 月 1 日以降はサポートを提供しません。 詳細については、次のタイムラインを参照してください。

### <a name="scope-of-affected-organizations"></a>影響を受ける組織の範囲

- Office 365組織とMicrosoft 365 Enterprise組織

- Office 365組織とMicrosoft 365 Education組織

- 政府機関Office 365およびMicrosoft 365。これにはGCC、GCC High、DoD が含まれます。

- Office 365 Germany

### <a name="timeline"></a>タイムライン

- 2020 年 7 月 1 日: 新しい電子情報開示 (プレミアム) v1.0 ケースを作成することはできません。

- 2020 年 10 月 1 日: 新しいデータ (電子情報開示の検索結果の準備 (プレミアム)) をケースに追加することはできません。 既存のケースでデータを引き続き操作することは、自己責任で行うことができるでしょう。 Microsoft サポートはサポートを提供しなくなります。 

- 2020 年 12 月 31 日: 電子情報開示 (プレミアム) v1.0 ケースにアクセスすることはできません。

### <a name="alternative-tools"></a>代替ツール

コンプライアンス ポータルの[電子情報開示 (プレミアム) ソリューション](./overview-ediscovery-20.md)。
