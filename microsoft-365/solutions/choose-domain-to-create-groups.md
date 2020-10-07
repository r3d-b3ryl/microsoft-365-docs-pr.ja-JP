---
title: Microsoft 365 グループを作成するときに使用するドメインを選択する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: PowerShell を使用して電子メールアドレスポリシーを構成することによって、Microsoft 365 グループを作成するときに使用するドメインを選択する方法について説明します。
ms.openlocfilehash: bb6137a3dfce17bc9c94648e5ea9e12ec2776195
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377439"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Microsoft 365 グループを作成するときに使用するドメインを選択する

一部の組織では、独立した複数のメール ドメインを使用して、ビジネスのさまざまな部分をセグメント化しています。 ユーザーが Microsoft 365 グループを作成するときに使用するドメインを指定できます。
  
ユーザーが会社の既定の承認済みドメイン以外のドメインにグループを作成する必要がある場合、PowerShell を使ってメール アドレス ポリシー (EAP) を構成することでこれを許可できます。

PowerShell コマンドレットを実行する前に、組織に説明できるモジュールをダウンロードしてインストールしてください。 詳細については、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=785881)」を参照してください。

## <a name="example-scenarios"></a>シナリオ例

ビジネスのメインドメインが Contoso.com であるとします。 しかし、組織の既定の承認済みドメインは service.contoso.com です。 これは、グループが service.contoso.com に作成されることを意味します (たとえば、jimsteam@service.contoso.com)。
  
組織にサブドメインが構成されているとします。 これらのドメインにグループを作成する必要があります。
  
- 学生用の students.contoso.com
    
- 教職員メンバー用の faculty.contoso.com
    
次の 2 つのシナリオで、その実行方法について説明します。

> [!NOTE]
> 複数の EAPs がある場合は、優先度の順に評価されます。 値が1の場合は、最も高い優先度を表します。 EAP が一致すると、それ以降の EAP は評価されず、グループにスタンプされたアドレスは一致した EAP によって取得されます。 > 指定された条件に一致する EAPs がない場合、グループは組織の既定の承認済みドメインでプロビジョニングされます。 承認済みドメインを追加する方法については、「 [Exchange Online で承認済みドメインを管理する」](https://go.microsoft.com/fwlink/p/?LinkId=785428) を参照してください。
  
### <a name="scenario-1"></a>シナリオ 1

次の例は、groups.contoso.com ドメイン内の組織内のすべての Microsoft 365 グループをプロビジョニングする方法を示しています。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>シナリオ 2

どのサブドメインの Microsoft 365 グループを作成するかを制御する必要があるとします。 あなたの希望です：
  
- Students.groups.contoso.com ドメインで、学生 ( **Department** が **学生**に設定されているユーザー) によって作成されたグループ。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- 教職員メンバーによって作成されたグループ ( **学科** に [ **教職員] または [電子メールアドレスが含まれ**ているユーザー]) が faculty.groups.contoso.com ドメインにある。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 他のユーザーによって作成されたグループは、groups.contoso.com ドメイン内に作成されます。 次のコマンドを使用します。
    
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

組織がハイブリッドシナリオで構成されている場合は、「 [microsoft 365 グループをオンプレミスの Exchange ハイブリッドで構成](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) する」を参照して、組織が microsoft 365 グループを作成するための要件を満たしていることを確認してください。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>電子メールアドレスポリシーグループの使用に関するその他の情報:

以下のいくつかの点を把握しておく必要あります。
  
- グループ作成の速度は、組織に構成されている EAP の数によって異なります。
    
- 管理者とユーザーは、グループを作成するときにドメインを変更することもできます。
    
- ユーザーのグループは、既に用意されている標準クエリ (ユーザーのプロパティ) を使用して決定されます。 サポートされているフィルター可能なプロパティについて [は、-受信者フィルターパラメーターのフィルター処理されたプロパティを](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) 確認してください。 
    
- グループに EAP を構成しないと、グループの作成で既定の承認済みドメインが選択されます。
    
- 承認済みドメインを削除する場合は、最初に、EAP を更新する必要があります。そうしないと、グループのプロビジョニングが影響を受けます。
    
- 1 つの組織につき最大で 100 のメール アドレス ポリシーを構成できます。
    
## <a name="related-articles"></a>関連記事

[管理センターで Microsoft 365 グループを作成する](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
