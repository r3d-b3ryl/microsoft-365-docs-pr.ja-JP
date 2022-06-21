---
title: テナント許可/禁止リストを使用して URL を許可またはブロックする
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150manage-tenant-allows.md
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストで URL を許可またはブロックする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 69d9b4725e0a2c57dac8bb711655b9e0ff02e3e5
ms.sourcegitcommit: 7df8adc9e67ab65e413d7ea7bb0dcb9fd2da1a11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66185814"
---
# <a name="allow-or-block-urls-using-the-tenant-allowblock-list"></a>テナント許可/禁止リストを使用して URL を許可またはブロックする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータルまたは PowerShell を使用して、テナント許可/ブロック リスト内の URL を許可またはブロックできます。

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

  - サブドメインを指定するには、左側のワイルドカードの後にピリオドが続く必要があります。 (ブロックにのみ適用)

    たとえば、 `*.contoso.com` 許可されます。 `*contoso.com` 許可されません。

  - パスを指定するには、右のワイルドカードをスラッシュ (/) に従う必要があります。

    たとえば、 `contoso.com/*` 許可されているか、 `contoso.com*` 許可されていないか `contoso.com/ab*` などです。

  - `*.com*` が無効です (解決可能なドメインではなく、正しいワイルドカードがスラッシュに従っていません)。

  - IP アドレスではワイルドカードは使用できません。

- チルダ (~) 文字は、次のシナリオで使用できます。

  - 左側のチルダは、ドメインとすべてのサブドメインを意味します。

    たとえば`~contoso.com`、次のものが含まれます`contoso.com`。`*.contoso.com`

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
  - contoso.com
  - contoso.com/q=a@contoso.com

- **ブロックの一致**:
  - contoso.com
  - contoso.com/a
  - payroll.contoso.com
  - test.com/contoso.com
  - test.com/q=contoso.com
  - contoso.com
  - contoso.com/q=a@contoso.com

- **一致しないブロック**: abc-contoso.com

#### <a name="scenario-left-wildcard-subdomain"></a>シナリオ: 左ワイルドカード (サブドメイン)

> [!NOTE]
> このシナリオは、ブロックにのみ適用されます。

**エントリ**: `*.contoso.com`

- **ブロックの一致**:
  - contoso.com
  - xyz.abc.contoso.com

- **一致しないブロック**:
  - 123contoso.com
  - contoso.com
  - test.com/contoso.com
  - contoso.com/abc

#### <a name="scenario-right-wildcard-at-top-of-path"></a>シナリオ: パスの上部にある右のワイルドカード

**エントリ**: `contoso.com/a/*`

- **一致** と **ブロックの一致** を許可する:
  - contoso.com/a/b
  - contoso.com/a/b/c
  - contoso.com/a/?q=joe@t.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。
  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/q=a@contoso.com

#### <a name="scenario-left-tilde"></a>シナリオ: 左チルダ

**エントリ**: `~contoso.com`

- **一致** と **ブロックの一致** を許可する:
  - contoso.com
  - contoso.com
  - xyz.abc.contoso.com

- **[一致しない]** と [ **ブロックが一致しない]** を許可します。
  - 123contoso.com
  - contoso.com/abc
  - contoso.com/abc

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

> [!NOTE]
> このシナリオは、ブロックにのみ適用されます。

**エントリ**: `*.contoso.com/*`

- **ブロックの一致**:
  - abc.contoso.com/ab
  - abc.xyz.contoso.com/a/b/c
  - contoso.com/a
  - contoso.com/b/a/c
  - xyz.contoso.com/ba

- **一致しないブロック**: contoso.com/b

#### <a name="scenario-left-and-right-tilde"></a>シナリオ: 左右のチルダ

**エントリ**: `~contoso.com~`

- **一致** と **ブロックの一致** を許可する:

  - contoso.com
  - contoso.com/a
  - contoso.com
  - contoso.com/b
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

  - conto\*so.com
  - conto~so.com

- **二重ワイルドカード**

  - contoso.com/\*\*
  - contoso.com/\*/\*

## <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストにブロック URL エントリを作成する

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defenderを使用する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **URL** ] タブが選択されていることを確認し、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[ブロック URL]** ポップアップで、次の設定を構成します。
   - **ワイルドカードを使用して URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 個まで入力します。 URL エントリの構文の詳細については、「 [テナント許可/ブロック一覧の管理](tenant-allow-block-list.md)」の URL 構文セクションを参照してください。
   - **期限切れになることはありません**: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![オフに](../../media/scc-toggle-off.png)切り替えます)。[ **削除オン** ] ボックスを使用して、エントリの有効期限を指定します。

       または

     - 切り替えを右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替えます。](../../media/scc-toggle-on.png).
   - **省略可能な注**: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの URL を含むメールは _、フィッシング_ としてブロックされます。

### <a name="use-powershell"></a>PowerShell を使う

テナント許可/ブロック リストにブロック URL エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

この例では、contoso.com とすべてのサブドメイン (contoso.com や xyz.abc.contoso.com など) のブロック URL エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していないため、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

## <a name="create-allow-url-entries"></a>許可 URL エントリを作成する

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defenderを使用する

Microsoft 365 Defenderの [**申請]** ページで URL を許可します。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Actions & submissions**\>] に移動 **します**。 または、[ **申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **申請] ページで** [ **URL** ] タブを選択し、[分析用に Microsoft に送信] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

3. **[確認用に Microsoft に送信する]** ポップアップを使用して、URL を追加してメッセージを送信します。

4. [ **Microsoft に送信する理由を選択** する] セクションで、[ **ブロックされていない必要があります (誤検知)]** を選択します。

5. **[次のような URL を許可する] オプションを** オンにします。

6. **[以下の後に削除]** ドロップダウン リストで、許可オプションを機能させる期間を選択します。

7. **省略可能なメモ** を使用して許可を追加する理由を追加します。 

8. 完了したら、[ **送信]** ボタンをクリックします。

    :::image type="content" source="../../media/submit-url-for-analysis.png" alt-text="分析用の URL を送信する" lightbox="../../media/submit-url-for-analysis.png":::

> [!NOTE]
>
> - URL が再び検出されると、起爆または評価チェックのために URL が送信されず、他のすべての URL ベースのフィルターはスキップされます。
> - そのため、電子メール (この URL を含む) の場合は、メール フロー中に、残りのフィルターでクリーンなメールが見つかると、電子メールが配信されます。

## <a name="view-url-entries"></a>URL エントリを表示する

テナント許可/ブロック 一覧でブロック URL エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <URL> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

この例では、ブロックされているすべての URL を返します。

```powershell
Get-TenantAllowBlockListItems -ListType Url -Block
```

構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

## <a name="modify-url-entries"></a>URL エントリを変更する 

テナントの許可/ブロックリストの URL エントリを変更またはブロックするには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <URL> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

この例では、指定したブロック URL エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

## <a name="remove-url-entries"></a>URL エントリを削除する 

テナント許可/ブロック リストから許可 URL エントリまたはブロック URL エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <URL> -Ids <"Id1","Id2",..."IdN">
```
次の使用例は、指定したブロック URL エントリをテナント許可/ブロック リストから削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="related-articles"></a>関連記事

- [管理者による報告](admin-submission.md)
- [誤検知と偽陰性を報告する](report-false-positives-and-false-negatives.md)
- [テナント許可/ブロック一覧で許可とブロックを管理する](manage-tenant-allow-block-list.md)
- [テナント許可/ブロック リスト内のファイルを許可またはブロックする](allow-block-files.md)
- [テナントの許可/ブロック一覧で電子メールを許可またはブロックする](allow-block-email-spoof.md)
