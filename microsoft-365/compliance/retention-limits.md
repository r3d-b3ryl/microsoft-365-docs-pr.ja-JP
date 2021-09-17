---
title: アイテム保持ポリシーとアイテム保持ラベルの制限
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: アイテム保持ポリシーおよび保持ラベル ポリシーのポリシーおよびポリシーごとの項目の最大数を把握する
ms.openlocfilehash: 322a0c711ed1838dfd5349d43b1c3bcbf656618e
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399864"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>アイテム保持ポリシーとアイテム保持ラベルの制限

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[アイテム保持ポリシーと保持ラベル ポリシー](retention.md#retention-policies-and-retention-labels)を使用して、組織のデータを自動的に保持または削除する場合、注意すべき最大数がいくつかあります。

## <a name="maximum-number-of-retention-labels-per-tenant"></a>テナントごとの保持ラベルの最大数

テナントごとに最大 1,000 の保持ラベルがサポートされます。

## <a name="maximum-number-of-policies-per-tenant"></a>テナントごとのポリシーの最大数

1 つのテナントに最大 10,000 のポリシー (任意の構成) を含めることができます。 この最大値はデータ保持のため複数の異なるポリシーを包含します。またコンプライアンスのための他のポリシー、例えばDLP、情報バリア、電子情報開示、機密度ラベル等も同様です。

この ポリシー 10,000個の制限内では、ワークロード毎のデータ保持ポリシーの最大数にもいくつかの制限があります。

- Exchange (任意の構成): 1,800
- SharePoint または OneDrive: (自動的に含まれるすべてのサイト): 13
- SharePoint または OneDrive (含まれるまたは除外される特定の場所): 2,600

Microsoft Teams と Yammer のデータ保持ポリシーでは、データ保持目的でメールボックスを使用しますが、Exchange Online のポリシーの最大数は、Teams と Yammer のデータ保持ポリシーを含みません。

## <a name="maximum-number-of-items-per-policy"></a>ポリシーごとのアイテムの最大数

省略可能な構成を使用して、特定のユーザー、特定の Microsoft 365 グループ、特定のサイトに保持設定を適用する場合に、ポリシーごとに注意すべき制限事項がいくつかあります。 

保持するポリシーごとのアイテムの最大数:

- Exchange メールボックス: 1,000
- Microsoft 365 グループ: 1,000
- Teams のメッセージ: 1,000
- Teams のチャット: 1,000
- Yammer コミュニティのメッセージ: 1,000
- Yammer ユーザーのメッセージ: 1,000
- SharePoint サイト: 100
- OneDrive アカウント: 100

Skype for Business は特定のユーザーにスコープを設定する必要があり、ポリシーごとにサポートされる最大数は 1,000 です。

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

## <a name="maximum-number-of-items-for-disposition"></a>処理するアイテムの最大数

[コンテンツの処理](disposition.md)については、注意すべきいくつかの制限があります。

- 各保持ラベルのステージごとに 1,000,000 アイテムの処理が保留中

- アイテムが処理されてから最大 7 年間の処理の証明。その期間の保持ラベルごとに 1,000,000 アイテムの制限があります。 
    
レコードとしてマークされているアイテムについて、この制限である 1,000,000 を超える処理の証明が必要な場合は、[Microsoft サポート](../business-video/get-help-support.md)に連絡してください。
