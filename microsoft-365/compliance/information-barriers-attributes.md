---
title: 情報バリア ポリシーの属性
description: この記事は、情報バリア セグメントの定義に使用できる Azure Active Directory ユーザー アカウント属性のリファレンスです。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5e7815dbcfc6129685322a250351276476f8a9e3
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980051"
---
# <a name="attributes-for-information-barrier-policies"></a>情報バリア ポリシーの属性

Azure Active Directory の特定の属性を使用して、ユーザーをセグメント化できます。 セグメントを定義すると、それらのセグメントを情報バリア ポリシーのフィルターとして使用できます。 たとえば、部門を使用して、組織内の部署別にユーザーのセグメントを定義できます (同時に 2 つの部署に 1 人の従業員が働かされていないと仮定します)。

この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。 情報バリアの詳細については、次のリソースを参照してください。

- [情報障壁](information-barriers.md)
- [Microsoft Teams で情報障壁のポリシーを定義する](information-barriers-policies.md)
- [情報バリア ポリシーの編集 (または削除)](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>情報バリア ポリシーで属性を使用する方法

この記事に記載されている属性を使用して、ユーザーのセグメントを定義または編集できます。 定義されたセグメントは、情報バリア ポリシーのパラメーター *(UserGroupFilter* 値と呼ばれる) [として機能します](information-barriers-policies.md)。

1. セグメントの定義に使用する属性を決定します。 (この記事 [の「リファレンス](#reference) 」セクションを参照してください)。

2. 手順 1 で選択した属性の値がユーザー アカウントに入力されている必要があります。 ユーザー アカウントの詳細を表示し、必要に応じてユーザー アカウントを編集して属性値を含めます。 

    - 複数のアカウントを編集する (または、PowerShell を使用して 1 つのアカウントを編集する) には、「Office [365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)でユーザー アカウントのプロパティを構成する」を参照してください。

    - 単一のアカウントを編集するには [、「Azure Active Directory を](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)使用してユーザーのプロファイル情報を追加または更新する」を参照してください。

3. [PowerShell を使用して、次の](information-barriers-policies.md#define-segments-using-powershell)例のようなセグメントを定義します。

    |**例**|**コマンドレット**|
    |:----------|:---------|
    | Department 属性を使用して Segment1 というセグメントを定義する | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | MemberOf 属性を使用して SegmentA というセグメントを定義します (この属性に "BlueGroup" などのグループ名が含まれているとします)。 | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | ExtensionAttribute1 を使用して DayTraders というセグメントを定義します (この属性に "DayTrader" などのジョブ タイトルが含まれているとします)。 | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > セグメントを定義する場合は、すべてのセグメントに同じ属性を使用します。 たとえば、Department を使用していくつかのセグメントを定義する場合 *は、Department* を使用してすべてのセグメントを定義 *します*。 Department を使用して一部のセグメントを定義し *、MemberOf* を使用する他のセグメント *は定義しない*。 セグメントが重ならないようにします。各ユーザーは、1 つのセグメントに割り当てる必要があります。

## <a name="reference"></a>リファレンス

次の表に、情報バリアで使用できる属性を示します。

|**Azure Active Directory プロパティ名 <br/> (LDAP 表示名)**|**Exchange プロパティ名**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
| Department | Department |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | エイリアス |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| メール | WindowsEmailAddress |
| 説明 | 説明 |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>リソース

- [Microsoft Teams で情報障壁のポリシーを定義する](information-barriers-policies.md)
- [情報バリアのトラブルシューティング](information-barriers-troubleshooting.md)
- [情報障壁](information-barriers.md)
