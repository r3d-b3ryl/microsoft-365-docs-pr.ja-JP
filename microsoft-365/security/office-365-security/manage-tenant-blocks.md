---
title: テナント許可/ブロックリストでブロックを管理する
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
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧でブロックを構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1ea87a29d93c43b89bcfb482d185bd4b397dcc5b
ms.sourcegitcommit: e3bc6563037bd2cce2abf108b3d1bcc2ccf538f6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/15/2022
ms.locfileid: "64862458"
---
# <a name="add-blocks-in-the-tenant-allowblock-list"></a>テナントの許可/禁止リストの禁止リストを追加する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する 

### <a name="create-block-sender-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストにブロック送信者エントリを作成する

1. Microsoft 365 Defender ポータルで、[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **送信者** ] タブが選択されていることを確認し、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[送信者のブロック** ] ポップアップで、次の設定を構成します。
   - **送信者の電子メール アドレスまたはドメイン**: 1 行あたり 1 つの送信者 (電子メール アドレスまたはドメイン) を最大 20 個まで入力します。
   - **期限切れになることはありません**: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![オフに](../../media/scc-toggle-off.png)切り替えます)。[ **削除オン** ] ボックスを使用して、エントリの有効期限を指定します。

       or

     - 切り替えを右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替えます。](../../media/scc-toggle-on.png).
   - **省略可能な注**: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの送信者からのメールは、 *高信頼スパム (SCL = 9)* としてブロックされます。 

### <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストにブロック URL エントリを作成する

1. Microsoft 365 Defender ポータルで、[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **URL** ] タブが選択されていることを確認し、[ブロック] アイコンをクリックします ![。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[ブロック URL]** ポップアップで、次の設定を構成します。
   - **ワイルドカードを使用して URL を追加する**: 1 行に 1 つの URL を入力し、最大 20 個まで入力します。 URL エントリの構文の詳細については、「 [テナント許可/ブロック一覧の管理](tenant-allow-block-list.md)」の URL 構文セクションを参照してください。
   - **期限切れになることはありません**: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![オフに](../../media/scc-toggle-off.png)切り替えます)。[ **削除オン** ] ボックスを使用して、エントリの有効期限を指定します。

       or

     - 切り替えを右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替えます。](../../media/scc-toggle-on.png).
   - **省略可能な注**: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの URL を含むメールは *、フィッシング* としてブロックされます。 

### <a name="create-block-file-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストにブロック ファイル エントリを作成する

1. Microsoft 365 Defender ポータルで、[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **ファイル** ] タブを選択し、[ブロック] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[ブロック ファイル** ] ポップアップで、次の設定を構成します。
   - **ファイル ハッシュを追加** する: 行ごとに 1 つの SHA256 ハッシュ値を入力し、最大 20 個まで入力します。
   - **期限切れになることはありません**: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![オフに](../../media/scc-toggle-off.png)切り替えます)。[ **削除オン** ] ボックスを使用して、エントリの有効期限を指定します。

     or

     - 切り替えを右に移動して、期限切れにならないようにエントリを構成します。 ![オンに切り替えます。](../../media/scc-toggle-on.png).
   - **省略可能な注**: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらのファイルを含む電子メールは *、マルウェア* としてブロックされます。 

### <a name="create-spoofed-sender-block-entries"></a>スプーフィングされた送信者ブロック エントリを作成する

**注意**:

- ドメイン ペアで定義されているスプーフィングされたユーザー _と_ 送信インフラストラクチャの _組み合わせ_ のみが、スプーフィングを許可またはブロックされます。
- ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンス分析情報に表示されなくなります。
- スプーフィングされた送信者のエントリが期限切れになることはありません。
- スプーフィングでは、許可とブロックの両方がサポートされます。

1. Microsoft 365 Defender ポータルで、[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。

2. [ **テナントの許可/ブロック一覧** ] ページで、[ **スプーフィング** ] タブを選択し、[ブロック] アイコンをクリック ![します。](../../media/m365-cc-sc-create-icon.png) **[追加]** 。

3. 表示される **[新しいドメイン ペアの追加]** ポップアップで、次の設定を構成します。
   - **ワイルドカードを使用して新しいドメイン ペアを追加する**:1 行あたり 1 つのドメイン ペアを入力し、最大 20 個まで入力します。 スプーフィングされた送信者エントリの構文の詳細については、「 [テナント許可/ブロックリストの管理](tenant-allow-block-list.md)」を参照してください。
   - **スプーフィングの種類**: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織に属するドメイン ( [承認済みドメイン](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)) にあります。
     - **外部**: スプーフィングされた送信者は外部ドメインにあります。
   - **アクション**: **[許可]** または [ブロック] を選択 **します**。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-powershell"></a>PowerShell を使う

### <a name="add-block-sender-file-or-url-entries-to-the-tenant-allowblock-list"></a>ブロック送信者、ファイル、または URL エントリをテナント許可/ブロック リストに追加する

テナント許可/ブロック リストにブロック送信者、ファイル、または URL エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

この例では、特定の日付に有効期限が切れる、指定した送信者のブロック送信者エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

次の使用例は、有効期限が切れない指定されたファイルのブロック ファイル エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

この例では、contoso.com とすべてのサブドメイン (contoso.com、www.contoso.com、xyz.abc.contoso.com など) のブロック URL エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用していないため、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)」を参照してください。

### <a name="add-spoofed-sender-block-entries"></a>スプーフィングされた送信者ブロック エントリを追加する 

テナント許可/ブロック リストにスプーフィングされた送信者エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)」を参照してください。
