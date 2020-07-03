---
title: Advanced eDiscovery の保留を管理する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 保管担当者およびそのデータソースに保持を配置して、高度な電子情報開示ケースに関連するコンテンツを保持する方法について説明します。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f56d12b6d69e56e85f0e7ad37fbf65746a1cff23
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024737"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Advanced eDiscovery の保留を管理する

高度な電子情報開示ケースを使用して、ケースに関連する可能性があるコンテンツを保持するためのホールドを作成できます。 高度な電子情報開示の保持機能を使用すると、保管担当者とそのデータソースに保持を配置できます。 さらに、メールボックスおよび OneDrive for Business サイトに、非 wi-fi ダイヤルを保持することができます。 また、Microsoft 365 グループのグループメールボックス、SharePoint サイト、OneDrive for Business サイトにホールドを配置することもできます。 同様に、Microsoft Teams に関連付けられているメールボックスおよびサイトにホールドを配置することができます。 コンテンツの場所を保持する場合、コンテンツは保管担当者を解放するか、特定のデータの場所を削除するか、保留ポリシー全体を削除するまで保持されます。

## <a name="manage-custodian-based-holds"></a>保管担当者ベースの保持を管理する

場合によっては、保管担当者のセットを特定し、ケース時にデータを保持することを決定している場合があります。 上級電子情報開示では、これらの保管担当者が保留になっていると、ユーザーと選択されたデータソースが保管担当者保留ポリシーに自動的に追加されます。

保管担当者ホールドポリシーを表示するには、次のようにします。

1. Microsoft 365 コンプライアンスセンターで、[**電子情報開示 > 詳細設定**] をクリックして、組織内のケースの一覧を表示します。

2. ケース内に保管担当者を追加するには、[**ソース**] タブに移動します。 高度な電子情報開示ケース内で保管担当者を追加して保存する方法については、「 [Add 保管担当者 to a case」を](add-custodians-to-case.md)参照してください。 保管担当者を既に追加していて、保留リストに配置している場合は、手順3に進みます。

3. [**保留**] タブに移動し、[ **Custodianhold \<HoldId> **] をクリックします。

4. フライアウトページには、ポリシーの [ホールド] の統計が表示されます。 また、保管担当者ベースのホールドにクエリを適用するなどの操作を実行することもできます。 保留クエリの作成と条件の使用の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。

## <a name="manage-non-custodial-holds"></a>非 wi-fi ダイヤルの保持を管理する

保留リストを作成するときに、指定されたコンテンツの場所に保持されているコンテンツの範囲を指定する場合は、次のオプションがあります。

- You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.
  
- You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.

高度な電子情報開示ケースに対して、非 custodial ホールドを作成するには、次のようにします。

1. Microsoft 365 コンプライアンスセンターで、[**電子情報開示 > 詳細設定**] をクリックして、組織内のケースの一覧を表示します。
  
2. 保留リストを作成するケースの横の [**開く**] をクリックします。
  
3. 大文字と小文字のホームページから、[**保留**] タブをクリックします。
  
4. [**保留**] タブで、[**作成**] をクリックします。
  
5. [**保留リストに名前**を付ける] ページで、ホールドに名前を付けます。 ホールドの名前は組織内で一意である必要があります。
 
6. (省略可能) [**説明 **] ボックスで、保留リストの説明を追加します。
  
7. [**次へ**] をクリックします。
  
8. Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold.

   1. **Exchange 電子メール**-[**ユーザー、グループ、またはチームの選択**] をクリックし、[**ユーザー、グループ、または teams**を再度選択する] をもう一度クリックして、保持するメールボックスを指定します。 検索ボックスを使用して、ユーザーのメールボックスと配布グループを検索します (グループメンバーのメールボックスを保留にする場合)。 また、Microsoft 365 グループまたは Microsoft チームに対して、関連付けられたメールボックスにホールドを配置することもできます。 [ユーザー、グループ、チーム] チェックボックスをオンにし、[**選択**] をクリックし、[**完了**] をクリックします。
 
      > [!NOTE]
      > When you click **Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.

   1. **Sharepoint サイト**-[**サイトの選択**] をクリックし、[**サイトの選択**] をもう一度クリックして、保持する SharePoint および OneDrive for business サイトを指定します。 保持する各サイトの URL を入力します。 また、Microsoft 365 グループまたは Microsoft チームの SharePoint サイトの URL を追加することもできます。 [**選択**] をクリックし、[**完了**] をクリックします。
    
      Microsoft 365 グループと Microsoft Teams を保持する方法に関するヒントについては、 **FAQ**のセクションを参照してください。

      > [!NOTE]
      > ユーザーの OneDrive アカウントの URL には、ユーザープリンシパル名 (UPN) が含まれています (例: `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` )。 まれに、ユーザーの UPN が変更された場合、その OneDrive の URL も新しい UPN を組み込むように変更されます。 ユーザーの OneDrive アカウントが非 wi-fi ダイヤルホールドの一部であり、その UPN が変更されている場合は、保留リストを更新して新しい OneDrive URL を指定する必要があります。 詳細については、「[UPN の変更による OneDrive URL への影響](https://docs.microsoft.com/onedrive/upn-changes)」をご覧ください。

   1. **Exchange パブリックフォルダー** -切り替えスイッチをすべての位置に移動して、Exchange Online 組織内のすべてのパブリックフォルダーを保持します。 特定のパブリックフォルダーを保持の対象にすることはできないことに注意してください。 パブリックフォルダーを保持しない場合は、トグルスイッチを **[なし**] のままにします。

9. 保留リストにコンテンツの場所を追加し終わったら、[**次へ**] をクリックします。
  
10. 条件を使用してクエリベースの保持を作成するには、次の手順を実行します。 それ以外の場合は、[**次へ**] をクリックします。
    
    - 検索条件に一致するコンテンツのみが保持されるようにするには、[**キーワード**] の下のボックスに検索クエリを入力します。 ファイル名などの、キーワード、メッセージプロパティ、またはドキュメントプロパティを指定できます。 ブール演算子 (AND、OR、NOT など) を使用するより複雑なクエリを使用することもできます。 [キーワード] ボックスを空白のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが保持されます。

    - [条件の**追加**] をクリックして、1つまたは複数の条件を追加して、保留リストの検索クエリを絞り込みます。 各条件は、保留を作成するときに作成および実行される KQL 検索クエリに句を追加します。 たとえば、日付範囲を指定して、指定した期間内に作成された電子メールまたはサイトのドキュメントが保留リストに配置されるようにすることができます。 条件は、AND 演算子によってキーワードのクエリ (キーワード ボックスで指定される) と論理的に接続されます。 これは、アイテムがキーワードクエリと条件の両方に一致する必要があることを意味します。

     検索クエリの作成と条件の使用の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions)」を参照してください。

11. クエリ ベースの保留リストを構成した後、[**次へ**] をクリックします。

12. 設定を確認し、[**この保留リストを作成**] をクリックします。

## <a name="view-hold-statistics"></a>保留の統計を表示する

しばらくすると、選択した保留リストの [**保留**] タブの [詳細] ウィンドウに、新しい保留リストに関する情報が表示されます。 この情報には、保留になっているアイテムの合計数とサイズ、保持統計情報が最後に計算されたときなど、保留中のコンテンツに関するメールボックスとサイトの数および統計情報が含まれます。 これらの保持統計情報は、電子情報開示ケースに関連するコンテンツの量を特定するのに役立ちます。

保留アイテムの統計情報については、次の点に注意してください。

- The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.
  
- The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md). 

- 最新の保持統計情報を取得するには、[統計情報の更新] をクリックして、保留中の現在のアイテム数を計算する検索推定を再度実行します。

- 必要に応じて、ツールバーの [更新] をクリックして、[詳細] ウィンドウで保持の統計情報を更新します。

- 通常、保留にされているアイテム数は時間と共に増えます。これは、メッセージ ボックスまたはサイトが保留にされているユーザーは、一般的に新しいメール メッセージを送受信し、新しい SharePoint および OneDrive for Business ドキュメントを作成するためです。

- If a SharePoint site or OneDrive account is moved to a different region in a multi-geo environment, the statistics for that site won't be included in the hold statistics. However, the content in the site will still be on hold. Also, if a site is moved to a different region the URL that's displayed in the hold will not be updated. You'll have to edit the hold and update the URL.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Microsoft Teams と Office 365 グループにホールドを適用する

Microsoft Teams は、Office 365 グループ上に構築されています。 そのため、高度な電子情報開示でそれらを保持することは非常によく似ています。 

- **追加の Microsoft 365 グループまたは Microsoft Teams サイトを保管担当者にマップするにはどうすればよいですか?また、Microsoft 365 グループと Microsoft Teams には、非 wi-fi ダイヤルを含めることができます。** Microsoft Teams は、Microsoft 365 グループに基づいて構築されています。 そのため、電子情報開示ケースでそれらを保持することは非常によく似ています。 Microsoft 365 グループと Microsoft Teams を保留にする場合は、次の点に注意してください。
  - Microsoft 365 グループおよび Microsoft Teams にあるコンテンツを配置するには、グループまたはチームに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。
  
  - Microsoft 365 グループまたは Microsoft teams のプロパティを表示するには、Exchange Online で**set-unifiedgroup**コマンドレットを実行します。 これは、Microsoft 365 グループまたは Microsoft チームに関連付けられているサイトの URL を取得するための適切な方法です。 たとえば、次のコマンドは、上級管理職チームという名前の Microsoft 365 グループの選択されたプロパティを表示します。


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Get-UnifiedGroup コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。

 - ユーザーのメールボックスを検索すると、そのユーザーがメンバーになっている Microsoft 365 グループまたは Microsoft チームは検索されません。 同様に、Microsoft 365 グループまたは Microsoft teams ホールドを配置すると、グループメールボックスとグループサイトのみが保持されます。グループメンバーのメールボックスと OneDrive for Business サイトは、保管担当者として明示的に追加したり、データソースを保持したりしない限り、保留リストには置かれません。 そのため、特定の保管担当者に対して Microsoft 365 グループまたは Microsoft teams を保持する必要がある場合は、グループメールボックスとグループメールボックスを保管担当者にマッピングすることを検討してください (「Advanced eDiscovery での保管担当者の管理」を参照してください)。 Microsoft 365 グループまたは Microsoft チームが1つの保管担当者に属さない場合は、そのソースを非 custodial ホールドに追加することを検討してください。 
 
 - Microsoft 365 グループまたは Microsoft チームのメンバーの一覧を取得するには、Microsoft 365 管理センターの [ホーム > グループ] ページでプロパティを表示します。 または、Exchange Online PowerShell で次のコマンドを実行できます。

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > **Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。

- Microsoft Teams チャネルの一部であるチャネル会話は、チームに関連付けられているメールボックスに格納されます。 同様に、メンバーがチャネルで共有するファイルは、チームの SharePoint サイトに保存されます。 そのため、チャネル内の会話やファイルを保持するには、Microsoft teams メールボックスと SharePoint サイトを保留にする必要があります。
  
- または、Microsoft Teams のチャットリストに含まれる会話が、チャットに参加しているユーザーのメールボックスに保存されます。  ユーザーがチャット会話で共有しているファイルは、そのファイルを共有しているユーザーの OneDrive for Business サイトに保存されます。 そのため、会話やファイルをチャットリストに保持するには、個々のユーザーメールボックスと OneDrive for Business サイトを保持する必要があります。 
  
- Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.

  > [!NOTE]
  > The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.
