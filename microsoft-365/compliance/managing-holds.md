---
title: 電子情報開示で保留を管理する (Premium)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: 04/27/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 電子情報開示 (Premium) ケースに関連するコンテンツを保持するために、保管担当者とそのデータ ソースに保留を配置する方法について説明します。
ms.custom:
- seo-marvel-mar2020
- admindeeplinkMAC
ms.openlocfilehash: f7c47afe74c4d48036160d0fbb0c9717f884bc46
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66629445"
---
# <a name="manage-holds-in-ediscovery-premium"></a>電子情報開示で保留を管理する (Premium)

Microsoft Purview eDiscovery (Premium) ケースを使用して、ケースに関連する可能性があるコンテンツを保持する保留を作成できます。 電子情報開示 (Premium) ホールド機能を使用して、保管担当者とそのデータ ソースに保留を配置できます。 また、メールボックスとOneDrive for Business サイトに非親権ホールドを配置することもできます。 Microsoft 365 グループのグループ メールボックス、SharePoint サイト、OneDrive for Business サイトにホールドを配置することもできます。 同様に、Microsoft Teams に関連付けられているメールボックスとサイトにホールドを配置することもできます。 コンテンツの場所を保留にすると、保管担当者を解放するか、特定のデータの場所を削除するか、ホールド ポリシーを完全に削除するまで、コンテンツは保持されます。

## <a name="manage-custodian-based-holds"></a>カストディアンベースの保留を管理する

場合によっては、特定した一連のカストディアンがあり、ケース中にデータを保持することに決めたことがあります。 電子情報開示 (Premium) では、これらのカストディアンを保留にすると、ユーザーとその選択したデータ ソースが自動的にカストディアンホールド ポリシーに追加されます。

カストディアンホールド ポリシーを表示するには:

1. Microsoft Purview コンプライアンス ポータルで、[**電子情報開示>詳細設定**] をクリックして、組織内のケースの一覧を表示します。

2. [ **ソース]** タブに移動して、ケース内にカストディアンを追加します。 電子情報開示 (Premium) ケース内でカストディアンを追加して保留にする方法については、「ケース [にカストディアンを追加する」を](add-custodians-to-case.md)参照してください。 カストディアンを既に追加して保留にしている場合は、手順 3 に進みます。

3. **[保留]** タブに移動し、[**CustodianHold\<HoldId>**] をクリックします。

4. ポップアップ ページでは、カストディアン ベースのホールドにクエリを適用するなどのアクションを実行できます。 ホールド クエリの作成と条件の使用の詳細については、「 [コンテンツ検索のキーワード クエリと検索条件」を](keyword-queries-and-search-conditions.md)参照してください。

## <a name="manage-non-custodial-holds"></a>非親権保留を管理する

保留リストを作成するときに、指定されたコンテンツの場所に保持されているコンテンツの範囲を指定する場合は、次のオプションがあります。

- すべてのコンテンツが保留にされている場合、無限の保留リストを作成します。また、検索クエリに一致したコンテンツのみが保留にされている場合、クエリ ベースの保留リストも作成できます。
  
- 日付の範囲を指定して、その日付の範囲内に送信、受信、または作成したコンテンツのみを保留にすることができます。また、コンテンツがいつ送信、受信、作成されたかにかかわらず、すべてのコンテンツを保留にすることもできます。

電子情報開示 (Premium) ケースの非保管ホールドを作成するには:

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">コンプライアンス ポータル</a>で、[**電子情報開示>詳細設定**] をクリックして、組織内のケースの一覧を表示します。
  
2. 保留リストを作成するケースの横の [**開く**] をクリックします。
  
3. ケースのホーム ページで、[ **保留** ] タブをクリックします。
  
4. [ **保留]** タブで、[ **作成**] をクリックします。
  
5. [ **保留リストの名前]** ページで、保留リストに名前を付けます。 ホールドの名前は組織内で一意である必要があります。

6. (省略可能) [**説明**] ボックスで、保留リストの説明を追加します。
  
7. [**次へ**] をクリックします。
  
8. 保留にするコンテンツの場所を選択します。メールボックス、サイト、パブリック フォルダーを保留にできます。

   1. **Exchange メール** - [ **ユーザー、グループ、またはチームの選択]** をクリックし、もう一度 [ **ユーザー、グループ、またはチームの選択** ] をクリックして、保留にするメールボックスを指定します。 検索ボックスを使用して、ユーザーのメールボックス、および配布グループ (グループ メンバーのメールボックスにホールドを適用するため) を検索し、ホールドを適用します。 Microsoft 365 グループまたは Microsoft チームの関連メールボックスにホールドを配置することもできます。 ユーザー、グループ、チームのチェック ボックスをオンにし、[ **選択**] をクリックして、[完了] をクリック **します**。

      > [!NOTE]
      > [**ユーザー、グループ、またはチームの選択**] をクリックして保留にするメールボックスを指定するときに、表示されるメールボックス ピッカーは空の状態です。これは、パフォーマンスを向上させるための仕様です。このリストにユーザーを追加するには、検索ボックスに名前 (3 文字以上) を入力します。

   1. **SharePoint サイト** - [**サイトの選択]** をクリックし、[**サイトの選択**] をもう一度クリックして SharePoint を指定し、保持するサイトをOneDrive for Businessします。 ホールドを適用する各サイトの URL を入力します。 Microsoft 365 グループまたは Microsoft チームの SharePoint サイトの URL を追加することもできます。 [ **選択] を** クリックし、[完了] をクリック **します**。

      > [!NOTE]
      > ユーザーの OneDrive アカウントの URL には、ユーザー プリンシパル名 (UPN) (たとえば) `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com`が含まれています。 まれに、ユーザーの UPN が変更された場合、OneDrive URL も新しい UPN を組み込むために変更されます。 ユーザーの OneDrive アカウントが非親権保留リストの一部であり、その UPN が変更された場合は、保留を更新し、新しい OneDrive URL をポイントする必要があります。 詳細については、「[UPN の変更による OneDrive URL への影響](/onedrive/upn-changes)」をご覧ください。

   1. **Exchange パブリック フォルダー** - トグル スイッチを [すべて] の位置に移動して、Exchange Online組織内のすべてのパブリック フォルダーを保留にします。 ただし、ホールドにする特定のパブリック フォルダーを選ぶことはできません。 パブリック フォルダーを保持しない場合は、トグル スイッチを **[なし]** に設定したままにします。

9. 保留リストにコンテンツの場所を追加し終わったら、[**次へ**] をクリックします。
  
10. 条件を含むクエリ ベースのホールドを作成するには、次の手順を実行します。 それ以外の場合は、[ **次へ**] をクリックします。

    - [ **キーワード**] ボックスに検索クエリを入力し、検索条件に一致するコンテンツのみが保留になるようにします。 キーワード、メッセージ プロパティ、ドキュメント プロパティ (ファイル名など) を指定できます。 AND、OR、NOT などのブール演算子を使用する、より複雑なクエリを使用することもできます。 キーワード ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが保留されます。

    - [条件の  **追加]** をクリックして 1 つ以上の条件を追加し、保留リストの検索クエリを絞り込みます。 各条件は、保留リストの作成時に作成および実行される KQL 検索クエリに句を追加します。 たとえば、日付範囲を指定して、日付範囲内で作成された電子メールまたはサイト ドキュメントを保留にすることができます。 条件は、AND 演算子によってキーワードのクエリ (キーワード ボックスで指定される) と論理的に接続されます。 つまり、アイテムは、キーワード クエリと保留にする条件の両方を満たす必要があります。

     検索クエリの作成と条件の使用の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](/office365/SecurityCompliance/keyword-queries-and-search-conditions)」を参照してください。

11. クエリ ベースの保留リストを構成した後、[**次へ**] をクリックします。

12. 設定を確認し、[**この保留リストを作成**] をクリックします。

> [!NOTE]
> クエリ ベースのホールドを作成すると、選択した場所のすべてのコンテンツが最初に保留になります。 Exchange または SharePoint のタイマー ジョブが実行されると、指定したクエリに一致しないコンテンツはすべて保留から消去されます。 1 つの場所のすべてのクエリの文字数が 10,000 文字を超えると、場所全体が保留になります。 

> [!NOTE]
> ユーザーのメールボックスを保留にした後にユーザーの SMTP アドレスが変更された場合、メールボックスは保持されたままになります。 新しい SMTP アドレスを使用して保留を設定するには、新しい保留を作成します。

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Microsoft Teams とOffice 365 グループにホールドを配置する

Microsoft Teams は、Office 365 グループに基づいて構築されています。 そのため、電子情報開示 (Premium) で保留にするのも同様です。

- **追加のMicrosoft 365 グループまたは Microsoft Teams サイトをカストディアンにマップ操作方法?また、Microsoft 365 グループと Microsoft Teams に非カストディアル ホールドを配置する場合はどうでしょうか。** Microsoft Teams は、Microsoft 365 グループに基づいて構築されています。 そのため、電子情報開示ケースで保留にするのも同様です。 Microsoft 365 グループと Microsoft Teams を保留にする場合は、次の点に注意してください。

  - Microsoft 365 グループおよび Microsoft Teams にあるコンテンツを保留にするには、グループまたはチームに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。
  
  - Exchange Onlineで **Get-UnifiedGroup** コマンドレットを実行して、Microsoft 365 グループまたは Microsoft Team のプロパティを表示します。 これは、Microsoft 365 グループまたは Microsoft チームに関連付けられているサイトの URL を取得するのに適した方法です。 たとえば、次のコマンドは、上級管理職チームという名前の Microsoft 365 グループの選択されたプロパティを表示します。

    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Get-UnifiedGroup コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。

  - ユーザーのメールボックスが検索されると、ユーザーがメンバーである Microsoft 365 グループまたは Microsoft Team は検索されません。 同様に、Microsoft 365 グループまたは Microsoft Team ホールドを配置すると、グループ メールボックスとグループ サイトのみが保留になります。グループ メンバーのメールボックスとOneDrive for Business サイトは、明示的にカストディアンとして追加するか、データ ソースを保持しない限り、保留にされません。 そのため、特定のカストディアンに対して Microsoft 365 グループまたは Microsoft Team を保留にする必要がある場合は、グループ サイトとグループ メールボックスをカストディアンにマッピングすることを検討してください (電子情報開示でのカストディアンの管理 (Premium)を参照)。 Microsoft 365 グループまたは Microsoft チームが 1 人のカストディアンに帰属しない場合は、ソースを非保管ホールドに追加することを検討してください。
  - Microsoft 365 グループまたは Microsoft Team のメンバーの一覧を取得するには、Microsoft 365 管理センターの **[ホーム** > [**グループ]**](https://go.microsoft.com/fwlink/p/?linkid=2052855) ページでプロパティを表示できます。 または、Exchange Online PowerShell で次のコマンドを実行できます。

    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
    ```

    > [!NOTE]
    > **Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。

  - Microsoft Teams チャネルの一部であるチャネル会話は、チームに関連付けられているメールボックスに格納されます。 同様に、メンバーがチャネルで共有するファイルは、チームの SharePoint サイトに保存されます。 そのため、チャネル内の会話とファイルを保持するには、Microsoft Team メールボックスと SharePoint サイトを保留にする必要があります。
  
  - または、Microsoft Teams のチャット リストに含まれる会話は、チャットに参加するユーザーのメールボックスに格納されます。  チャット会話でユーザーが共有するファイルは、ファイルを共有するユーザーのOneDrive for Business サイトに格納されます。 そのため、チャットの一覧で会話やファイルを保持するには、個々のユーザー メールボックスとOneDrive for Business サイトを保留にする必要があります。
  
  - 各 Microsoft チームまたはチーム チャネルには、メモと共同作業用の Wiki が含まれています。Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。このファイルは、チームの SharePoint サイトの Teams Wiki データ ドキュメント ライブラリに保存されます。Wiki のコンテンツを保留にするには、チームの SharePoint サイトを保留にします。

    > [!NOTE]
    > (チームの SharePoint サイトを保留にするときに) Microsoft チームまたはチーム チャネルの Wiki コンテンツを保持する機能は、2017 年 6 月 22 日にリリースされました。チーム サイトが保留にされると、この日から Wiki コンテンツが保持されます。ただし、チーム サイトが保留にされ、Wiki コンテンツが 2017 年 6 月 22 日よりも前に削除された場合、その Wiki コンテンツは保持されていません。
