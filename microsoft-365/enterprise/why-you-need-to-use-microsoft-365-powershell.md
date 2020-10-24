---
title: Microsoft 365 で PowerShell を使用する理由
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: ''
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: '概要: PowerShell を使用して Microsoft 365 を管理する必要がある理由について説明します。場合によっては効率的で、その他の場合は必要になることがあります。'
ms.openlocfilehash: d56a2cc47a06be911f1fd38aea3a557c631d2db0
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754108"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Microsoft 365 で PowerShell を使用する理由

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 管理センターを使用すると、Microsoft 365 のユーザーアカウントとライセンスを管理できます。 また、Exchange Online、Teams、SharePoint Online などの Microsoft 365 サービスを管理することもできます。 PowerShell を使用してこれらのサービスを管理する場合は、速度、自動化、およびその他の機能を実現するために、コマンドラインおよびスクリプト言語環境を利用できます。
  
この記事では、PowerShell を使用して Microsoft 365 を管理する方法について説明します。
  
- Microsoft 365 管理センターでは表示できない追加情報を確認する
    
- PowerShell でのみ使用可能な機能と設定を構成する
    
- 一括操作を実行する
    
- データをフィルター処理する
    
- データを印刷または保存する
    
- サービス間で管理する
    
Microsoft 365 の PowerShell は、windows PowerShell 用のモジュールのセットであることに注意してください。これは、Windows ベースのサービスとプラットフォームのコマンドライン環境です。 この環境では、追加のモジュールで拡張できるコマンドシェル言語が作成されます。 これにより、単純なまたは複雑なコマンドまたはスクリプトを実行することができます。 たとえば、microsoft 365 モジュールの PowerShell をインストールし、Microsoft 365 サブスクリプションに接続した後、次のコマンドを実行して Microsoft Exchange Online のすべてのユーザーメールボックスを一覧表示できます。
  
```powershell
Get-Mailbox
```

また、Microsoft 365 管理センターを使用してメールボックスの一覧を取得することもできますが、すべての web アプリケーションのすべてのサイトについて、すべてのリストのアイテムをカウントするのは簡単ではありません。
  
Microsoft 365 用の PowerShell は、microsoft 365 を管理することを支援するように設計されています。 microsoft 365 管理センターを置き換えることはできません。 Microsoft 365 コマンドの PowerShell でしか実行できない構成手順があるため、管理者は Microsoft 365 の PowerShell を使用できる必要があります。 このような場合は、次の方法を知っておく必要があります。
  
- Microsoft 365 モジュールの PowerShell をインストールします (管理者のコンピューターごとに1回のみ行われます)。
    
- Microsoft 365 サブスクリプション (PowerShell セッションごとに1回) に接続します。
    
- Microsoft 365 コマンドに必要な PowerShell を実行するために必要な情報を収集します。
    
- Microsoft 365 コマンドの PowerShell を実行します。
    
これらの基本的なスキルを習得した後は、メールボックスユーザーを **取得** するために、メールボックスのコマンドを使用する必要はありません。 また、以前に説明したコマンドを使用して、すべての web アプリのすべてのサイトのすべてのリスト内のすべてのアイテムをカウントする方法について理解する必要はありません。 Microsoft と管理者コミュニティは、必要に応じてこれらのタスクを支援します。
  
## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>Microsoft 365 用の PowerShell は、Microsoft 365 管理センターでは表示できない情報を公開することができます

Microsoft 365 管理センターには、さまざまな役に立つ情報が表示されます。 しかし、Microsoft 365 でユーザー、ライセンス、メールボックス、サイトに関して保存される可能性のある情報がすべて表示されるわけではありません。 Microsoft 365 管理センターの *ユーザーとグループ* の例を次に示します。
  
![Microsoft 365 管理センターでのユーザーとグループの表示例。](../media/o365-powershell-users-and-groups.png)
  
このビューでは、多くの場合に必要な情報が提供されます。 しかし、もっと多くの情報が必要な場合もあります。 たとえば、Microsoft 365 ライセンス (およびユーザーが使用できる Microsoft 365 機能) は、ユーザーの地理的な場所によって異なります。 米国に住んでいるユーザーに拡張できるポリシーと機能は、インドまたはベルギーでユーザーに拡張できるものとは異なる場合があります。 Microsoft 365 管理センターで、次の手順を実行して、ユーザーの地理的な場所を決定します。
  
1. ユーザーの **表示名** をダブルクリックします。
    
2. ユーザープロパティの表示ウィンドウで、[ **詳細**] を選択します。
    
3. 詳細表示で、[ **追加の詳細**] を選択します。
    
4. 見出しの **国または地域**が見つかるまでスクロールします。
    
     ![Microsoft 365 管理センター内のユーザーの地域情報の例。](../media/o365-powershell-usage-location.png)
  
5. ユーザーの表示名と場所を紙に書き留めるか、コピーしてメモ帳に貼り付けます。
    
この手順をユーザーごとに繰り返す必要があります。 ユーザー数が多い場合、このプロセスは退屈になる可能性があります。 Microsoft 365 の PowerShell では、次のコマンドを使用して、すべてのユーザーについてこの情報を表示することができます。
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core は、Windows PowerShell モジュールの Microsoft Azure Active Directory モジュールと、名前に *Msol* が含まれるコマンドレットをサポートしていません。 これらのコマンドレットは、Windows PowerShell から実行する必要があります。
>

結果の例を次に示します。
  
```powershell
DisplayName                               UsageLocation
-----------                               -------------
Bonnie Kearney                            GB
Fabrice Canel                             BR
Brian Johnson (TAILSPIN)                  US
Anne Wallace                              US
Alex Darrow                               US
David Longmuir                            BR
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション (**set-azureaduser**) 内のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示します (**DisplayName、使用場所の選択**)。
  
Microsoft 365 用の PowerShell はコマンドシェル言語をサポートしているため、 **set-azureaduser** コマンドで取得した情報をさらに操作することができます。 たとえば、これらのユーザーを場所によって並べ替えたり、すべてのブラジルユーザーを一緒にグループ化したり、すべての米国ユーザーを一緒にグループ化したりしたい場合があります。 コマンドは次のとおりです。
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation | Sort UsageLocation, DisplayName
```

結果の例を次に示します。
  
```powershell
DisplayName                                 UsageLocation
-----------                                 -------------
David Longmuir                              BR
Fabrice Canel                               BR
Bonnie Kearney                              GB
Alex Darrow                                 US
Anne Wallace                                US
Brian Johnson (TAILSPIN)                    US
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション内のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示し、それらの場所とその名前 (**並べ替えでは、DisplayName**) を並べ替えます。
  
追加のフィルター処理を使用することもできます。 たとえば、ブラジル在住のユーザーに関する情報のみを表示する場合には、次のコマンドを使用します。
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq "BR"} | Select DisplayName, UsageLocation 
```

結果の例を次に示します。
  
```powershell
DisplayName                                           UsageLocation
-----------                                           -------------
David Longmuir                                        BR
Fabrice Canel                                         BR
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションで、場所がブラジルであるすべてのユーザーを取得します (**Where {$ \_ .使用場所-eq "BR"}**) を選択して、各ユーザーの名前と場所を表示します。
  
 **大規模なドメインに関する注意事項**
  
多数のユーザーが含まれる大きなドメインがある場合、この記事に示されている例のいくつかを試してみると調整につながる可能性があります。 コンピューティングパワーや使用可能なネットワーク帯域幅などの要因に基づいて、一度に多くの操作を実行しようとしている可能性があります。 大規模な組織では、これらの PowerShell 操作の一部を2つのコマンドに分割する必要がある場合があります。

たとえば、次のコマンドを実行すると、すべてのユーザーアカウントが返され、それぞれの名前と場所が表示されます。
  
```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

このコマンドは、規模が小さいドメインには最適に機能します。 しかし、大規模な組織では、この操作を2つのコマンドに分割する必要があります。1つは、ユーザーアカウント情報を変数に格納し、もう1つのコマンドを使用して必要な情報を表示することです。 次に例を示します:
  
```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

この PowerShell コマンドのセットは次のように解釈されます。
1. 現在の Microsoft 365 サブスクリプション内のすべてのユーザーを取得し、その情報を $x (**$x = set-azureaduser**) という名前の変数に格納します。
1.  変数 *$x*の内容を表示します。ただし、各ユーザーの名前と場所のみが含まれます (**$x |DisplayName、[その他] の場所) を選択**します。
  
## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365 には、Microsoft 365 の PowerShell でのみ構成できる機能があります。

Microsoft 365 管理センターは、ほとんどの環境に適用される一般的で便利な管理タスクへのアクセスを提供することを目的としています。 つまり、Microsoft 365 管理センターは、一般的な管理者が最も一般的な管理タスクを実行できるように設計されています。 ただし、管理センターでは実行できないタスクがいくつかあります。
  
たとえば、Skype for Business Online 管理センターには、カスタムの会議出席依頼を作成するためのオプションがいくつか用意されています。
  
![Skype for Business Online 管理センターでカスタムの会議出席依頼を表示する例です。](../media/o365-powershell-meeting-invitation.png)
  
これらの設定を使用すると、会議出席依頼にパーソナルでプロフェッショナルな風合いを加えることができます。 ただし、会議構成設定には、カスタムの会議出席依頼を作成するだけでなく、さらに多くのことがあります。 たとえば、既定では会議に関して以下の事柄が許可されています。
  
- 匿名ユーザーが、各会議に自動的に参加すること。
    
- 参加者が、会議を記録すること。
    
- 組織のすべてのユーザーが、会議に参加するときに発表者として指定されること。
    
これらの設定は、Skype for Business Online 管理センターからは使用できません。 Microsoft 365 の PowerShell を使用して制御できます。 次の3つの設定を無効にするコマンドを次に示します。
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> このコマンドを実行するには、 [Skype For Business Online PowerShell モジュール ](https://www.microsoft.com/download/details.aspx?id=39366)をインストールする必要があります。
  
この PowerShell コマンドの解釈は次のとおりです。
 
1. [新しい Skype for Business Online 会議の設定 (AdmitAnonymousUsersByDefault **)]** で、匿名ユーザーが会議への自動入り口を取得することを許可しないようにします (**-$False**)。
2.  参加者が会議を記録する機能を無効にします (**-AllowConferenceRecording $False**)。
3. 組織内のすべてのユーザーを発表者として指定しないでください (**-designateaspresenter "None"**)。
  
これらの既定の設定 (オプションを有効にする) を復元するには、次のコマンドを実行します。
  
```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

他にも同様のシナリオがあります。これは、管理者が Microsoft 365 コマンドで PowerShell を実行する方法について理解しておく必要があるためです。
  
## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>Microsoft 365 の PowerShell は一括操作に適しています。

Microsoft 365 管理センターのようなビジュアルインターフェイスは、単一の操作を行う場合に最も役立ちます。 たとえば、1つのユーザーアカウントを無効にする必要がある場合は、管理センターを使用してチェックボックスをすばやく見つけてクリアすることができます。 これは、PowerShell で同様の操作を実行するよりも簡単になります。
  
しかし、その他の多くの場合に、多数の項目や一部の選択項目を変更する必要がある場合は、Microsoft 365 管理センターが最適なツールではない可能性があります。 たとえば、数千人の電話番号のプレフィックスを変更したり、すべての SharePoint Online サイトから特定のユーザー *Ken Myer* を削除したりする必要があるとします。 Microsoft 365 管理センターでは、どのような方法を実行しますか?
  
最後の例では、数百の SharePoint Online サイトがあり、Ken Meyer がメンバーであるかどうかがわからないとします。 Microsoft 365 管理センターから開始して、各サイトでこの手順を実行する必要があります。
  
1. サイトの **URL** を選択します。
    
2. [ **サイトコレクションのプロパティ** ] ボックスで、[ **Web サイトのアドレス** ] リンクを選択してサイトを開きます。
    
3. サイトで、[ **共有**] を選択します。
    
4. [ **共有** ] ダイアログボックスで、サイトへのアクセス許可を持つすべてのユーザーを表示するリンクを選択します。
    
     ![SharePoint Online 管理センターの SharePoint Online サイトのメンバーを表示する例です。](../media/o365-powershell-view-permissions.png)
  
5. [ **共有相手** ] ダイアログボックスで、[ **詳細設定**] を選択します。
    
6. ユーザーのリストを下にスクロールし、Ken Myer (サイトへのアクセス許可があることを前提としています) を見つけて選択し、[ **ユーザー権限の削除**] を選択します。
    
これには、数百のサイトでは *長い* 時間がかかります。
  
別の方法として、Microsoft 365 の PowerShell で次のコマンドを実行して、すべてのサイトから Ken Myer を削除することができます。
  
```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> このコマンドを実行するには、 [SharePoint Online PowerShell モジュール](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)をインストールする必要があります。 
  
この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション (**get-sposite**) 内のすべての SharePoint サイトを取得し、各サイトについてアクセスできるユーザーのリストから Ken Meyer を削除し**ます (ForEach {Remove-Spouser-site $ \_ 。Url-ログイン "kenmyer \@ litwareinc.com"}**)。
  
Microsoft 365 に、ユーザーがアクセス権を持っていないものも含めて、すべてのサイトから Ken Meyer を削除するよう伝えています。 そのため、ユーザーがアクセス権を持っていないサイトに関するエラーが表示されます。 このコマンドで追加の条件を使用して、彼がログインリストにあるサイトから Ken Meyer のみを削除することができます。 ただし、返されるエラーは、サイト自体に害を与えることはありません。 このコマンドは、Microsoft 365 管理センターで作業する時間ではなく、数百のサイトに対して実行されるまでに数分かかる場合があります。
  
もう1つの一括操作の例を次に示します。 次のコマンドを使用して、組織内のすべてのサイトに *Bonnie Kearney*(新しい SharePoint 管理者) を追加します。
  
```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプション内のすべての SharePoint サイトを取得します。また、サイトのメンバーグループにログイン名を追加して Bonnie Kearney access を許可することもできます (**ForEach {Add-SPOUser-site $ \_ 。Url-"bkearney \@ litwareinc.com"-グループ "Members"}**)。
  
## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>Microsoft 365 の PowerShell は、データのフィルター処理に適しています。

Microsoft 365 管理センターでは、データをフィルター処理して、対象となる情報のサブセットを簡単に見つけられるようにする方法がいくつか用意されています。 たとえば、Exchange では、ユーザー メールボックスのほとんどすべてのプロパティに対するフィルターを簡単に適用できます。 たとえば、ブルーミントン市に居住しているすべてのユーザーのメールボックスの一覧を次に示します。
  
![ブルーミントンの市区町村に居住しているすべてのユーザーのメールボックスの一覧については、Microsoft 365 管理センターで高度な検索を実行する例を示します。](../media/o365-powershell-advanced-search.png)
  
Exchange 管理センターでは、フィルター条件を組み合わせることもできます。 たとえば、ブルーミントンに居住していて、財務部門で勤務しているすべてのユーザーのメールボックスを見つけることができます。
  
ただし、Exchange 管理センターでできることには制限があります。 たとえば、ブルーミントン *または* サンディエゴに居住しているユーザーのメールボックスや、ブルーミントンに居住していないすべてのユーザーのメールボックスを簡単に見つけることができませんでした。
  
次の Microsoft 365 コマンドの PowerShell を使用して、ブルーミントンまたはサンディディエゴに居住しているすべてのユーザーのメールボックスの一覧を取得できます。
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and ($_.City -eq "San Diego" -or $_.City -eq "Bloomington")} | Select DisplayName, City
```

結果の例を次に示します。
  
```powershell
DisplayName                              City
-----------                              ----
Alex Darrow                              San Diego
Bonnie Kearney                           San Diego
Julian Isla                              Bloomington
Rob Young                                Bloomington
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションで、メールボックスが San ディエゴまたはブルーミントン (Where {$) の市区町村にあるすべてのユーザーを取得し** \_ ます。[受信者] Typetypedetails-eq "UserMailbox"-and ($ \_ .City-eq "サンディエゴ"-または $ \_ 。City-eq "ブルーミントン")}**) をクリックし、それぞれの名前と市区町村を表示します (**DisplayName、City を選択**)。
  
ブルーミントン以外の場所にいるユーザーのすべてのメールボックスを一覧表示するコマンドは次のとおりです。
  
```powershell
Get-User | Where {$_.RecipientTypeDetails -eq "UserMailbox" -and $_.City -ne "Bloomington"} | Select DisplayName, City
```

結果の例を次に示します。
  
```powershell
DisplayName                               City
-----------                               ----
MOD Administrator                         Redmond
Alex Darrow                               San Diego
Allie Bellew                              Bellevue
Anne Wallace                              Louisville
Aziz Hassouneh                            Cairo
Belinda Newman                            Charlotte
Bonnie Kearney                            San Diego
David Longmuir                            Waukesha
Denis Dehenne                             Birmingham
Garret Vargas                             Seattle
Garth Fort                                Tulsa
Janet Schorr                              Bellevue
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションで、メールボックスがブルーミントンの city (Where {$) にないすべてのユーザーを取得し** \_ ます。[受信者] Typetypedetails-eq "UserMailbox"-and $ \_ 。City-ne "ブルーミントン"}**) を選択し、それぞれの名前と市区町村を表示します。
  
### <a name="use-wildcards"></a>ワイルドカードを使用する

また、PowerShell フィルターでワイルドカード文字を使用して、名前の一部と一致させることもできます。 たとえば、ユーザーアカウントを探しているとします。 ユーザーの姓が *Anderson* か、 *Henderson* または *Jorgenson*であることを覚えておくことができます。
  
検索ツールを使用して、次の3つの異なる検索を実行することによって、Microsoft 365 管理センターでそのユーザーを追跡することができます。
  
- *Anderson*  用のもの 
    
- *Henderson*  用のもの 
    
- *Jorgenson*  用のもの 
    
これらの3つの名前はすべて "son" で終わるので、名前が "son" で終わるすべてのユーザーを表示するように PowerShell に指示できます。 コマンドは次のとおりです。
  
```powershell
Get-User -Filter '{LastName -like "*son"}'
```

この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションのすべてのユーザーを取得しますが、姓が "son" で終わるユーザーの一覧のみを含むフィルターを使用します (**-filter ' {LastName-like " \* son"} '**)。 は、 \* ユーザーの姓の文字である任意の文字セットを表します。
  
## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>Microsoft 365 の PowerShell を使用すると、データの印刷や保存が容易になります。

Microsoft 365 管理センターでは、データの一覧を表示できます。 Skype for business Online 管理センターの例では、Skype for business Online が有効になっているユーザーの一覧が表示されています。
  
![Skype for Business Online 管理センターで、Skype for Business Online に対して有効になっているユーザーの一覧を表示する例です。](../media/o365-powershell-lync-users.png)
  
その情報をファイルに保存するには、その情報を文書または Microsoft Excel ワークシートに貼り付ける必要があります。 どちらの場合も、追加の書式設定が必要になることがあります。 また、Microsoft 365 管理センターでは、表示されている一覧を直接印刷する方法は使用できません。
  
さいわい、PowerShell を使用してリストを表示するだけでなく、Excel に簡単にインポートできるファイルに保存することもできます。 次に、Skype for Business Online ユーザーデータをコンマ区切り値 (CSV) ファイルに保存するコマンドの例を示します。これは、Excel ワークシートのテーブルとして簡単にインポートできます。
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

結果の例を次に示します。
  
![コンマ区切り値ファイルに保存された Skype for Business Online ユーザーデータの Excel ワークシートにインポートされるテーブルの例です。](../media/o365-powershell-data-in-excel.png)
  
この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションのすべての Skype for Business Online ユーザーを取得します (**-Csonline ユーザー**)。ユーザー名、UPN、および場所のみを取得します (**DisplayName、UserPrincipalName、および利用場所を選択し**ます)。その情報を C: \\ logs \\SfBUsers.csv (**Export-csv-Path "c: \\ Logs \\SfBUsers.csv"-notypeinformation**) という名前の CSV ファイルに保存します。
  
オプションを使用して、このリストを XML ファイルまたは HTML ページとして保存することもできます。 実際には、追加の PowerShell コマンドを使用して、必要なカスタム書式設定を使用して Excel ファイルとして直接保存することができます。
  
また、Windows の既定のプリンターにリストを直接表示する PowerShell コマンドの出力を送信することもできます。 コマンドの例を次に示します。
  
```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

印刷されたドキュメントは次のようになります。
  
![Windows の既定のプリンターに直接送信された PowerShell コマンドの出力であった印刷ドキュメントの例。](../media/o365-powershell-printed-data.png)
  
この PowerShell コマンドの解釈は次のとおりです。現在の Microsoft 365 サブスクリプションのすべての Skype for Business Online ユーザーを取得します。ユーザー名、UPN、および場所のみを取得します。その情報を既定の Windows プリンター (**出力プリンター**) に送信します。
  
印刷された文書の簡単な書式設定は、PowerShell コマンドウィンドウの表示と同じです。 ハードコピーを取得するには、| を追加するだけです。 **| Out-Printer**コマンドの最後に印刷します。
  
## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>Microsoft 365 の PowerShell を使用すると、複数のサーバー製品を管理できます。

Microsoft 365 を構成するコンポーネントは、共同作業を行うように設計されています。 たとえば、Microsoft 365 に新しいユーザーを追加し、ユーザーの部署や電話番号などの情報を指定するとします。 この情報は、Microsoft 365 サービスのいずれか (Skype for Business Online、Exchange、または SharePoint) でユーザーの情報にアクセスすると利用できるようになります。
  
ただし、これは製品のスイートに共通する一般情報の場合です。 製品固有の情報 (ユーザーの Exchange メールボックスに関する情報など) は、通常、このスイートでは利用できません。 たとえば、ユーザーのメールボックスが有効になっているかどうかに関する情報は、Exchange 管理センターでのみ使用できます。
  
すべてのユーザーに関する次のような情報を示すレポートを作成するとします。
  
- ユーザーの表示名
    
- ユーザーが Microsoft 365 用にライセンスされているかどうか
    
- ユーザーの Exchange メールボックスが有効になっているかどうか
    
- ユーザーが Skype for Business Online に対して有効になっているかどうか
    
Microsoft 365 管理センターでは、このようなレポートを簡単に作成することはできません。 代わりに、Excel ワークシートなどの情報を格納するために別のドキュメントを作成する必要があります。 次に、Microsoft 365 管理センターからすべてのユーザー名とライセンス情報を取得し、Exchange 管理センターからメールボックス情報を取得して、skype for business Online 管理センターから Skype for Business Online 情報を取得し、その情報を結合します。
  
別の方法として、PowerShell スクリプトを使用してレポートをコンパイルできます。
  
次のスクリプト例は、この記事で説明したコマンドよりも複雑です。 しかし、これは、PowerShell を使用して、それ以外の方法で情報ビューを作成する可能性があることを示しています。 必要なリストをコンパイルして表示するためのスクリプトを次に示します。
  
```powershell
$x = Get-AzureADUser

foreach ($i in $x)
    {
      $y = Get-Mailbox -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled

      $y = Get-CsOnlineUser -Identity $i.UserPrincipalName
      $i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled
    }

$x | Select DisplayName, IsLicensed, IsMailboxEnabled, EnabledforSfB
```

結果の例を次に示します。
  
```powershell
DisplayName             IsLicensed   IsMailboxEnabled   EnabledForSfB
-----------             ----------   ----------------   --------------
Bonnie Kearney          True         True               True
Fabrice Canel           True         True               True
Brian Johnson           False        True               False
Anne Wallace            True         True               True
Alex Darrow             True         True               True
David Longmuir          True         True               True
Katy Jordan             False        True               False
Molly Dempsey           False        True               False
```

この PowerShell スクリプトの解釈は次のとおりです。  

1. 現在の Microsoft 365 サブスクリプション内のすべてのユーザーを取得し、その情報を *$x* (**$x = set-azureaduser**) という名前の変数に格納します。
1. 変数 $x 内のすべてのユーザーに対して実行されるループを開始します (**foreach ($x では $i)**)。  
1. *$Y*という名前の変数を定義し、ユーザーのメールボックス情報をそこに格納します (**$y = Get-Mailbox-Identity $i UserPrincipalName**)。
1. *IsMailBoxEnabled*という名前のユーザー情報に新しいプロパティを追加します。 ユーザーのメールボックスの IsMailBoxEnabled プロパティの値に設定します (**$i | Add-Member-MemberType 注プロパティ-Name IsMailBoxEnabled-value $Y IsMailBoxEnabled**)。
1. *$Y*という名前の変数を定義し、ユーザーの Skype For business Online 情報をその変数に格納します (**$y = Get-CsOnlineUser-Identity $i UserPrincipalName**)。
1. *Enabledforsfb*という名前のユーザー情報に新しいプロパティを追加します。 これを、ユーザーの Skype for Business Online 情報の Enabled プロパティの値 (**$i | Add-Member-MemberType 注プロパティ-Name EnabledForSfB-value $Y enabled**) の値に設定します。
1. ユーザーの一覧を表示しますが、ユーザー名、ライセンスがあるかどうか、メールボックスが有効になっているかどうか、およびそれらのプロパティが Skype for Business Online に対して有効になっているかどうかを示す2つの新しいプロパティを含めます (**$x |DisplayName、IsLicensed、IsMailboxEnabled、EnabledforSfB) を選択**します。
  
## <a name="see-also"></a>関連項目

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)
  
[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Windows PowerShell を使用して Microsoft 365 でレポートを作成する](use-windows-powershell-to-create-reports-in-microsoft-365.md)
