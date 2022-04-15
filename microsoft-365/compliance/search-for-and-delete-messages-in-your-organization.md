---
title: 組織内の電子メールメッセージの検索と削除
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Microsoft 365 コンプライアンス センターの検索と消去機能を使って、組織のすべてのメールボックスからメール メッセージを検索し、削除できます。
ms.openlocfilehash: 8d283148b0a0cee0aed3d91a6332c96bd31111b4
ms.sourcegitcommit: a7e1d155939e862337271fbe38bf26f62bd49bdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846970"
---
# <a name="search-for-and-delete-email-messages"></a>メール メッセージを検索して削除する

**この記事は管理者向けです。メールボックスで削除するアイテムを探している場合は、「[クイック検索を使ってメッセージまたはアイテムを検索する](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**」を参照してください。

コンテンツ検索機能を使って、組織のすべてのメールボックスにあるメール メッセージを検索し、削除できます。これは、次に示す潜在的に有害または高リスクのメールを見つけて削除するのに役立ちます。

- 危険性のある添付ファイルやウイルスを含むメッセージ

- フィッシング メッセージ

- 機密データを含むメッセージ

> [!TIP]
> 組織に Office 365 プラン 2 の Defender サブスクリプションがある場合は、この記事で説明する手順に従うのではなく、[Office 365 で配信された悪意のあるメールの修復](/microsoft-365/security/office-365-security/remediate-malicious-email-delivered-office-365)に関する手順を使用することをお勧めします。

## <a name="before-you-begin"></a>始める前に

- この記事で説明されている検索と消去のワークフローでは、Microsoft Teams からチャット メッセージやその他のコンテンツは削除されません。 手順 2 で作成したコンテンツ検索で Microsoft Teams からアイテムが返された場合、手順 3 でアイテムを消去しても、それらのアイテムは削除されません。 チャット メッセージを検索および削除するには、「[ Teams でのチャット メッセージの検索と消去](search-and-delete-Teams-chat-messages.md)」 を参照してください。

- コンテンツ検索を作成して実行するには、**電子情報開示マネージャー** ロール グループのメンバーであるか、Microsoft 365 コンプライアンス センターの **コンプライアンス検索** ロールが割り当てられている必要があります。メッセージを削除するには、**組織の管理** 役割グループのメンバーであるか、Microsoft 365 コンプライアンス センターで **検索と消去** の役割が割り当てられている必要があります。ユーザーを役割グループに追加する方法の詳細については、「[電子情報開示権限を割り当てる](assign-ediscovery-permissions.md)」をご覧ください。

  > [!NOTE]
  > **組織の管理** ロール グループは、Exchange Online と Microsoft 365 コンプライアンス センターの両方にあります。 これらは、異なる権限を持つ個別の役割グループです。 Exchange Online で **組織の管理** のメンバーであっても、メール メッセージを削除するために必要なアクセス許可は付与されません。 Microsoft 365 コンプライアンス センターで **検索と消去** の役割が (直接、または **組織の管理** などの役割グループを通じて) 割り当てられていない場合、手順 3 で **New-ComplianceSearchAction** コマンドレットを実行し、"パラメーター名 'Purge' と一致するパラメーターが見つかりません" というエラー メッセージが表示されます。

- メッセージを削除するには、セキュリティ/コンプライアンス センターの PowerShell を使用する必要があります。 接続方法については、[手順 1](#step-1-connect-to-security--compliance-center-powershell) を参照してください。

- メールボックスごとに最大 10 個のアイテムを一度に削除できます。メッセージを検索および削除する機能はインシデント対応ツールとして作られているので、この制限によってメールボックスからメッセージをすばやく削除できます。これは、ユーザーのメールボックスをクリーン アップするための機能ではありません。

- コンテンツ検索で検索と削除アクションを実行してアイテムを削除するために使用できるメールボックスの最大数は 50,000 個です。 検索 ([手順 2](#step-2-create-a-content-search-to-find-the-message-to-delete) で作成) で 50,000 個を超えるメールボックスを検索する場合、削除アクション (手順 3 で作成) は失敗します。 1 回の検索で 50,000 個を超えるメールボックスを検索するのは、通常、組織内のすべてのメールボックスを検索に含めるように構成した場合です。 この制限は、検索クエリに一致するアイテムが 50,000 個未満のメールボックスに含まれている場合でも適用されます。 検索のアクセス許可を使用して 50,000 個を超えるメールボックスからアイテムを検索および消去する方法については、「[詳細情報](#more-information)」セクションを参照してください。

- この記事の手順は、Exchange Online のメールボックスとパブリック フォルダーにあるアイテムを削除する場合にのみ使用できます。 SharePoint や OneDrive for Business のサイトからコンテンツを削除する場合には使用できません。

- Advanced eDiscovery ケースのレビュー セット内のメール アイテムは、この記事の手順で削除することはできません。 これは、レビュー セット内のアイテムはライブ サービスではなく、Azure ストレージの場所に保存されるからです。 これは、手順 1 で作成したコンテンツ検索では返されないことを意味します。 レビュー セット内のアイテムを削除するには、レビュー セットが含まれている Advanced eDiscovery ケースを削除する必要があります。 詳細については、「[Close or delete an Advanced eDiscovery case (Advanced eDiscovery ケースを閉じるか、または削除する)](close-or-delete-case.md)」を参照してください。

## <a name="step-1-connect-to-security--compliance-center-powershell"></a>手順 1: セキュリティ/コンプライアンス センターの PowerShell に接続する

最初の手順は、組織のセキュリティ/コンプライアンス センターの PowerShell に接続することです。 詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](/powershell/exchange/connect-to-scc-powershell)」を参照してください。

## <a name="step-2-create-a-content-search-to-find-the-message-to-delete"></a>手順 2: コンテンツ検索を作成して、削除するメッセージを探す

2 番目の手順は、組織のメールボックスから削除するメッセージを見つけるコンテンツ検索を作成し、実行することです。Microsoft 365 コンプライアンス センターを使用するか、セキュリティ/コンプライアンス PowerShell の **New-ComplianceSearch** コマンドレットと **Start-ComplianceSearch** コマンドレットを実行すると、検索を作成できます。[手順 3](#step-3-delete-the-message) で **New-ComplianceSearchAction** コマンドを実行すると、この検索のクエリに一致するメッセージは削除されます。コンテンツ検索を作成し、検索クエリを構成する方法については、次のトピックを参照してください。

- [Office 365 のコンテンツ検索](content-search.md)

- [コンテンツ検索のキーワード クエリ](keyword-queries-and-search-conditions.md)

- [New-ComplianceSearch](/powershell/module/exchange/New-ComplianceSearch)

- [Start-ComplianceSearch](/powershell/module/exchange/Start-ComplianceSearch)

> [!NOTE]
> この手順で作成するコンテンツ検索で検索されるコンテンツの場所に、SharePoint や OneDrive for Business のサイトを含めることはできません。 メール メッセージに使われるコンテンツ検索には、メールボックスとパブリック フォルダーのみを含めることができます。 コンテンツ検索にサイトが含まれる場合、**New-ComplianceSearchAction** コマンドレットを実行すると、手順 3 でエラーが発生します。

### <a name="tips-for-finding-messages-to-remove"></a>削除するメッセージを見つけるためのヒント

検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。

- メッセージの件名に使われているテキストまたはフレーズを正確に記憶している場合は、検索クエリの **Subject** プロパティをご利用ください。

- メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。

- メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。

- 検索結果をプレビューして、検索が、削除を希望するメッセージだけを返したことを確認します。

- 検索見積もりの統計情報 (Microsoft 365 コンプライアンス センターの検索の詳細ウィンドウや、[Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch) コマンドレットを使用して表示される情報) を使用して、結果の合計数のカウントを取得します。

不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。

- このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。

  ```powershell
  (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
  ```

- このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。

  ```powershell
  (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
  ```

次に示す例では、**New-ComplianceSearch** コマンドレットと **Start-ComplianceSearch** コマンドレットを実行することにより、クエリを使用して検索を作成して開始し、組織内のすべてのメールボックスを検索します。

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-3-delete-the-message"></a>手順 3: メッセージを削除する

コンテンツ検索を作成して、削除するメッセージを返すように検索条件を絞りこんだ後は、最後に Security/Compliance PowerShell の **New-ComplianceSearchAction -Purge** コマンドレットを実行して、メッセージを削除します。 メッセージは、論理的に削除することも、物理的に削除することもできます。 論理的に削除したアイテムは、ユーザーの [回復可能なアイテム] フォルダーに移動され、削除済みアイテムの保持期間が切れるまで保持されます。 物理的に削除したメッセージは、メールボックスから完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に完全に削除されます。 そのメールボックスで単一アイテムの回復が有効になっている場合、物理的に削除したアイテムは、削除済みアイテムの保持期間が切れると完全に削除されます。 メールボックスが保留中になっている場合は、削除したメッセージは、そのアイテムの保留期間が切れるか、その保留がメールボックスから削除されるまで保持されます。

> [!NOTE]
> 前述のように、 **New-ComplianceSearchAction -Purge** コマンドを実行しても、コンテンツ検索によって返される Microsoft Teams のアイテムは削除されません。

次のコマンドを実行してメッセージを削除するには、[セキュリティ/コンプライアンス センター PowerShell に接続](/powershell/exchange/connect-to-scc-powershell)していることを確認して下さい。

### <a name="soft-delete-messages"></a>メッセージの論理的な削除

次の例では、"Remove Phishing Message" (フィッシング メッセージの削除) という名前のコンテンツ検索によって返された検索結果が、そのコマンドによって論理的に削除されます。

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

### <a name="hard-delete-messages"></a>メッセージの物理的な削除

"Remove Phishing Message" コンテンツ検索によって返されたアイテムを物理的に削除するには、次のコマンドを実行します:

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

前のコマンドを実行してメッセージを論理的または物理的に削除する場合、*SearchName* パラメーターで指定される検索は、手順 1 で作成したコンテンツ検索になります。

詳細については、「[New-ComplianceSearchAction](/powershell/module/exchange/New-ComplianceSearchAction)」を参照してください。

## <a name="more-information"></a>詳細情報

- **検索と削除の操作の状態を取得するにはどうすればよいですか?**

  **Get-ComplianceSearchAction** を実行して、削除操作の状態を取得します。**New-ComplianceSearchAction** コマンドレットを実行したときに作成されるオブジェクトは、`<name of Content Search>_Purge` という形式を使って名前が付けられます。

- **メッセージを削除するとどうなりますか?**

  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` コマンドを使用して削除されたメッセージは、Purges フォルダーに移動され、ユーザーはアクセスできなくなります。 Purges フォルダーに移動されたメッセージは、そのメールボックスで単一アイテムの回復が有効になっている場合、削除済みアイテムの保持期間が切れるまで保持されます。 (Microsoft 365 では、新しいメールボックスを作成すると、既定で単一アイテムの回復が有効になります)。削除済みアイテムの保持期間を過ぎると、そのメッセージは完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に Microsoft 365 から消去されます。

  `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` コマンドを使用すると、メッセージは、ユーザーの回復可能なアイテム フォルダーの Deletions フォルダーに移動されます。すぐに Microsoft 365 から削除されることはありません。ユーザーは、メールボックス用に構成された削除済みアイテムの保持期間に基づく期間、[削除済みアイテム] フォルダーにあるメッセージを回復できます。この保持期間が過ぎると (または過ぎる前にユーザーがメッセージを削除すると)、メッセージは Purges (消去) フォルダーに移動し、ユーザーはアクセスできなくなります。Purges (消去) フォルダーに移動すると、メールボックスで単一アイテムの回復が利用できれば、メールボックス用に構成された削除済みアイテムの保持期間に基づく期間、再度保持できます。(Microsoft 365 では、新しいメールボックスが作成されると、単一アイテムの回復が既定で利用できます。) 削除済みアイテムの保持期間が過ぎると、メッセージが完全な削除対象としてマークされ、次回管理フォルダー アシスタントによってメールボックスが処理されたときに Microsoft 365 から削除されます。

- **50,000 を超えるメールボックスからメッセージを削除するにはどうすればよいですか?**

  前述のとおり、検索と削除の操作を実行できるメールボックスの上限は 50,000 です (検索クエリに一致するアイテムが 50,000 個未満の場合でも)。 50,000 を超えるメールボックスに対して検索と削除の操作を実行する必要がある場合は、検索対象となるメールボックスの数を 50,000 未満に減らす一時的な検索権限フィルターを作成することをご検討ください。 たとえば、異なる部署、都道府県、国のメールボックスが組織内にある場合、そのようなメールボックスのプロパティのいずれかを基にメールボックスの検索権限フィルターを作成して、組織のメールボックスのサブセットを検索できます。 検索権限フィルターを作成したら、検索を作成 (手順 1 を参照) し、メッセージを削除 (手順 3 を参照) します。 その後、フィルターを編集し、別のメールボックスのセット内のメッセージを検索して削除できます。 検索権限フィルターの作成の詳細については、「[コンテンツ検索用にアクセス許可フィルターを設定する](permissions-filtering-for-content-search.md)」を参照してください。

- **検索結果に含まれるインデックスのないアイテムも削除されますか?**

  いいえ。`New-ComplianceSearchAction -Purge コマンドでは、インデックスのないアイテムは削除されません。

- **メッセージが、インプレース ホールドまたは訴訟ホールドが設定されたメールボックスから削除されたり、Microsoft 365 の保持ポリシーに割り当てられたりするとどうなりますか?**

  メッセージを消去し、削除フォルダーに移動した後、メッセージはホールド期間が過ぎるまで保存されます。ホールド期間が無期限である場合は、ホールドが解除されるか、またはホールド期間が変更されるまで、アイテムは保持されます。

- **検索と削除のワークフローが、セキュリティ/コンプライアンス センターのさまざまなロール グループに分けられているのはなぜですか?**

  これまでにご説明したとおり、メールボックスを検索するには、ユーザーは電子情報開示管理者ロール グループのメンバーであるか、コンプライアンス検索管理者ロールが割り当てられている必要があります。メッセージを削除するには、組織の管理者ロール グループのメンバーであるか、検索と消去の管理者ロールが割り当てられている必要があります。これにより、組織内でメールボックスを検索できる人と、メッセージを削除できる人とを制御できます。
