---
title: テナントの許可/禁止リストのエントリを変更および削除する
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
description: 管理者は、セキュリティ ポータルのテナント許可/ブロックリストでエントリを変更および削除する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac612b51cab9069e50c4eec05948b3aa840b9cc9
ms.sourcegitcommit: 4d6a8e9d69a421d6c293b2485a8aa5e806b71616
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2022
ms.locfileid: "65182697"
---
# <a name="modify-and-remove-entries-in-the-tenant-allowblock-list"></a>テナントの許可/禁止リストのエントリを変更および削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365 Defender ポータルまたは PowerShell を使用して、テナント許可/ブロック リストのエントリを変更および削除できます。

## <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する

### <a name="modify-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック リストのエントリを変更する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. 変更するエントリの種類を含むタブを選択します。
   - [**Senders (送信者)**]
   - 「**スプーフィング**」
   - **Url**
   - **ファイル**

3. 変更するエントリを選択し、[編集] アイコンをクリックします ![。](../../media/m365-cc-sc-edit-icon.png) **編集**。 ポップアップで変更できる値は、前の手順で選択したタブによって異なります。
   - [**Senders (送信者)**]
     - **期限切れ** や有効期限を設定しないでください。
     - **省略可能なメモ**
   - 「**スプーフィング**」
     - **アクション**: 値を **[許可** ] または [ **ブロック**] に変更できます。
   - **Url**
     - **期限切れ** や有効期限を設定しないでください。
     - **省略可能なメモ**
   - **ファイル**
     - **期限切れ** や有効期限を設定しないでください。
     - **省略可能なメモ**

4. 完了したら、**[保存]** をクリックします。

> [!NOTE]
> 延長できるのは、作成日から最大で 30 日間です。 ブロックは最大 90 日間延長できますが、許可とは異なり、[期限切れなし] に設定することもできます。

### <a name="remove-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロック リストからエントリを削除する

1. Microsoft 365 Defender ポータルの <https://security.microsoft.com>[**ポリシー&ルール****脅威ポリシー** \> **ルール**\>] セクション\>**の [テナント許可/ブロック リスト**] に移動します。 または、 **テナント許可/ブロック リスト** ページに直接移動するには、 <https://security.microsoft.com/tenantAllowBlockList>.

2. 削除するエントリの種類を含むタブを選択します。
   - [**Senders (送信者)**]
   - 「**スプーフィング**」
   - **Url**
   - **ファイル**

3. 削除するエントリを選択し、[削除] アイコンをクリックします ![。](../../media/m365-cc-sc-delete-icon.png) **Delete**

4. 表示される警告ダイアログで、[削除] をクリック **します**。

## <a name="use-powershell"></a>PowerShell を使う

### <a name="modify-allow-or-block-sender-file-and-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧の送信者、ファイル、および URL エントリを変更またはブロックする

テナント許可/ブロックリストの送信者、ファイル、URL のエントリを変更またはブロックするには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

この例では、指定したブロック URL エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)」を参照してください。

### <a name="remove-allow-or-block-sender-url-or-file-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロックリストから送信者、URL、またはファイルエントリを削除する

テナント許可/ブロック一覧から送信者、ファイル、URL の許可またはブロックのエントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <Sender | FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

次の使用例は、指定したブロック URL エントリをテナント許可/ブロック リストから削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)」を参照してください。

### <a name="modify-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロックリストからスプーフィングされた送信者エントリを変更またはブロックする

テナント許可/ブロックリストのスプーフィングされた送信者エントリを変更またはブロックするには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

この例では、スプーフィングされた送信者エントリを許可からブロックに変更します。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

構文とパラメーターの詳細については、「 [Set-TenantAllowBlockListSpoofItems」を参照](/powershell/module/exchange/set-tenantallowblocklistspoofitems)してください。

### <a name="remove-allow-or-block-spoofed-sender-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロックリストからスプーフィングされた送信者エントリを削除またはブロックする

テナント許可/ブロックリストからスプーフィング送信者の許可エントリまたはブロックスプーフィング エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

構文とパラメーターの詳細については、「 [Remove-TenantAllowBlockListSpoofItems](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)」を参照してください。
