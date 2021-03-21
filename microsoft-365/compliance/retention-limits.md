---
title: アイテム保持ポリシーとアイテム保持ラベルの制限
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: アイテム保持ポリシーおよび保持ラベル ポリシーのポリシーおよびポリシーごとの項目の最大数を把握する
ms.openlocfilehash: 53539df4d36fab02171e1ac06ba944ed3bea34e8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917243"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>アイテム保持ポリシーとアイテム保持ラベルの制限

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[アイテム保持ポリシーと保持ラベル ポリシー](retention.md#retention-policies-and-retention-labels)を使用して、組織のデータを自動的に保持または削除する場合、注意すべき最大数がいくつかあります。

## <a name="maximum-number-of-policies-per-tenant"></a>テナントごとのポリシーの最大数

1 つのテナントに最大 10,000 のポリシー (任意の構成) を含めることができます。 この最大数には、保持に関するさまざまなポリシーと、DLP ポリシーなどのコンプライアンスに関するその他のポリシーが含まれます。

ワークロードごとの保持に関するポリシーの最大数:

- Exchange Online (任意の構成): 1,800
- SharePoint または OneDrive: (自動的に含まれるすべてのサイト): 13
- SharePoint または OneDrive (含まれるまたは除外される特定の場所): 2,600

## <a name="maximum-number-of-items-per-policy"></a>ポリシーごとのアイテムの最大数

省略可能な構成を使用して、特定のユーザー、特定の Microsoft 365 グループ、特定のサイトに保持設定を適用する場合に、ポリシーごとに注意すべき制限事項がいくつかあります。 

保持するポリシーごとのアイテムの最大数:

  - 1,000 メールボックス (ユーザー メールボックスまたはグループ メールボックス)
  - 1,000 個の Microsoft 365 グループ
  - Teams のプライベート チャットのユーザー 1,000 人
  - 100 個のサイト (OneDrive または SharePoint)

ポリシーごとにこれらの制限があるので、これらの数を超える結果となる特定の対象または除外を使用する必要がある場合は、同じ保持設定を持つ追加の保持ポリシーを作成することができます。 このために複数の保持ポリシーを使用するいくつかの[シナリオ例とソリューション](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers)については、次のセクションを参照してください。

ただし、複数の保持ポリシーを所有すると管理費が高くなるので、本当に対象や除外が必要かどうかを常に確認する必要があります。 場所全体に適用される既定値の構成には制限がなく、この構成の選択は、複数のポリシーを作成して維持するよりも良い解決策になるかもしれないことに留意してください。

> [!TIP]
> このシナリオで複数のポリシーを作成して維持する必要がある場合は、[PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) を使用してより効率的な構成を検討してください。

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>最大数を超えないようにするために複数のポリシーを使用する例

以下の例では、保持ポリシーの場所だけを指定できず、前のセクションで説明した最大数を考慮しなければならない場合の設計ソリューションをいくつか提供しています。

交換例は、以下のとおりです。

- **要件**: 40,000 以上のユーザー メールボックスがある組織では、ほとんどのユーザーは 7 年間メールを保持する必要がありますが、特定のユーザーのサブセット (425) は 5 年間だけメールを保持する必要があります。

- **ソリューション**: Exchange メールの保持期間が 7 年のアイテム保持ポリシーを 1 つ作成し、ユーザーのサブセットを除外します。 次に、Exchange メールの第 2 のアイテム保持ポリシーを作成し、保持期間を 5 年として、ユーザーのサブセットを含めます。 
    
    どちらの場合も、対象となる数と除外される数が 1 つのポリシーの指定メールボックスの最大数を下回っており、ユーザーのサブセットは、第二のポリシーよりも[保持期間](retention.md#the-principles-of-retention-or-what-takes-precedence)が長いため、最初のポリシーから明示的に除外されなければなりません。 ユーザーのサブセットが保存期間のより長いアイテム保持ポリシーを必要とする場合は、最初のポリシーから除外する必要はありません。
     
    このソリューションでは、新規に組織に加入したユーザーがいる場合は、そのユーザーのメールボックスは自動的に 7 年間最初のポリシーに含まれ、サポートされている最大数に影響はありません。 しかし、5 年間の保持期間を必要とする新規ユーザーは、対象数と除外数に追加され、この制限は最大 1,000 です。

SharePoint の例は、以下のとおりです。

- **要件**: ある組織では、数千の SharePoint サイトがありますが、10 年の保持期間が必要なのは 2,000 サイトのみで、8,000 サイトでは 4 年の保持期間が必要です。

- **ソリューション**: 特定の 100 サイトを含む保持期間 10 年の SharePoint 用アイテム保持ポリシーを 20 個作成し、特定の 100 サイトを含む保持期間 4 年の SharePoint 用アイテム保持ポリシーを 80 個作成します。
    
    すべての SharePoint サイトを保持する必要はなく、特定のサイトを指定したアイテム保持ポリシーを作成する必要があります。 アイテム保持ポリシーは指定した 100 サイト以上には対応していないため、2 つの保持期間に対応したポリシーを複数作成する必要があります。 これらのアイテム保持ポリシーには、含まれるサイトの最大数が含まれているため、次に保持が必要な新しいサイトは、保持期間に関係なく、新しいアイテム保持ポリシーが必要になります。