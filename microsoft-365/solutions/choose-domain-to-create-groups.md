---
title: グループの作成時に使用するドメインMicrosoft 365する
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
recommendations: false
description: PowerShell を使用して電子メール アドレス ポリシーを構成して、Microsoft 365グループを作成するときに使用するドメインを選択する方法について説明します。
ms.openlocfilehash: c63542e707322040df379f3620ab893d23f6243656f787e9b72c6491b7b52232
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53893581"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>グループの作成時に使用するドメインMicrosoft 365する

一部の組織では、独立した複数のメール ドメインを使用して、ビジネスのさまざまな部分をセグメント化しています。 ユーザーがグループを作成するときに使用するドメインMicrosoft 365できます。
  
ユーザーが会社の既定の承認済みドメイン以外のドメインにグループを作成する必要がある場合、PowerShell を使ってメール アドレス ポリシー (EAP) を構成することでこれを許可できます。

PowerShell コマンドレットを実行する前に、組織に相談できるモジュールをダウンロードしてインストールします。 詳細については、「[リモート PowerShell による Exchange への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

## <a name="example-scenarios"></a>シナリオ例

たとえば、ビジネスのメイン ドメインが Contoso.com。 ただし、組織の既定で受け入れられるドメインは service.contoso.com。 つまり、グループはグループ (たとえば、service.contoso.com) に作成 jimsteam@service.contoso.com。
  
たとえば、組織でサブドメインも構成済みだとします。 これらのドメインにグループを作成する場合も、次の手順を実行します。
  
- 学生用の students.contoso.com
    
- 教職員メンバー用の faculty.contoso.com
    
次の 2 つのシナリオで、その実行方法について説明します。

> [!NOTE]
> 複数の EAP がある場合、優先度の順に評価されます。 値 1 は、優先度が最も高い値を意味します。 EAP が一致すると、それ以上の EAP は評価され、グループにスタンプされるアドレスは、一致した EAP に基いて行います。 > 指定した条件に一致する EAP がない場合、グループは組織の既定の受け入れドメインにプロビジョニングされます。 承認された[ドメインを追加する](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)方法の詳細については、「Exchange Onlineで受け入れドメインを管理する」を参照してください。
  
### <a name="scenario-1"></a>シナリオ 1

次の使用例は、組織のすべてのグループMicrosoft 365ドメインでプロビジョニングする groups.contoso.com します。
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>シナリオ 2

たとえば、グループが作成されるサブドメインMicrosoft 365制御するとします。 あなたの希望です：
  
- 学生 (部門が [学生] に設定されている **ユーザー)** によって作成されたグループは、students.groups.contoso.com されます。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- 教員が作成したグループ ([部署] が [教職員] または [電子メール アドレス] に設定されているユーザー **には、faculty.contoso.com)** が faculty.groups.contoso.com されます。 次のコマンドを使用します。
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- 他のユーザーが作成したグループは、ドメイン内 groups.contoso.com されます。 次のコマンドを使用します。
    
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

組織がハイブリッド シナリオで構成されている場合は、「Microsoft 365 グループをオンプレミス[Exchange](/exchange/hybrid-deployment/set-up-microsoft-365-groups)ハイブリッドで構成する」を参照して、組織が Microsoft 365 グループを作成するための要件を満たしていることを確認します。 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>電子メール アドレス ポリシー グループの使用に関する追加情報:

以下のいくつかの点を把握しておく必要あります。
  
- グループ作成の速度は、組織に構成されている EAP の数によって異なります。
    
- 管理者とユーザーは、グループを作成するときにドメインを変更することもできます。
    
- ユーザーのグループは、既に用意されている標準クエリ (ユーザーのプロパティ) を使用して決定されます。 サポートされている [フィルター可能なプロパティについては、-RecipientFilter パラメーターの Filterable](/powershell/exchange/recipientfilter-properties) プロパティを参照してください。 
    
- グループに EAP を構成しないと、グループの作成で既定の承認済みドメインが選択されます。
    
- 承認済みドメインを削除する場合は、最初に、EAP を更新する必要があります。そうしないと、グループのプロビジョニングが影響を受けます。
    
- 1 つの組織につき最大で 100 のメール アドレス ポリシーを構成できます。
    
## <a name="related-content"></a>関連コンテンツ

[コラボレーション ガバナンス計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step) (記事)

[コラボレーション ガバナンス 計画の作成](collaboration-governance-first.md) (記事)

[管理センター Microsoft 365グループを作成する](../admin/create-groups/create-groups.md)(記事)