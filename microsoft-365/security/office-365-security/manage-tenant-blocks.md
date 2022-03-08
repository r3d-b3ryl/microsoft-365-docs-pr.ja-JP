---
title: テナント許可/ブロック一覧でブロックを管理する
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
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧でブロックを構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4cca466ce4862cc93ec7521bf6bd00fe960f06a9
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63317431"
---
# <a name="add-blocks-in-the-tenant-allowblock-list"></a>テナントの許可/禁止リストの禁止リストを追加する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する 

### <a name="create-block-sender-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧でブロック送信者エントリを作成する

1. ポータルで、[Microsoft 365 Defenderルールのポリシー]  \>  \>  \> &[テナントの許可/ブロックリスト] **セクションに移動します**。

2. [テナントの **許可/ブロック一覧] ページ** で、[送信者] タブが選択されているのを確認し、[ブロック] アイコンを![クリックします。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[送信者のブロック]** フライアウトで、次の設定を構成します。
   - **送信者の電子メール アドレスまたは** ドメイン: 1 行に 1 つの送信者 (電子メール アドレスまたはドメイン) を入力し、最大 20 人まで入力します。
   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![トグルオフ)。](../../media/scc-toggle-off.png)[削除] ボックスを使用して、エントリの有効期限を指定します。

       または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替える。](../../media/scc-toggle-on.png).
   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの送信者からのメールはスパムとしてブロック *されます*。 

### <a name="create-block-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧でブロック URL エントリを作成する

1. ポータルで、[Microsoft 365 Defenderルールのポリシー]  \>  \>  \> &[テナントの許可/ブロックリスト] **セクションに移動します**。

2. [テナントの **許可/ブロック一覧] ページ** で、[ **URL** ] タブが選択されているのを確認し、[ブロック] アイコンを ![クリックします。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[URL のブロック]** フライアウトで、次の設定を構成します。
   - **ワイルドカードを使用して URL を追加** する: 1 行に 1 つの URL を入力し、最大 20 を入力します。 URL エントリの構文の詳細については、「テナント許可/ブロック一覧の管理」の「URL 構文 [」セクションを参照してください](tenant-allow-block-list.md)。
   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![トグルオフ)。](../../media/scc-toggle-off.png)[削除] ボックスを使用して、エントリの有効期限を指定します。

       または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替える。](../../media/scc-toggle-on.png).
   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらの URL を含むメールは、フィッシングとしてブロック *されます*。 

### <a name="create-block-file-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧でブロック ファイル エントリを作成する

1. ポータルで、[Microsoft 365 Defenderルールのポリシー]  \>  \>  \> &[テナントの許可/ブロックリスト] **セクションに移動します**。

2. [テナントの **許可/ブロック一覧] ページで** 、[ファイル] タブ **を選択し** 、[ブロック] アイコンを ![クリックします。](../../media/m365-cc-sc-create-icon.png) **ブロック**。

3. 表示される **[ファイルのブロック** ] フライアウトで、次の設定を構成します。
   - **ファイル ハッシュの追加**: 1 行に 1 つの SHA256 ハッシュ値を入力し、最大 20 を入力します。
   - **有効期限が切れる** ことはありません: 次のいずれかの手順を実行します。
     - 設定がオフになっていることを確認します (![トグルオフ)。](../../media/scc-toggle-off.png)[削除] ボックスを使用して、エントリの有効期限を指定します。

     または

     - 切り替えボタンを右に移動して、有効期限が切れなきエントリを構成します。 ![オンに切り替える。](../../media/scc-toggle-on.png).
   - **省略可能な** メモ: エントリの説明テキストを入力します。

4. 完了したら、**[追加]** をクリックします。

> [!NOTE]
> これらのファイルを含む電子メールはマルウェアとしてブロック *されます*。 

### <a name="create-spoofed-sender-block-entries"></a>スプーフィングされた送信者ブロック エントリを作成する

**注意**:

- スプー _フィング_ されたユーザーと、ドメイン ペアで定義されている送信インフラストラクチャの組み合わせだけが、スプーフィングを許可またはブロックされます。
- ドメイン ペアの許可エントリまたはブロック エントリを構成すると、そのドメイン ペアからのメッセージはスプーフィング インテリジェンスインサイトに表示されなくなりました。
- スプーフィングされた送信者のエントリは有効期限が切れることはありません。
- スプーフィングは、許可とブロックの両方をサポートします。

1. ポータルで、[Microsoft 365 Defenderルールのポリシー]  \>  \>  \> &[テナントの許可/ブロックリスト] **セクションに移動します**。

2. [テナントの **許可/ブロック一覧] ページ** で、[スプーフィング] タブ **を選択** し、[ブロック] アイコンを ![クリックします。](../../media/m365-cc-sc-create-icon.png) **[追加]** 。

3. 表示される **[新しいドメイン ペアの追加** ] フライアウトで、次の設定を構成します。
   - **ワイルドカードを使用して新しいドメイン ペア** を追加する: 1 行に 1 つのドメイン ペアを入力し、最大 20 を入力します。 スプーフィングされた送信者エントリの構文の詳細については、「 [Manage the Tenant Allow/Block List」を参照してください](tenant-allow-block-list.md)。
   - **スプーフィング** の種類: 次のいずれかの値を選択します。
     - **内部**: スプーフィングされた送信者は、組織 (受け入れドメイン) に属する [ドメイン内にいます](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)。
     - **外部**: スプーフィングされた送信者が外部ドメイン内にある。
   - **アクション**: [許可] **または [ブロック]** を **選択します**。

4. 完了したら、**[追加]** をクリックします。

## <a name="use-powershell"></a>PowerShell を使う

### <a name="add-block-sender-file-or-url-entries-to-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧にブロック送信者、ファイル、または URL エントリを追加する

テナント許可/ブロック一覧にブロック送信者、ファイル、または URL エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

次の使用例は、特定の日付に有効期限が切れる、指定した送信者のブロック送信者エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType Sender -Block -Entries "test@badattackerdomain.com", "test2@anotherattackerdomain.com" -ExpirationDate 8/20/2021
```

次の使用例は、有効期限が切れることはありません指定したファイルのブロック ファイル エントリを追加します。

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

次の使用例は、contoso.com およびすべてのサブドメイン (たとえば、contoso.com、www.contoso.com、および xyz.abc.contoso.com) のブロック URL エントリを追加します。 ExpirationDate パラメーターまたは NoExpiration パラメーターを使用しないので、エントリは 30 日後に期限切れになります。

```powershell
New-TenantAllowBlockListItems -ListType Url -Block -Entries ~contoso.com
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="add-spoofed-sender-block-entries"></a>スプーフィングされた送信者ブロック エントリの追加 

テナント許可/ブロック一覧にスプーフィングされた送信者エントリを追加するには、次の構文を使用します。

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

構文とパラメーターの詳細については、「 [New-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。
