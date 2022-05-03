---
title: テナント許可/ブロック一覧で許可とブロックを管理する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧で、許可とブロックを管理する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a067672a013f3e0ed7b9009604f8a4fe000ea47f
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65172814"
---
# <a name="manage-the-tenant-allowblock-list"></a>テナントの許可/禁止リストを管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) 組織にメールボックスが含まれているMicrosoft 365組織では、Exchange Onlineメールボックスがない場合は、EOP フィルターの判定に同意しない可能性があります。 たとえば、適切なメッセージが無効 (誤検知) としてマークされたり、不適切なメッセージが許可されたり (偽陰性) されたりすることがあります。

Microsoft 365 Defender ポータルのテナント許可/ブロック リストを使用すると、Microsoft 365フィルターの判定を手動でオーバーライドできます。 テナント許可/ブロック リストは、受信メッセージのメール フロー中 (組織内メッセージには適用されません)、ユーザーがクリックした時点で使用されます。 次の種類のオーバーライドを指定できます。

- ブロックする URL。
- ブロックするファイル。
- ブロックする送信者の電子メールまたはドメイン。
- 許可またはブロックするスプーフィングされた送信者。 [スプーフィング インテリジェンス分析情報](learn-about-spoof-intelligence.md)の許可またはブロックの判定をオーバーライドすると、スプーフィングされた送信者は、テナント許可/ブロックリストの [**スプーフィング**] タブにのみ表示される手動の許可エントリまたはブロック エントリになります。 スプーフィング インテリジェンスによって検出される前に、スプーフィングされた送信者の許可エントリまたはブロック エントリを手動で作成することもできます。
- 許可する URL。
- 許可するファイル。
- 許可する送信者の電子メールまたはドメイン。

この記事では、Microsoft 365 Defender ポータルまたは PowerShell (Exchange Online のメールボックスを持つMicrosoft 365組織の PowerShell をExchange Online、スタンドアロン EOP PowerShell を使用しない組織のテナント許可/ブロック リストでエントリを構成する方法について説明します。Exchange Online メールボックス)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[テナント許可/ブロック リスト**] ページに直接移動するには、次を使用<https://security.microsoft.com/tenantAllowBlockList>します。

- ファイルの SHA256 ハッシュ値を使用してファイルを指定します。 Windowsでファイルの SHA256 ハッシュ値を見つけるには、コマンド プロンプトで次のコマンドを実行します。

  ```console
  certutil.exe -hashfile "<Path>\<Filename>" SHA256
  ```

  値の例は `768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3a`. Perceptual hash (pHash) 値はサポートされていません。

- 使用可能な URL 値については、この記事の後半の [「テナント許可/ブロック 一覧](#url-syntax-for-the-tenant-allowblock-list) 」セクションの URL 構文で説明します。

- テナント許可/ブロック リストでは、送信者に対して最大 500 エントリ、URL のエントリは 500 エントリ、ファイル ハッシュの場合は 500 エントリ、スプーフィング (スプーフィングされた送信者) には 1024 エントリが許可されます。

- 各エントリの最大文字数は次のとおりです。
  - ファイル ハッシュ = 64
  - URL = 250

- エントリは 30 分以内にアクティブにする必要があります。

- 既定では、テナント許可/ブロック リストのエントリは 30 日後に期限切れになります。 日付を指定するか、期限切れにならないように設定できます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめExchange Online でアクセス許可を割り当てる必要があります。
  - **送信者、URL、ファイル**:
    - テナント許可/ブロック リストの値を追加および削除するには、次のメンバーである必要があります。
      - **組織の管理** または **セキュリティ管理者** の役割グループ (**セキュリティ管理者ロール**)
      - **Security Operator** ロール グループ (**テナント AllowBlockList Manager**)。
    - テナント許可/ブロック リストへの読み取り専用アクセスの場合は、次のメンバーである必要があります。
      - **グローバル リーダー**  の役割グループ
      - **セキュリティ 閲覧者** の役割グループ
  - **スプーフィング**: 次のいずれかの組み合わせ。
    - **組織の管理**
    - **セキュリティ管理者**<u>と</u>**表示専用構成** または **表示専用組織管理**。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  > [!NOTE]
  >
  > - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 *および* Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

## <a name="configure-the-tenant-allowblock-list"></a>テナント許可/ブロック リストを構成する

### <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する

Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 **[テナント許可/ブロック リスト**] ページに直接移動するには、次を使用<https://security.microsoft.com/tenantAllowBlockList>します。

すべてのブロックを追加するには、「 [テナント許可/ブロック一覧にブロックを追加](manage-tenant-blocks.md)する」を参照してください。

すべての許可を追加するには、 [テナント許可/ブロック リストの許可の追加に関するページ](manage-tenant-allows.md)を参照してください。

すべてのブロックと許可を変更および削除するには、「 [テナント許可/ブロック一覧のエントリを変更および削除](modify-remove-entries-tenant-allow-block.md)する」を参照してください。

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell"></a>PowerShell またはスタンドアロンの EOP PowerShell Exchange Online使用する

すべての許可とブロックを管理するには、「[テナントの許可/ブロックリストにブロックを追加する」、「テナントの許可/ブロックリスト](manage-tenant-blocks.md)[に許可を追加する」、「テナント許可/ブロックリスト](manage-tenant-allows.md)[のエントリを変更および削除する」](modify-remove-entries-tenant-allow-block.md)を参照してください。

## <a name="view-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストのエントリを表示する

1. Microsoft 365 Defender ポータルの [ルール **] セクションの** <https://security.microsoft.com>[**ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 **[テナント許可/ブロック リスト**] ページに直接移動するには、次を使用<https://security.microsoft.com/tenantAllowBlockList>します。

2. 目的のタブを選択します。 使用可能な列は、選択したタブによって異なります。

   - **送信者**:
     - **値**: 送信者のドメインまたは電子メール アドレス。
     - **アクション**: 値 **Allow** または **Block**。
     - **変更者**
     - **最終更新日時**
     - **[削除]**
     - **注**
   - **URL**:
     - **値**: URL。
     - **アクション**: 値 **Allow** または **Block**。
     - **変更者**
     - **最終更新日時**
     - **[削除]**
     - **注**
   - **ファイル**
     - **値**: ファイル ハッシュ。
     - **アクション**: 値 **Allow** または **Block**。
     - **変更者**
     - **最終更新日時**
     - **[削除]**
     - **注**
   - 「**スプーフィング**」
     - **スプーフィングされたユーザー**
     - **インフラストラクチャの送信**
     - **スプーフィングの種類**: 値 **内部** または **外部**。
     - **アクション**: 値 **[ブロック]** または **[許可] を指定** します。

   列見出しをクリックすると、昇順または降順で並べ替えることができます。

   [ **グループ]** をクリックして結果をグループ化できます。 使用可能な値は、選択したタブによって異なります。

   - **送信者**: **アクション** で結果をグループ化できます。
   - **URL**: **アクション** で結果をグループ化できます。
   - **ファイル**: **アクション** で結果をグループ化できます。
   - **スプーフィング**: **アクション** または **スプーフィングの種類** で結果をグループ化できます。

   [ **検索**] をクリックし、値の全部または一部を入力し、Enter キーを押して特定の値を見つけます。 完了したら、[検索のクリア] アイコンをクリックします ![。](../../media/m365-cc-sc-close-icon.png) **検索をクリアします**。

   [ **フィルター]** をクリックして結果をフィルター処理します。 **表示されるフィルター** ポップアップで使用できる値は、選択したタブによって異なります。

   - [**Senders (送信者)**]
     - **操作**
     - **有効期限が切れない**
     - **最終更新日**
     - **[削除]**
   - **Url**
     - **操作**
     - **有効期限が切れない**
     - **最終更新日**
     - **[削除]**
   - **ファイル**
     - **操作**
     - **有効期限が切れない**
     - **最終更新日時**
     - **[削除]**
   - 「**スプーフィング**」
     - **操作**
     - **スプーフィングの種類**

   完了したら、**[適用]** をクリックします。 既存のフィルターをクリアするには、[ **フィルター**] をクリックし、表示される **[フィルター** ] ポップアップで [ **フィルターのクリア**] をクリックします。

3. 完了したら、**[追加]** をクリックします。

## <a name="view-sender-file-or-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧で送信者、ファイル、または URL エントリを表示する

テナント許可/ブロック 一覧のブロック送信者、ファイル、または URL エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <Sender | FileHash | URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

この例では、指定したファイル ハッシュ値の情報を返します。

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

この例では、ブロックされているすべての URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

## <a name="view-spoofed-sender-entries"></a>スプーフィングされた送信者エントリを表示する

テナント許可/ブロックリストでスプーフィングされた送信者エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListSpoofItems [-Action <Allow | Block>] [-SpoofType <External | Internal>
```

次の使用例は、テナント許可/ブロック リスト内のすべてのスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems
```

この例では、内部であるすべての許可されたスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Allow -SpoofType Internal
```

次の使用例は、外部にある、ブロックされているすべてのスプーフィングされた送信者エントリを返します。

```powershell
Get-TenantAllowBlockListSpoofItems -Action Block -SpoofType External
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListSpoofItems](/powershell/module/exchange/get-tenantallowblocklistspoofitems)」を参照してください。

## <a name="url-syntax-for-the-tenant-allowblock-list"></a>テナント許可/ブロック リストの URL 構文

- IPv4 アドレスと IPv6 アドレスは許可されますが、TCP/UDP ポートは許可されません。

- ファイル名拡張子は許可されません (test.pdfなど)。

- Unicode はサポートされていませんが、Punycode はサポートされています。

- ホスト名は、次のすべてのステートメントに該当する場合に許可されます。
  - ホスト名にはピリオドが含まれています。
  - ピリオドの左側に少なくとも 1 つの文字があります。
  - ピリオドの右側には少なくとも 2 文字あります。

  たとえば、 `t.co` 許可されているか、 `.com` 許可されていないか `contoso.` などです。

- サブパスは許可に対して暗示されません。

  たとえば、. `contoso.com` `contoso.com/a`

- ワイルドカード (*) は、次のシナリオで使用できます。

  - サブドメインを指定するには、左側のワイルドカードの後にピリオドが続く必要があります。

    たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。

  - パスを指定するには、右のワイルドカードをスラッシュ (/) に従う必要があります。

    たとえば、 `contoso.com/*` 許可されているか、 `contoso.com*` 許可されていないか `contoso.com/ab*` などです。

  - `*.com*` が無効です (解決可能なドメインではなく、正しいワイルドカードがスラッシュに従っていません)。

  - IP アドレスではワイルドカードは使用できません。

- チルダ (~) 文字は、次のシナリオで使用できます。

  - 左側のチルダは、ドメインとすべてのサブドメインを意味します。

    たとえば`~contoso.com`、次のものが含まれます`contoso.com`。`*.contoso.com`

- すべてのプロトコルに URL エントリが適用されるため、プロトコル (たとえば、 `http://`、、 `https://`、 `ftp://`) を含む URL エントリは失敗します。

- ユーザー名またはパスワードはサポートされていないか、必須ではありません。

- 引用符 (' または ") は無効な文字です。

- URL には、可能な限りすべてのリダイレクトを含める必要があります。

### <a name="url-entry-scenarios"></a>URL エントリのシナリオ

有効な URL エントリとその結果については、次のセクションで説明します。

#### <a name="scenario-no-wildcards"></a>シナリオ: ワイルドカードなし

**エントリ**: `contoso.com`

- **一致を許可** する: contoso.com

- **一致しない許可**:

  - abc-contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **ブロックの一致**:

  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

- **一致しないブロック**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

**エントリ**: `*.contoso.com`

- **一致** と **ブロックの一致** を許可する:

  - www.contoso.com
  - xyz.abc.contoso.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部にある右のワイルドカード

**エントリ**: `contoso.com/a/*`

- **一致** と **ブロックの一致** を許可する:

  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>シナリオ: 左チルダ

**エントリ**: `~contoso.com`

- **一致** と **ブロックの一致** を許可する:

  - contoso.com
  - www.contoso.com
  - xyz.abc.contoso.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - 123contoso.com
  - contoso.com/abc
  - www.contoso.com/abc

#### <a name="scenario-right-wildcard-suffix"></a>シナリオ: 右ワイルドカード サフィックス

**エントリ**: `contoso.com/*`

- **一致** と **ブロックの一致** を許可する:

  - contoso.com/?q=whatever@fabrikam.com
  - contoso.com/a
  - contoso.com/a/b/c
  - contoso.com/ab
  - contoso.com/b
  - contoso.com/b/a/c
  - contoso.com/ba

- **一致しない** 許可と **一致しないブロック**: contoso.com

#### <a name="scenario-left-wildcard-subdomain-and-right-wildcard-suffix"></a>シナリオ: 左ワイルドカード サブドメインと右ワイルドカード サフィックス

**エントリ**: `*.contoso.com/*`

- **一致** と **ブロックの一致** を許可する:

  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - www.contoso.com/a
  - www.contoso.com/b/a/c
  - xyz.contoso.com/ba

- **一致しない許可** と **一致しないブロック**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左右のチルダ

**エントリ**: `~contoso.com~`

- **一致** と **ブロックの一致** を許可する:

  - contoso.com
  - contoso.com/a
  - www.contoso.com
  - www.contoso.com/b
  - xyz.abc.contoso.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - 123contoso.com
  - contoso.org

#### <a name="scenario-ip-address"></a>シナリオ: IP アドレス

**エントリ**: `1.2.3.4`

- **一致** と **ブロックの一致** を許可する: 1.2.3.4

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。

  - 1.2.3.4/a
  - 11.2.3.4/a

#### <a name="ip-address-with-right-wildcard"></a>右のワイルドカードを含む IP アドレス

**エントリ**: `1.2.3.4/*`

- **一致** と **ブロックの一致** を許可する:

  - 1.2.3.4/b
  - 1.2.3.4/baaaa

### <a name="examples-of-invalid-entries"></a>無効なエントリの例

次のエントリは無効です。

- **ドメイン値が見つからないか無効です**。

  - Contoso
  - \*.contoso.\*
  - \*.com
  - \*.pdf

- **テキストのワイルドカードまたは空白文字なし**:

  - \*contoso.com
  - contoso.com\*
  - \*1.2.3.4
  - 1.2.3.4\*
  - contoso.com/a\*
  - contoso.com/ab\*

- **ポートを含む IP アドレス**:

  - contoso.com:443
  - abc.contoso.com:25

- **説明以外のワイルドカード**:

  - \*
  - \*.\*

- **中央のワイルドカード**:

  - conto\* so.com
  - conto~so.com

- **二重ワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="domain-pair-syntax-for-spoofed-sender-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧のスプーフィングされた送信者エントリのドメイン ペア構文

テナント許可/ブロック リストのスプーフィングされた送信者のドメイン ペアでは、次の構文を使用します `<Spoofed user>, <Sending infrastructure>`。

- **スプーフィングされたユーザー**: この値には、メール クライアントの [ **差** 出人] ボックスに表示されるスプーフィングされたユーザーの電子メール アドレスが含まれます。 このアドレスは、アドレスとも `5322.From` 呼ばれます。 有効な値は次のとおりです。
  - 個々の電子メール アドレス (chris@contoso.com など)。
  - 電子メール ドメイン (contoso.com など)。
  - ワイルドカード文字 (たとえば)。 \*

- **インフラストラクチャの送信**: この値は、スプーフィングされたユーザーからのメッセージのソースを示します。 有効な値は次のとおりです。
  - 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン (fabrikam.com など)。
  - 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは /24 (たとえば、192.168.100.100/24) として \<source IP\>識別されます。

スプーフィングされた送信者を識別するための有効なドメイン ペアの例を次に示します。

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

スプーフィングされた送信者エントリの最大数は 1000 です。

ドメイン ペアを追加すると、スプーフィングされたユーザー *と* 送信インフラストラクチャの *組み合わせ* のみが許可またはブロックされます。 スプーフィングされたユーザーからの任意のソースからのメールは許可されず、スプーフィングされたユーザーの送信インフラストラクチャ ソースからの電子メールも許可されません。

たとえば、次のドメイン ペアの許可エントリを追加します。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングを許可できるのは、そのドメインからのメッセージ *と* 送信インフラストラクチャ ペアからのメッセージだけです。 gmail.com をスプーフィングしようとしている他の送信者は許可されません。 tms.mx.com から発信された他のドメインの送信者からのメッセージは、スプーフィング インテリジェンスによってチェックされます。
