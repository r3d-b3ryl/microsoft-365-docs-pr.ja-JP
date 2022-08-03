---
title: テナント許可/禁止リストを使用して電子メールを許可またはブロックする
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
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストで、電子メールとスプーフィングされた送信者エントリを許可またはブロックする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 107aef5dd4cc3098d6e77f45e6b95352997ef738
ms.sourcegitcommit: d7193ee954c01c4172e228d25b941026c8d92d30
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2022
ms.locfileid: "67175006"
---
# <a name="allow-or-block-emails-using-the-tenant-allowblock-list"></a>テナント許可/禁止リストを使用して電子メールを許可またはブロックする

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータルまたは PowerShell を使用して、テナント許可/ブロック リストを使用して電子メール (スプーフィング メールを含む) を許可またはブロックできます。

## <a name="create-block-sender-entries"></a>ブロック送信者エントリを作成する 

### <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **ドメイン&アドレス** ] タブが選択されていることを確認し、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[ブロック ドメイン&アドレス** ポップアップ] で、次の設定を構成します。
   - **Email アドレスまたはドメイン**: 1 行あたり 1 つの電子メール アドレスまたはドメインを入力し、最大 20 個まで入力します。
   - **期限切れになることはありません**: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![オフに](../../media/scc-toggle-off.png)切り替えます)。[ **削除オン** ] ボックスを使用して、エントリの有効期限を指定します。

       or

     - 切り替えを右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替えます。](../../media/scc-toggle-on.png).
   - **省略可能な注**: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの送信者からのメールは、 _信頼度の高いスパム_ としてブロックされます (SCL = 9)。
> 組織内のユーザーは、これらのブロックされたドメインとアドレスに電子メールを送信できません。 "5.7.1 組織のテナント許可/ブロック リスト ポリシーによって 1 人以上の受信者がブロックされているため、メッセージを配信できません" という非配信レポートが表示されます。

### <a name="use-powershell"></a>PowerShell を使う

テナント許可/ブロック リストにブロック送信者エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <Sender> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

この例では、特定の日付に有効期限が切れる、指定した送信者のブロック送信者エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

## <a name="create-allow-sender-entries"></a>送信者を許可するエントリを作成する 

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defenderを使用する

Microsoft 365 Defenderの **[送信]** ページで送信者 (またはドメイン) を許可します。

許可エントリを追加するようにテナント許可/ブロック リストを直接変更することはできません。 代わりに、 [管理者の提出を](admin-submission.md) 使用して、ブロックされたメッセージを送信します。 このアクションにより、対応する URL、ファイル、スプーフィングされた送信者のドメイン ペア、偽装されたドメイン (またはユーザー)、または送信者がテナント許可/ブロック リストに追加されます。 アイテムがブロックされていない場合、許可は作成されません。 メッセージが誤ってブロックされた誤検知であると判断されたほとんどの場合、許可エントリは指定された有効期限日に削除されます。

> [!IMPORTANT]
> - Microsoft は許可エントリを管理するため、不要な送信者、URL、またはファイル許可エントリは不要なエントリが削除されます。 この動作により、組織が保護され、構成の誤った許可エントリを防ぐことができます。 判定に同意しない場合は、メッセージが依然として不適切と見なされる理由を判断するためにサポート ケースを開く必要がある場合があります。


1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Actions & submissions**\>] に移動 **します**。 または、[ **申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信]** ページで、[ **電子メール** ] タブが選択されていることを確認し、[分析用に Microsoft に送信] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

3. ネットワーク メッセージ ID を追加するか、電子メール ファイルをアップロードして、 **Microsoft に送信してレビュー** ポップアップを使用してメッセージを送信します。

4. [ **Microsoft に送信する理由を選択** する] セクションで、[ **ブロックされていない必要があります (誤検知)]** を選択します。

5. **[このオプションのようなメッセージを許可する**] をオンにします。

6. [ **削除後に削除]** ドロップダウン リストから、許可オプションを動作させる期間を指定します。

7. **[省略可能なメモ**] ボックスを使用して許可を追加する理由を追加します。 

8. 完了したら、[**送信**] を選択します。

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="分析の例として、Microsoft にマルウェアを送信します。" lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
>
> - メール フロー中に、悪意のあるメールであると判断されたフィルターに基づいて、許可が追加されます。 たとえば、送信者と URL が正しくないと判断され、それぞれに許可が追加されます。
> - そのエンティティ (送信者、ドメイン、URL、ファイル) が再び検出されると、そのエンティティに関連付けられているすべてのフィルターがスキップされます。
> - メール フロー中に、フィルターの残りの部分で、このエンティティを含む電子メールがクリーンであることが見つかると、電子メールが配信されます。 たとえば、送信者の許可 (認証に合格した場合) は、添付ファイルまたは URL に関連付けられたマルウェアと高信頼フィッシングを除くすべての判定をバイパスします。

## <a name="view-sender-entries"></a>送信者エントリを表示する 

テナント許可/ブロック リストでブロック送信者エントリを表示するには、次の構文を使用します。

```powershell
Get-TenantAllowBlockListItems -ListType <Sender> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```
構文とパラメーターの詳細については、「 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)」を参照してください。

## <a name="modify-sender-entries"></a>送信者エントリを変更する 

テナント許可/ブロックリストの送信者のエントリを変更またはブロックするには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <Sender> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

## <a name="remove-sender-entries"></a>送信者エントリを削除する 

テナント許可/ブロック 一覧から送信者の許可またはブロックエントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender> -Ids <"Id1","Id2",..."IdN">
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

## <a name="domain-pair-syntax-for-spoofed-sender-entries"></a>スプーフィングされた送信者エントリのドメイン ペア構文

テナント許可/ブロック リストのスプーフィングされた送信者のドメイン ペアでは、次の構文を使用します `<Spoofed user>, <Sending infrastructure>`。

- **スプーフィングされたユーザー**: この値には、メール クライアントの [ **差** 出人] ボックスに表示されるスプーフィングされたユーザーの電子メール アドレスが含まれます。 このアドレスは、アドレスとも `5322.From` 呼ばれます。 有効な値は次のとおりです。
  - 個々の電子メール アドレス (chris@contoso.com など)。
  - 電子メール ドメイン (contoso.com など)。
  - ワイルドカード文字 (たとえば)。 \*

- **インフラストラクチャの送信**: この値は、スプーフィングされたユーザーからのメッセージのソースを示します。 有効な値は次のとおりです。
  - 送信元電子メール サーバーの IP アドレスの逆引き DNS 参照 (PTR レコード) で見つかったドメイン (fabrikam.com など)。
  - 送信元 IP アドレスに PTR レコードがない場合、送信インフラストラクチャは /24 (たとえば、192.168.100.100/24) として \<source IP\>識別されます。
  - 検証済みの DKIM ドメイン。

スプーフィングされた送信者を識別するための有効なドメイン ペアの例を次に示します。

- `contoso.com, 192.168.100.100/24`
- `chris@contoso.com, fabrikam.com`
- `*, contoso.net`

スプーフィングされた送信者エントリの最大数は 1000 です。

ドメイン ペアを追加すると、スプーフィングされたユーザー *と* 送信インフラストラクチャの *組み合わせ* のみが許可またはブロックされます。 スプーフィングされたユーザーからの任意のソースからのメールは許可されず、スプーフィングされたユーザーの送信インフラストラクチャ ソースからの電子メールも許可されません。

たとえば、次のドメイン ペアの許可エントリを追加します。

- **ドメイン**: gmail.com
- **インフラストラクチャ**: tms.mx.com

スプーフィングを許可できるのは、そのドメインからのメッセージ _と_ 送信インフラストラクチャ ペアからのメッセージだけです。 gmail.com をスプーフィングしようとしている他の送信者は許可されません。 tms.mx.com から発信された他のドメインの送信者からのメッセージは、スプーフィング インテリジェンスによってチェックされます。

## <a name="create-blocked-spoofed-sender-entries"></a>ブロックされたスプーフィングされた送信者エントリを作成する

### <a name="use-microsoft-365-defender"></a>Microsoft 365 Defenderを使用する

> [!NOTE]
> これらの送信者からのEmailは _、フィッシング_ としてブロックされます。
>
> ドメイン ペアで定義されているスプーフィングされたユーザー _と_ 送信インフラストラクチャの _組み合わせ_ のみが、スプーフィングを許可またはブロックされます。
>
> ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンス分析情報に表示されなくなります。
>
> スプーフィングされた送信者のエントリが期限切れになることはありません。

1. Microsoft 365 Defender ポータルで、[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **スプーフィングされた送信者** ] タブを選択し、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **[追加]** 。

3. 表示される **[新しいドメイン ペアの追加]** ポップアップで、次の設定を構成します。
   - **ワイルドカードを使用して新しいドメイン ペアを追加する**:1 行あたり 1 つのドメイン ペアを入力し、最大 20 個まで入力します。 スプーフィングされた送信者エントリの構文の詳細については、「 [テナント許可/ブロックリストの管理](tenant-allow-block-list.md)」を参照してください。
   - **スプーフィングの種類**: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織に属するドメイン ( [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) にあります。
     - **外部**: スプーフィングされた送信者は外部ドメインにあります。
   - **アクション**: **[ブロック**] を選択します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの送信者からのメールは _フィッシング_ としてブロックされます。

### <a name="use-powershell"></a>PowerShell を使う

テナント許可/ブロック リストにスプーフィングされた送信者エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)」を参照してください。

## <a name="create-allowed-spoofed-sender-entries"></a>許可されたスプーフィングされた送信者エントリを作成する 

### <a name="use-the-tenant-allowblock-list-in-microsoft-365-defender"></a>Microsoft 365 Defenderでテナント許可/ブロック リストを使用する

> [!NOTE]
>
> - ドメイン ペアで定義されているスプーフィングされたユーザー _と_ 送信インフラストラクチャの _組み合わせ_ のみが、スプーフィングを許可またはブロックされます。
> - ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンス分析情報に表示されなくなります。
> - スプーフィングされた送信者のエントリが期限切れになることはありません。

1. Microsoft 365 Defender ポータルの [ルール **] セクション****の** <https://security.microsoft.com>[Email & コラボレーション \> **ポリシー&ルール** \> **脅威ポリシー** \> **テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **スプーフィングされた送信者** ] タブを選択し、[追加] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **[追加]** 。

3. 表示される **[新しいドメイン ペアの追加]** ポップアップで、次の設定を構成します。
   - **ワイルドカードを使用して新しいドメイン ペアを追加する**:1 行あたり 1 つのドメイン ペアを入力し、最大 20 個まで入力します。 スプーフィングされた送信者エントリの構文の詳細については、「 [テナント許可/ブロックリストの管理](tenant-allow-block-list.md)」を参照してください。
   - **スプーフィングの種類**: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織に属するドメイン ( [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) にあります。
     - **外部**: スプーフィングされた送信者は外部ドメインにあります。
   - **アクション**: **[許可**] を選択します。

4. 完了したら、**[追加]** をクリックします。

### <a name="use-admin-submission-in-microsoft-365-defender"></a>Microsoft 365 Defenderで管理申請を使用する

Microsoft 365 Defenderの **[送信]** ページを使用して、スプーフィングされた送信者を許可することもできます。

[管理者の提出を](admin-submission.md)使用して、ブロックされたメッセージを送信します。 このアクションにより、対応する URL、ファイル、スプーフィングされた送信者のドメイン ペア、偽装されたドメイン (またはユーザー)、または送信者がテナント許可/ブロック リストに追加されます。 アイテムがブロックされていない場合、許可は作成されません。 

> [!IMPORTANT]
>
> - スプーフィングでは、組織内、組織間、DMARC スプーフィングを処理できます。
> - 管理者申請の省略可能なメモは、スプーフィングには適用されません。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Actions & submissions**\>] に移動 **します**。 または、[ **申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信]** ページで、[ **電子メール** ] タブが選択されていることを確認し、[分析用に Microsoft に送信] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

3. ネットワーク メッセージ ID を追加するか、電子メール ファイルをアップロードして、 **Microsoft に送信してレビュー** ポップアップを使用してメッセージを送信します。

4. [ **Microsoft に送信する理由を選択** する] セクションで、[ **ブロックされていない必要があります (誤検知)]** を選択します。

5. **[このオプションのようなメッセージを許可する**] をオンにします。

6. [ **Remove after]\(削除後** の削除\) ドロップダウン リストから、許可オプションが機能する期間を指定します。ただし、スプーフィングでは適用されませんが、有効期限が切れることはありません。

7. 完了したら、[**送信**] を選択します。

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="分析の例として、Microsoft にマルウェアを送信します。" lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
>
> - スプーフィングされた送信者のドメイン ペアが作成され、[**テナント許可/ブロック] リスト** ページの [**スプーフィングされた送信者**] タブに表示されます。


### <a name="use-powershell"></a>PowerShell を使う

[PowerShell](/powershell/exchange/exchange-online-powershell) のテナント許可/ブロック リストにスプーフィングされた送信者エントリExchange Online追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)」を参照してください。

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

## <a name="modify-spoofed-sender-entries"></a>スプーフィングされた送信者エントリを変更する 

テナント許可/ブロックリストのスプーフィングされた送信者エントリを変更またはブロックするには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

この例では、スプーフィングされた送信者エントリを許可からブロックに変更します。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListSpoofItems」を参照](/powershell/module/exchange/set-tenantallowblocklistspoofitems)してください。

## <a name="remove-spoofed-sender-entries"></a>スプーフィングされた送信者エントリを削除する 

テナント許可/ブロックリストからスプーフィング送信者の許可エントリまたはブロックスプーフィング エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)」を参照してください。

## <a name="create-impersonated-sender-entries"></a>偽装された送信者エントリを作成する

### <a name="use-admin-submission-in-microsoft-365-defender"></a>Microsoft 365 Defenderで管理申請を使用する

Microsoft 365 Defenderの **[送信]** ページを使用して、偽装された送信者を許可することもできます。

[管理者の提出を](admin-submission.md)使用して、ブロックされたメッセージを送信します。 このアクションにより、対応する URL、ファイル、スプーフィングされた送信者のドメイン ペア、偽装されたドメイン (またはユーザー)、または送信者がテナント許可/ブロック リストに追加されます。 アイテムがブロックされていない場合、許可は作成されません。 

> [!IMPORTANT]
>
> - 偽装では、ドメインとユーザーの偽装を処理できます。
> - グラフの偽装は、現時点ではここでは処理されません。

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**Actions & submissions**\>] に移動 **します**。 または、[ **申請]** ページに直接移動するには、 <https://security.microsoft.com/reportsubmission>.

2. [ **送信]** ページで、[ **電子メール** ] タブが選択されていることを確認し、[分析用に Microsoft に送信] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **分析のために Microsoft に送信します**。

3. ネットワーク メッセージ ID を追加するか、電子メール ファイルをアップロードして、 **Microsoft に送信してレビュー** ポップアップを使用してメッセージを送信します。

4. [ **Microsoft に送信する理由を選択** する] セクションで、[ **ブロックされていない必要があります (誤検知)]** を選択します。

5. **[このオプションのようなメッセージを許可する**] をオンにします。

6. [ **削除後に削除]** ドロップダウン リストから、権限借用された許可には適用されませんが、有効期限が切れることがないため、許可オプションを使用する期間を指定します。

7. 完了したら、[**送信**] を選択します。

  :::image type="content" source="../../media/admin-submission-allow-messages.png" alt-text="分析の例として、Microsoft にマルウェアを送信します。" lightbox="../../media/admin-submission-allow-messages.png":::

> [!NOTE]
> 偽装されたドメイン (またはユーザー) が作成され、フィッシング対策ポリシーの **[信頼された送信者とドメイン** ] セクションに <https://security.microsoft.com/antiphishing>表示されます。

## <a name="related-articles"></a>関連記事

- [管理者による報告](admin-submission.md)
- [誤検知と偽陰性を報告する](report-false-positives-and-false-negatives.md)
- [テナント許可/ブロック一覧で許可とブロックを管理する](manage-tenant-allow-block-list.md)
- [テナント許可/ブロック リスト内のファイルを許可またはブロックする](allow-block-files.md)
- [テナント許可/ブロック リストの URL を許可またはブロックする](allow-block-urls.md)
