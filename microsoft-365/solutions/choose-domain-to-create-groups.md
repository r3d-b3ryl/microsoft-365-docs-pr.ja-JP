---
title: Microsoft 365 グループの作成時に使用するドメインを選択する
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
recommendations: false
description: PowerShell を使用して電子メール アドレス ポリシーを構成して、Microsoft 365 グループを作成するときに使用するドメインを選択する方法について説明します。
ms.openlocfilehash: bd9fad340d136fe4cac228f94f1904761cff7071
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66490899"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Microsoft 365 グループの作成時に使用するドメインを選択する

一部の組織では、独立した複数のメール ドメインを使用して、ビジネスのさまざまな部分をセグメント化しています。 ユーザーが Microsoft 365 グループを作成するときに使用するドメインを指定できます。
  
ユーザーが会社の既定の承認済みドメイン以外のドメインにグループを作成する必要がある場合、PowerShell を使ってメール アドレス ポリシー (EAP) を構成することでこれを許可できます。

PowerShell コマンドレットを実行する前に、組織と対話できるモジュールをダウンロードしてインストールします。 [PowerShell への接続Exchange Online確認します](/powershell/exchange/connect-to-exchange-online-powershell)。

## <a name="example-scenarios"></a>シナリオ例

たとえば、ビジネスのメイン ドメインが Contoso.com であるとします。 ただし、組織の既定の承認済みドメインは service.contoso.com。 つまり、グループは service.contoso.com で作成されます (jimsteam@service.contoso.com など)。
  
組織でサブドメインも構成しているとします。 これらのドメインにもグループを作成する必要があります。
  
- 学生用の students.contoso.com
    
- 教職員メンバー用の faculty.contoso.com
    
次の 2 つのシナリオで、その実行方法について説明します。

> [!NOTE]
> 複数の EAP がある場合は、優先順位の順に評価されます。 値が 1 の場合は、優先度が最も高いことを意味します。 EAP が一致すると、それ以上の EAP は評価されません。グループにスタンプされるアドレスは、一致した EAP に従います。 > 指定した条件に一致する EAP がない場合、グループは組織の既定の承認済みドメインにプロビジョニングされます。 [承認済みドメインを追加する方法の詳細については、「Exchange Onlineで承認済](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)みドメインを管理する」を参照してください。
  
### <a name="scenario-1"></a>シナリオ 1

次の例では、組織内のすべての Microsoft 365 グループを groups.contoso.com ドメインにプロビジョニングする方法を示します。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>シナリオ 2

たとえば、Microsoft 365 グループが作成されるサブドメインを制御するとします。 あなたの希望です：
  
- students.groups.contoso.com ドメイン内の学生 ( **部門** が **学生** に設定されているユーザー) によって作成されたグループ。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- faculty.groups.contoso.com ドメイン内の教職員メンバー ( **部門** が **教職員または電子メール アドレス** に設定されているユーザー) によって作成されたグループには faculty.contoso.com が含まれます)。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 他のユーザーによって作成されたグループは、groups.contoso.com ドメインに作成されます。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```
> [!NOTE]
> このシナリオは、MX レコードがサード パーティのスパム フィルター処理を指している場合は機能しません。
 
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

組織がハイブリッド シナリオで構成されている場合は、「 [オンプレミスの Exchange ハイブリッドを使用して Microsoft 365 グループを構成](/exchange/hybrid-deployment/set-up-microsoft-365-groups) する」を参照して、組織が Microsoft 365 グループを作成するための要件を満たしていることを確認してください。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>電子メール アドレス ポリシー グループの使用に関する追加情報:

以下のいくつかの点を把握しておく必要あります。
  
- グループ作成の速度は、組織に構成されている EAP の数によって異なります。
    
- 管理者とユーザーは、グループを作成するときにドメインを変更することもできます。
    
- ユーザーのグループは、既に用意されている標準クエリ (ユーザーのプロパティ) を使用して決定されます。 サポートされている [フィルター可能なプロパティについては、-RecipientFilter パラメーター](/powershell/exchange/recipientfilter-properties) のフィルター可能なプロパティを確認してください。 
    
- グループに EAP を構成しないと、グループの作成で既定の承認済みドメインが選択されます。
    
- 承認済みドメインを削除する場合は、最初に、EAP を更新する必要があります。そうしないと、グループのプロビジョニングが影響を受けます。
    
- 1 つの組織につき最大で 100 のメール アドレス ポリシーを構成できます。
    
## <a name="related-content"></a>関連コンテンツ

[コラボレーション ガバナンス計画の推奨事項](collaboration-governance-overview.md#collaboration-governance-planning-recommendations) (記事)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md) (記事)

[管理センターで Microsoft 365 グループを作成する](../admin/create-groups/create-groups.md) (記事)
