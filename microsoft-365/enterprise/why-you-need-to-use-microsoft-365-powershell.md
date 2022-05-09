---
title: Microsoft 365 で PowerShell を使用する理由
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/17/2020
audience: ITPro
ms.topic: overview
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: admindeeplinkEXCHANGE
ms.assetid: b3209b1a-40c7-4ede-8e78-8a88bb2adc8a
description: '概要: PowerShell を使用してMicrosoft 365を管理する必要がある理由を理解します。場合によっては、必要に応じて効率的に管理する必要があります。'
ms.openlocfilehash: 114b97ff27ae1b79e58589eb746a261f83dc422f
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097934"
---
# <a name="why-you-need-to-use-powershell-for-microsoft-365"></a>Microsoft 365 で PowerShell を使用する理由

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Microsoft 365 管理センターを使用すると、Microsoft 365ユーザー アカウントとライセンスを管理できます。 Exchange Online、Teams、SharePoint Online など、Microsoft 365 サービスを管理することもできます。 代わりに PowerShell を使用してこれらのサービスを管理する場合は、コマンド ラインとスクリプト言語環境を利用して、速度、自動化、その他の機能を利用できます。

この記事では、PowerShell を使用して次のMicrosoft 365を管理する方法について説明します。

- Microsoft 365 管理センターに表示できない追加情報を表示する

- PowerShell でのみ可能な機能と設定を構成する

- 一括操作を実行する

- データをフィルター処理する

- データを印刷または保存する

- サービス間で管理する

PowerShell for Microsoft 365は、Windows ベースのサービスとプラットフォームのコマンド ライン環境であるWindows PowerShell用のモジュールのセットであることに注意してください。 この環境では、追加のモジュールで拡張できるコマンド シェル言語を作成します。 これは、単純なコマンドまたは複雑なコマンドまたはスクリプトを実行する方法を提供します。 たとえば、powerShell for Microsoft 365 モジュールをインストールし、Microsoft 365 サブスクリプションに接続した後、次のコマンドを実行して、Microsoft Exchange Onlineのすべてのユーザー メールボックスを一覧表示できます。

```powershell
Get-Mailbox
```

Microsoft 365 管理センターを使用してメールボックスの一覧を取得することもできますが、すべての Web アプリのすべてのサイトのすべてのリストのアイテムをカウントするのは簡単ではありません。

PowerShell for Microsoft 365は、Microsoft 365 管理センターを置き換えるのではなく、Microsoft 365を管理するのに役立ちます。 管理者は PowerShell を使用してMicrosoft 365できる必要があります。これは、powerShell を使用してMicrosoft 365コマンドを使用する場合にのみ実行できる構成手順があるためです。 このような場合は、次の方法を知る必要があります。

- Microsoft 365 モジュール用の PowerShell をインストールします (管理者コンピューターごとに 1 回だけ実行)。

- Microsoft 365 サブスクリプションにConnectします (PowerShell セッションごとに 1 回)。

- Microsoft 365 コマンドに必要な PowerShell を実行するために必要な情報を収集します。

- powerShell を実行してMicrosoft 365コマンドを実行します。

これらの基本的なスキルを学習した後、 **Get-Mailbox** コマンドを使用してメールボックス ユーザーを一覧表示する必要はありません。 また、すべての Web アプリのすべてのサイトのすべてのリストのすべての項目をカウントするために、前に引用したコマンドのような新しいコマンドを作成する方法を理解する必要はありません。 Microsoft と管理者コミュニティは、必要に応じてこのようなタスクを支援できます。

## <a name="powershell-for-microsoft-365-can-reveal-information-that-you-cant-see-with-the-microsoft-365-admin-center"></a>PowerShell for Microsoft 365では、Microsoft 365 管理センターでは表示できない情報を表示できます。

Microsoft 365 管理センターには、多くの有用な情報が表示されます。 ただし、ユーザー、ライセンス、メールボックス、およびサイトに関するMicrosoft 365格納できるすべての情報は表示されません。 Microsoft 365 管理センターの *ユーザーとグループ* の例を次に示します。

![Microsoft 365 管理センター内のユーザーとグループの表示の例。](../media/o365-powershell-users-and-groups.png)

このビューには、多くの場合に必要な情報が表示されます。 しかし、もっと多くの情報が必要な場合もあります。 たとえば、Microsoft 365ライセンス (およびユーザーが使用できるMicrosoft 365機能) は、ユーザーの地理的な場所によって異なります。 米国に住むユーザーに拡張できるポリシーと機能は、インドまたはベルギーのユーザーに拡張できるポリシーと同じでない場合があります。 Microsoft 365 管理センターの次の手順に従って、ユーザーの地理的な場所を決定します。

1. ユーザーの **表示名** をダブルクリックします。

2. ユーザー プロパティの表示ウィンドウで、 **詳細** を選択します。

3. 詳細表示で、追加の **詳細** を選択します。

4. **[国または地域]** という見出しが見つかるまでスクロールします。

     ![Microsoft 365 管理センター内のユーザーのリージョン情報の例。](../media/o365-powershell-usage-location.png)

5. ユーザーの表示名と場所を紙に書き留めるか、コピーしてメモ帳に貼り付けます。

この手順をユーザーごとに繰り返す必要があります。 ユーザーが多い場合、このプロセスは面倒な場合があります。 PowerShell for Microsoft 365では、次のコマンドを使用して、すべてのユーザーに対してこの情報を表示できます。

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```


>[!Note]
>PowerShell Core では、名前に *Msol* が含まれるWindows PowerShell モジュールとコマンドレットのMicrosoft Azure Active Directory モジュールはサポートされていません。 これらのコマンドレットは、Windows PowerShellから実行する必要があります。
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

この PowerShell コマンドの解釈は、現在のMicrosoft 365 サブスクリプション (**Get-AzureADUser**) 内のすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示します (**DisplayName、UsageLocation の選択**)。

PowerShell for Microsoft 365ではコマンド シェル言語がサポートされているため、**Get-AzureADUser** コマンドで取得した情報をさらに操作できます。 たとえば、これらのユーザーを場所別に並べ替え、すべてのブラジルユーザーをグループ化し、すべての米国ユーザーをまとめて並べ替える場合などです。 コマンドを次に示します。

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

この PowerShell コマンドの解釈は、現在のMicrosoft 365 サブスクリプションのすべてのユーザーを取得しますが、各ユーザーの名前と場所のみを表示し、最初に場所と名前 (**Sort UsageLocation、DisplayName**) で並べ替えます。

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

この PowerShell コマンドの解釈は、現在のMicrosoft 365サブスクリプション内のすべてのユーザーを取得し、その場所がブラジル (**Where {$\_.UsageLocation -eq "BR"}**) をクリックし、各ユーザーの名前と場所を表示します。

 **大きなドメインに関するメモ**

数万人のユーザーを持つ大規模なドメインがある場合は、この記事で示す例の一部を試すと、調整が発生する可能性があります。 コンピューティング能力や使用可能なネットワーク帯域幅などの要因に基づいて、一度に多くのことを試みる可能性があります。 大規模な組織では、これらの PowerShell 操作の一部を 2 つのコマンドに分割したい場合があります。

たとえば、次のコマンドはすべてのユーザー アカウントを返し、それぞれの名前と場所を示します。

```powershell
Get-AzureADUser | Select DisplayName, UsageLocation
```

このコマンドは、規模が小さいドメインには最適に機能します。 ただし、大規模な組織では、その操作を 2 つのコマンドに分割することができます。1 つのコマンドでユーザー アカウント情報を変数に格納し、もう 1 つは必要な情報を表示します。 次に例を示します。

```powershell
$x = Get-AzureADUser
$x | Select DisplayName, UsageLocation
```

この PowerShell コマンドのセットの解釈は次のとおりです。
1. 現在のMicrosoft 365 サブスクリプションのすべてのユーザーを取得し、$x (**$x = Get-AzureADUser**) という名前の変数に情報を格納します。
1.  変数 *$x* の内容を表示しますが、各ユーザーの名前と場所のみを含めます (**$x |DisplayName、UsageLocation) を選択** します。

## <a name="microsoft-365-has-features-that-you-can-only-configure-with-powershell-for-microsoft-365"></a>Microsoft 365には、PowerShell for Microsoft 365でのみ構成できる機能があります

Microsoft 365 管理センターは、ほとんどの環境に適用される一般的で有用な管理タスクへのアクセスを提供することを目的としています。 つまり、Microsoft 365 管理センターは、一般的な管理者が最も一般的な管理タスクを実行できるように設計されています。 ただし、管理センターでは実行できないタスクがいくつかあります。

たとえば、Skype for Business Online 管理センターには、カスタム会議出席依頼を作成するためのいくつかのオプションがあります。

![Skype for Business Online 管理センターでカスタムの会議出席依頼を表示する例です。](../media/o365-powershell-meeting-invitation.png)

これらの設定を使用すると、会議出席依頼にパーソナルでプロフェッショナルな風合いを加えることができます。 ただし、会議の構成設定には、単にカスタム会議出席依頼を作成するよりも多くの機能があります。 たとえば、既定では会議に関して以下の事柄が許可されています。

- 匿名ユーザーが、各会議に自動的に参加すること。

- 参加者が、会議を記録すること。

- 組織のすべてのユーザーが、会議に参加するときに発表者として指定されること。

これらの設定は、Skype for Business Online 管理センターでは使用できません。 PowerShell から制御してMicrosoft 365できます。 次の 3 つの設定を無効にするコマンドを示します。

```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $False -AllowConferenceRecording $False -DesignateAsPresenter "None"
```

> [!NOTE]
> このコマンドを実行するには、[Skype for Business Online PowerShell モジュール](https://www.microsoft.com/download/details.aspx?id=39366)をインストールする必要があります。

この PowerShell コマンドの解釈は次のとおりです。

1. 新しい Skype for Business Online 会議 (**Set-CsMeetingConfiguration**) の設定で、匿名ユーザーが会議に自動的に参加できるようにする (**-AdmitAnonymousUsersByDefault $False**) を無効にします。
2.  出席者が会議を記録する機能を無効にします (**-AllowConferenceRecording $False**)。
3. 組織のすべてのユーザーを発表者として指定しないでください (**-DesignateAsPresenter "None"**)。

これらの既定の設定を復元する (オプションを有効にする) には、次のコマンドを実行します。

```powershell
Set-CsMeetingConfiguration -AdmitAnonymousUsersByDefault $True -AllowConferenceRecording $True -DesignateAsPresenter "Company"
```

同様のシナリオも他にもあります。そのため、管理者は powerShell を実行してMicrosoft 365コマンドを実行する方法を理解する必要があります。

## <a name="powershell-for-microsoft-365-is-great-for-bulk-operations"></a>powerShell for Microsoft 365 は、一括操作に最適です

Microsoft 365 管理センターなどのビジュアル インターフェイスは、1 回の操作を実行する場合に最も役立ちます。 たとえば、1 つのユーザー アカウントを無効にする必要がある場合は、管理センターを使用して、チェック ボックスをすばやく見つけてクリアすることができます。 これは、PowerShell で同様の操作を実行するよりも簡単な場合があります。

ただし、他の大規模なセット内で多くの変更や選択した内容を変更する必要がある場合は、Microsoft 365 管理センターが最適なツールではない可能性があります。 たとえば、数千の電話番号のプレフィックスを変更するか、特定のユーザー *Ken Myer* をすべてのSharePoint Online サイトから削除する必要があるとします。 Microsoft 365 管理センターではどのように行いますか?

最後の例では、数百の SharePoint Online サイトがあり、Ken Meyer がどのサイトのメンバーであるかがわからないとします。 Microsoft 365 管理センターから開始し、サイトごとに次の手順を実行する必要があります。

1. サイトの **URL を** 選択します。

2. **サイト コレクションのプロパティ** ボックスで、[**Web サイト アドレス**] リンクを選択してサイトを開きます。

3. サイトで、[ **共有**] を選択します。

4. [ **共有** ] ダイアログ ボックスで、サイトに対するアクセス許可を持つすべてのユーザーを示すリンクを選択します。

     ![SharePoint Online 管理センターの SharePoint Online サイトのメンバーを表示する例です。](../media/o365-powershell-view-permissions.png)

5. [共有ユーザー] ダイアログ ボックス **で** 、[ **詳細設定**] を選択します。

6. ユーザーの一覧を下にスクロールし、Ken Myer を見つけて選択し (サイトに対するアクセス許可がある場合) 、[ **ユーザーのアクセス許可の削除**] を選択します。

これは、数百のサイトに *長い* 時間がかかります。

代わりに、PowerShell for Microsoft 365で次のコマンドを実行して、すべてのサイトから Ken Myer を削除します。

```powershell
Get-SPOSite | ForEach {Remove-SPOUser -Site $_.Url -LoginName "kenmyer@litwareinc.com"}
```

> [!NOTE]
> このコマンドでは、[SharePoint Online PowerShell モジュール](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)をインストールする必要があります。

この PowerShell コマンドの解釈は、現在のMicrosoft 365 サブスクリプション (**Get-SPOSite**) 内のすべてのSharePoint サイトを取得し、サイトごとにアクセスできるユーザーの一覧から Ken Meyer を削除します (**ForEach {Remove-SPOUser -Site $\_)。URL -LoginName "kenmyer\@ litwareinc.com"}**)。

Ken Meyer にアクセスできないサイトも含め、すべてのサイトから Ken Meyer を削除するようにMicrosoft 365に指示します。 そのため、アクセス権を持たないサイトのエラーが結果に表示されます。 このコマンドで追加の条件を使用して、Ken Meyer を自分のログイン リストに含まれているサイトからのみ削除できます。 ただし、返されるエラーは、サイト自体に害を及ぼしません。 このコマンドは、Microsoft 365 管理センターを処理する時間ではなく、数百のサイトに対して実行するのに数分かかる場合があります。

別の一括操作の例を次に示します。 次のコマンドを使用して、新しいSharePoint管理者である *ボニー キーニー* を組織内のすべてのサイトに追加します。

```powershell
Get-SPOSite | ForEach {Add-SPOUser -Site $_.Url -LoginName "bkearney@litwareinc.com" -Group "Members"}
```

この PowerShell コマンドの解釈は次のとおりです。現在のMicrosoft 365 サブスクリプション内のすべてのSharePoint サイトを取得し、サイトごとに、サイトのメンバー グループ (**ForEach {Add-SPOUser -Site $\_.URL -LoginName "bke litwareinc.com\@" -group "Members"}**)。

## <a name="powershell-for-microsoft-365-is-great-at-filtering-data"></a>Microsoft 365用 PowerShell は、データのフィルター処理に優れています

Microsoft 365 管理センターには、データをフィルター処理して、対象となる情報のサブセットを簡単に特定するためのいくつかの方法が用意されています。 たとえば、Exchange では、ユーザー メールボックスのほとんどすべてのプロパティに対するフィルターを簡単に適用できます。 たとえば、ブルーミングトン市に住むすべてのユーザーのメールボックスの一覧を次に示します。

![ブルーミングトン市に住むすべてのユーザーのメールボックスの一覧のMicrosoft 365 管理センターで高度な検索を実行する例。](../media/o365-powershell-advanced-search.png)

<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>では、フィルター条件を組み合わせることもできます。 たとえば、ブルーミングトンに住み、財務部門で働くすべてのユーザーのメールボックスを見つけることができます。

ただし、Exchange管理センターでできることには制限があります。 たとえば、ブルーミングトンやサン ディエゴに住んでいるユーザーのメールボックス *や* 、ブルーミングトンに住まないすべてのユーザーのメールボックスを簡単に見つけることができませんでした。

次の PowerShell for Microsoft 365 コマンドを使用して、ブルーミングトンまたはサン ディエゴに住むすべてのユーザーのメールボックスの一覧を取得できます。

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

この PowerShell コマンドの解釈は、現在のMicrosoft 365 サブスクリプションに含まれるすべてのユーザーを取得し、San Diego または Bloomington (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and ($\_.City -eq "San Diego" -or $\_.City -eq "Bloomington")}**)、それぞれの名前と都市を表示します (**DisplayName、City の選択**)。

また、Bloomington を除く任意の場所に住んでいるユーザーのすべてのメールボックスを一覧表示するコマンドを次に示します。

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

この PowerShell コマンドの解釈は次のとおりです。現在のMicrosoft 365 サブスクリプションに含まれるすべてのユーザーを取得します。メールボックスを持つユーザーは、ブルーミングトン市にありません (**Where {$\_.RecipientTypeDetails -eq "UserMailbox" -and $\_。City -ne "Bloomington"}**)、それぞれの名前と都市を表示します。

### <a name="use-wildcards"></a>ワイルドカードを使用する

PowerShell フィルターでワイルドカード文字を使用して、名前の一部と一致することもできます。 たとえば、ユーザー アカウントを探しているとします。 覚えておくことができるのは、ユーザーの姓が *Anderson* か *、Henderson* または *Arnoldnson* であった可能性があるということです。

検索ツールを使用し、次の 3 つの異なる検索を実行することで、Microsoft 365 管理センターでそのユーザーを追跡できます。

- *Anderson*  用のもの

- *Henderson*  用のもの

- *Jorgenson*  用のもの

これらの 3 つの名前はすべて "son" で終わるので、名前が "son" で終わるすべてのユーザーを表示するように PowerShell に指示できます。 コマンドを次に示します。

```powershell
Get-User -Filter '{LastName -like "*son"}'
```

この PowerShell コマンドの解釈は、現在のMicrosoft 365 サブスクリプションのすべてのユーザーを取得しますが、姓が "son" で終わるユーザーのみを一覧表示するフィルターを使用します (**-Filter '{LastName -like "\*son"}**)。 任意 \* の文字セットを表します。これは、ユーザーの姓の文字です。

## <a name="powershell-for-microsoft-365-makes-it-easy-to-print-or-save-data"></a>PowerShell for Microsoft 365を使用すると、データを簡単に印刷または保存できます

Microsoft 365 管理センターでは、データの一覧を表示できます。 Skype for Business Online に対して有効になっているユーザーの一覧を表示するSkype for Business Online 管理センターの例を次に示します。

![Skype for Business Online 管理センターで、Skype for Business Online に対して有効になっているユーザーの一覧を表示する例です。](../media/o365-powershell-lync-users.png)

その情報をファイルに保存するには、ドキュメントまたはワークシートMicrosoft Excel貼り付ける必要があります。 どちらの場合も、追加の書式設定が必要になる場合があります。 さらに、Microsoft 365 管理センターでは、表示されたリストを直接印刷する方法は提供されません。

幸いにも、PowerShell を使用してリストを表示するだけでなく、Excelに簡単にインポートできるファイルに保存することもできます。 オンライン ユーザー データSkype for Businessコンマ区切り値 (CSV) ファイルに保存するコマンドの例を次に示します。これにより、Excel ワークシートのテーブルとして簡単にインポートできます。

```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Export-Csv -Path "C:\Logs\SfBUsers.csv" -NoTypeInformation
```

結果の例を次に示します。

![コンマ区切り値ファイルに保存されたSkype for Business Online ユーザー データのExcel ワークシートにインポートされたテーブルの例。](../media/o365-powershell-data-in-excel.png)

この PowerShell コマンドの解釈は次のとおりです。現在のMicrosoft 365 サブスクリプション (**Get-CsOnlineUser**)のすべてのSkype for Business Online ユーザーを取得し、ユーザー名、UPN、場所のみを取得します (**DisplayName、UserPrincipalName、UsageLocation を選択)、** その情報を C:\\Logs\\SfBUsers.csv (**Export-Csv -Path "C:\\Logs\\)" という名前の CSV ファイルに保存します。SfBUsers.csv" -NoTypeInformation**)。

オプションを使用して、このリストを XML ファイルまたは HTML ページとして保存することもできます。 実際、追加の PowerShell コマンドを使用すると、任意のカスタム書式設定を使用して、Excel ファイルとして直接保存できます。

リストを表示する PowerShell コマンドの出力を、Windowsの既定のプリンターに直接送信することもできます。 コマンドの例を次に示します。

```powershell
Get-CsOnlineUser | Select DisplayName, UserPrincipalName, UsageLocation | Out-Printer
```

印刷されたドキュメントは次のようになります。

![Windowsの既定のプリンターに直接送信された PowerShell コマンドの出力だった印刷されたドキュメントの例。](../media/o365-powershell-printed-data.png)

この PowerShell コマンドの解釈は、現在のMicrosoft 365 サブスクリプションのすべての Skype for Business Online ユーザーを取得し、ユーザー名、UPN、および場所のみを取得し、その情報を既定のWindows プリンター (**Out-Printer**) に送信することです。

印刷されたドキュメントの書式設定は、PowerShell コマンド ウィンドウの表示と同じです。 ハード コピーを取得するには、|を追加するだけです **コマンドの** 最後までプリンターを外します。

## <a name="powershell-for-microsoft-365-lets-you-manage-across-server-products"></a>PowerShell for Microsoft 365を使用すると、サーバー製品全体を管理できます

Microsoft 365を構成するコンポーネントは、連携するように設計されています。 たとえば、Microsoft 365に新しいユーザーを追加し、ユーザーの部署や電話番号などの情報を指定するとします。 その後、Microsoft 365 サービス (Skype for Business Online、Exchange、SharePoint) のいずれかでユーザーの情報にアクセスすると、その情報を利用できるようになります。

ただし、これは製品のスイートに共通する一般情報の場合です。 通常、製品固有の情報 (ユーザーのExchange メールボックスに関する情報など) は、スイート全体では使用できません。 たとえば、ユーザーのメールボックスが有効かどうかに関する情報は、Exchange管理センターでのみ使用できます。

すべてのユーザーに関する次のような情報を示すレポートを作成するとします。

- ユーザーの表示名

- ユーザーがMicrosoft 365に対してライセンスを付与されているかどうか

- ユーザーの Exchange メールボックスが有効になっているかどうか

- ユーザーが Skype for Business Online に対して有効になっているかどうか

このようなレポートをMicrosoft 365 管理センターで簡単に作成することはできません。 代わりに、Excel ワークシートなどの情報を格納する別のドキュメントを作成する必要があります。 次に、Microsoft 365 管理センターからすべてのユーザー名とライセンス情報を取得し、<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange管理センター</a>からメールボックス情報を取得し、Skype for Business Online 管理センターからオンライン情報Skype for Business取得し、その情報を結合します。

代わりに、PowerShell スクリプトを使用してレポートをコンパイルすることもできます。

次のサンプル スクリプトは、この記事でこれまでに見てきたコマンドよりも複雑です。 ただし、PowerShell を使用して、それ以外の場合は取得するのが困難な情報ビューを作成する可能性を示しています。 必要なリストをコンパイルして表示するスクリプトを次に示します。

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

1. 現在のMicrosoft 365 サブスクリプションのすべてのユーザーを取得し、$x (**$x = Get-AzureADUser**) という名前の変数に情報を格納します。
1. 変数$x内のすべてのユーザーに対して実行されるループを開始します **(foreach ($xの$i)。**
1. *$y* という名前の変数を定義し、その変数にユーザーのメールボックス情報を格納 **します ($y = Get-Mailbox -Identity $i.UserPrincipalName**)。
1. *IsMailBoxEnabled* という名前のユーザー情報に新しいプロパティを追加します。 ユーザーのメールボックスの IsMailBoxEnabled プロパティの値に設定 **します ($i | Add-Member -MemberType NoteProperty -Name IsMailboxEnabled -Value $y.IsMailboxEnabled**)。
1. *$y* という名前の変数を定義し、その変数にユーザーのSkype for Business Online 情報を格納 **します ($y = Get-CsOnlineUser -Identity $i.UserPrincipalName**)。
1. *EnabledForSfB* という名前のユーザー情報に新しいプロパティを追加します。 ユーザーの Skype for Businessオンライン情報 (**$i | Add-Member -MemberType NoteProperty -Name EnabledForSfB -Value $y.Enabled**) の Enabled プロパティの値に設定します。
1. ユーザーの一覧を表示しますが、名前、ライセンスを付与されているかどうか、およびメールボックスが有効になっているかどうかと、Skype for Business Online に対して有効になっているかどうかを示す 2 つの新しいプロパティ (**$x |DisplayName、IsLicensed、IsMailboxEnabled、EnabledforSfB**) を選択します。

## <a name="see-also"></a>関連項目

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)

[Microsoft 365 ユーザー アカウント、ライセンス、PowerShell を使用したグループを管理する](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)

[Windows PowerShell を使用して Microsoft 365 でレポートを作成する](use-windows-powershell-to-create-reports-in-microsoft-365.md)