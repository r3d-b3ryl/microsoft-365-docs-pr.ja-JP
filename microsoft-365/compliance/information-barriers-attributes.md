---
title: 情報バリアの属性
description: この記事は、情報バリア セグメントの定義に使用できる Azure Active Directory ユーザー アカウント属性のリファレンスです。
keywords: Microsoft 365、Microsoft Purview、コンプライアンス、情報バリア
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
ms.localizationpriority: ''
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1549a0cb3bf03056b37a75175c3b24416bec7b5
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66639778"
---
# <a name="information-barriers-attributes"></a>情報バリアの属性

Azure Active Directory の特定の属性は、情報バリア (IB) でユーザーをセグメント化するために使用できます。 セグメントが定義されると、これらのセグメントを IB ポリシーのフィルターとして使用できます。 たとえば、 **部門** を使用して、組織内の部門別にユーザーのセグメントを定義することができます (1 人の従業員が 2 つの部署で同時に働く場合を想定)。

この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。 情報バリアの詳細については、次のリソースを参照してください。

- [情報障壁](information-barriers.md)
- [Microsoft Teams で情報バリアのポリシーを定義する](information-barriers-policies.md)
- [IB ポリシーを編集 (または削除) する](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-ib-policies"></a>IB ポリシーで属性を使用する方法

この記事に記載されている属性は、ユーザーのセグメントを定義または編集するために使用できます。 定義されたセグメントは、[IB ポリシー](information-barriers-policies.md)のパラメーター (*UserGroupFilter* 値と呼ばれます) として機能します。

1. セグメントの定義に使用する属性を決定します。 (この記事の [「リファレンス」](#reference) セクションを参照してください)。

2. ユーザー アカウントに、手順 1 で選択した属性の値が入力されていることを確認します。 ユーザー アカウントの詳細を表示し、必要に応じてユーザー アカウントを編集して属性値を含めます。 

    - 複数のアカウントを編集する (または PowerShell を使用して 1 つのアカウントを編集する) 場合は、「[powerShell でユーザー アカウントのプロパティを構成するOffice 365](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)」を参照してください。

    - 1 つのアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する」を](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)参照してください。

3. 次の例のように、[PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)します。

    |**例**|**コマンドレット**|
    |:----------|:---------|
    | Department 属性を使用して Segment1 というセグメントを定義する | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | MemberOf 属性を使用して SegmentA というセグメントを定義します (この属性に "BlueGroup" などのグループ名が含まれているとします)。 | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | ExtensionAttribute1 を使用して DayTraders というセグメントを定義します (この属性に "DayTrader" などの役職が含まれているとします) | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。 たとえば、Department を使用して一部のセグメントを定義する場合は、 *Department* を使用してすべてのセグメントを定義 *します*。 *Department* を使用して一部のセグメントを定義し、*MemberOf を* 使用するセグメントを定義しないでください。 セグメントが重複していないことを確認します。各ユーザーは、1 つのセグメントに割り当てる必要があります。

## <a name="reference"></a>関連情報

次の表に、情報バリアで使用できる属性の一覧を示します。

|**Azure Active Directory プロパティ名<br/> (LDAP 表示名)**|**Exchange プロパティ名**|
|:---------------------------------------------------------------|:-------------------------|
| 共同 | 共同 |
| 会社名 | 会社名 |
| 部署 | Department |
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
| Proxyaddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| Targetaddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| メール | WindowsEmailAddress |
| 説明 | 説明 |
| 一員 | MemberOfGroup |

## <a name="resources"></a>リソース

- [Microsoft Teams で情報バリアのポリシーを定義する](information-barriers-policies.md)
- [情報バリアのトラブルシューティング](/office365/troubleshoot/information-barriers/information-barriers-troubleshooting)
- [情報障壁](information-barriers.md)
