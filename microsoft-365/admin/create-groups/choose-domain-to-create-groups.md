---
title: Office 365 グループを作成するときに使うドメインを選ぶ
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'PowerShell を使用して電子メールアドレスポリシーを構成することによって、Office 365 グループを作成するときに使用するドメインを選択する方法について説明します。 '
ms.openlocfilehash: 55fc99cd201e66166e7da164777cfba2f763609c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241409"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a>Office 365 グループを作成するときに使うドメインを選ぶ

 一部の組織では、独立した複数のメール ドメインを使用して、ビジネスのさまざまな部分をセグメント化しています。ユーザーが Office 365 グループを作成するときに使用する必要があるドメインを指定できます。
  
ユーザーが会社の既定の承認済みドメイン以外のドメインにグループを作成する必要がある場合、PowerShell を使ってメール アドレス ポリシー (EAP) を構成することでこれを許可できます。
  
PowerShell コマンドレットを実行するには、事前に Office 365 組織と通信するためのモジュールをダウンロードしインストールしておきます。詳細については、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=785881)」を参照してください。
  
## <a name="example-scenarios"></a>シナリオ例

ビジネスのメインドメインが Contoso.com であるとします。 しかし、組織の既定の承認済みドメインは service.contoso.com です。 これは、グループが service.contoso.com に作成されることを意味します (たとえば、jimsteam@service.contoso.com)。
  
組織にサブドメインが構成されているとします。 これらのドメインにグループを作成する必要があります。
  
- 学生用の students.contoso.com
    
- 教職員メンバー用の faculty.contoso.com
    
次の 2 つのシナリオで、その実行方法について説明します。
  
> [!NOTE]
> 複数の EAPs がある場合は、優先度の順に評価されます。 値が1の場合は、最も高い優先度を表します。 EAP が一致すると、それ以降の EAP は評価されず、グループにスタンプされたアドレスは一致した EAP によって取得されます。 > 指定された条件に一致する EAPs がない場合、グループは組織の既定の承認済みドメインでプロビジョニングされます。 承認済みドメインを追加する方法については、「 [Exchange Online で承認済みドメインを管理する」](https://go.microsoft.com/fwlink/p/?LinkId=785428)を参照してください。 
  
### <a name="scenario-1"></a>シナリオ 1

次の例に、groups.contoso.com ドメインで、組織内のすべての Office 365 グループをプロビジョニングする方法を示します。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>シナリオ 2

どのサブドメインの Office 365 グループを作成するかを制御する必要があるとします。 あなたの希望です：
  
- Students.groups.contoso.com ドメインで、学生 ( **Department**が**学生**に設定されているユーザー) によって作成されたグループ。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- 教職員メンバーによって作成されたグループ (**学科**に [**教職員] または [電子メールアドレスが含まれ**ているユーザー]) が faculty.groups.contoso.com ドメインにある。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 他のすべてのユーザーを groups.contoso.com ドメインに入れる。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>メール アドレス ポリシーを変更する

既存の EAP の優先順位またはメール アドレス テンプレートを変更するには、Set-EmailAddressPolicy コマンドレットを使用します。
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

EAP を変更しても、プロビジョニング済みのグループには影響ありません。
  
## <a name="delete-email-address-policies"></a>メール アドレス ポリシーを削除する

EAP を削除するには、Remove-EmailAddressPolicy コマンドレットを使用します。
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

EAP を変更しても、プロビジョニング済みのグループには影響ありません。
  
## <a name="hybrid-requirements"></a>ハイブリッド要件

組織がハイブリッド シナリオで構成されている場合は、「[Configure Office 365 Groups with on-premises Exchange hybrid (オンプレミスの Exchange ハイブリッドで Office 365 グループを構成する)](https://go.microsoft.com/fwlink/p/?LinkId=785430)」を参照して、組織が Office 365 グループを作成するための要件を満たしていることを確認します。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>電子メールアドレスポリシーグループの使用に関するその他の情報:

以下のいくつかの点を把握しておく必要あります。
  
- グループ作成の速度は、組織に構成されている EAP の数によって異なります。
    
- 管理者とユーザーは、グループを作成するときにドメインを変更することもできます。
    
- ユーザーのグループは、既に用意されている標準クエリ (ユーザーのプロパティ) を使用して決定されます。サポートされているフィルター可能なプロパティについては、「[-RecipientFilter パラメーターのフィルター可能なプロパティ](https://go.microsoft.com/fwlink/p/?LinkId=785918)」を参照してください。 
    
- グループに EAP を構成しないと、グループの作成で既定の承認済みドメインが選択されます。
    
- 承認済みドメインを削除する場合は、最初に、EAP を更新する必要があります。そうしないと、グループのプロビジョニングが影響を受けます。
    
- 1 つの組織につき最大で 100 のメール アドレス ポリシーを構成できます。
    
## <a name="related-articles"></a>関連記事

[管理センターで Office 365 グループを作成する](create-groups.md)
