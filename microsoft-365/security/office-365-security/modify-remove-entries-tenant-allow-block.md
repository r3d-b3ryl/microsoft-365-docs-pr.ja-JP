---
title: テナント許可/ブロック一覧のエントリを変更および削除する
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、セキュリティ ポータルのテナント許可/ブロック一覧でエントリを変更および削除する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 23c390babc64909aa860554437b60e2370d0fd1f
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53542569"
---
# <a name="modify-and-remove-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧のエントリを変更および削除する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

ポータルまたは PowerShell Microsoft 365 Defenderを使用して、テナント許可/ブロック一覧のエントリを変更および削除できます。

## <a name="use-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルを使用する

### <a name="modify-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧のエントリを変更する

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. 変更するエントリの種類を含むタブを選択します。
   - **URL**
   - **Files**
   - 「**スプーフィング**」

3. 変更するエントリを選択し、[編集] アイコン [編集] ![ を ](../../media/m365-cc-sc-edit-icon.png) **クリックします**。 表示されるフライアウトで変更できる値は、前の手順で選択したタブによって異なっています。
   - **URL**
     - **有効期限や有効期限** はありません。
     - **省略可能なメモ**
   - **Files**
     - **有効期限や有効期限** はありません。
     - **省略可能なメモ**
   - 「**スプーフィング**」
     - **アクション**: 値を [許可] または [ブロック **] に****変更できます**。
4. 完了したら、**[保存]** をクリックします。

### <a name="remove-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧からエントリを削除する

1. このポータルMicrosoft 365 Defender、[ポリシー] & **[** 脅威ポリシー ルール] セクションの [テナントの許可/ブロックリスト \>  \>  \> **] に移動します**。

2. 削除するエントリの種類を含むタブを選択します。
   - **URL**
   - **Files**
   - 「**スプーフィング**」

3. 削除するエントリを選択し、[削除] アイコン [削除] ![ を ](../../media/m365-cc-sc-delete-icon.png) **クリックします**。

4. 表示される警告ダイアログで、[削除] を **クリックします**。

## <a name="use-powershell"></a>PowerShell を使う

### <a name="modify-block-file-and-url-entries-in-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更する

テナント許可/ブロック一覧のブロック ファイルと URL エントリを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

次の使用例は、指定したブロック URL エントリの有効期限を変更します。

```powershell
Set-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -ExpirationDate "5/30/2020"
```

構文とパラメーターの詳細については [、「Set-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="remove-url-or-file-entries-from-the-tenant-allowblock-list"></a>テナント許可/ブロック一覧から URL またはファイル エントリを削除する

テナント許可/ブロック一覧からファイルエントリと URL エントリを削除するには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash | Url> -Ids <"Id1","Id2",..."IdN">
```

次の使用例は、指定したブロック URL エントリをテナント許可/ブロック一覧から削除します。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSPAAAA0"
```

構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistitems)。

### <a name="modify-allow-or-block-spoofed-sender-entries"></a>スプーフィングされた送信者エントリの許可またはブロックを変更する

テナント許可/ブロック一覧でスプーフィングされた送信者エントリの許可またはブロックを変更するには、次の構文を使用します。

```powershell
Set-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN"> -Action <Allow | Block>
```

次の使用例は、スプーフィングされた送信者エントリを許可からブロックに変更します。

```powershell
Set-TenantAllowBlockListItems -Ids "RgAAAAAI8gSyI_NmQqzeh-HXJBywBwCqfQNJY8hBTbdlKFkv6BcUAAAl_QCZAACqfQNJY8hBTbdlKFkv6BcUAAAl_oSRAAAA" -Action Block
```

構文とパラメーターの詳細については [、「Set-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/set-tenantallowblocklistspoofitems)。

### <a name="remove-allow-or-block-spoofed-sender-entries"></a>スプーフィングされた送信者エントリを許可またはブロックする

テナント許可/ブロック一覧からスプーフィング送信者エントリを許可またはブロックするには、次の構文を使用します。

```powershell
Remove-TenantAllowBlockListSpoofItems -Ids <"Id1","Id2",..."IdN">
```

構文とパラメーターの詳細については [、「Remove-TenantAllowBlockListSpoofItems」を参照してください](/powershell/module/exchange/remove-tenantallowblocklistspoofitems)。