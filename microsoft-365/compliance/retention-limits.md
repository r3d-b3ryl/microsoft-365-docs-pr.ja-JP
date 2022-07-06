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
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: アイテム保持ポリシーおよび保持ラベル ポリシーのポリシーおよびポリシーごとの項目の最大数を把握する
ms.openlocfilehash: fba8d0385831b4f05bbf0a967072d64eead5644a
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66633413"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>アイテム保持ポリシーとアイテム保持ラベルの制限

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

[アイテム保持ポリシーと保持ラベル ポリシー](retention.md#retention-policies-and-retention-labels)を使用して、組織のデータを自動的に保持または削除する場合、注意すべき最大数がいくつかあります。

## <a name="maximum-number-of-retention-labels-per-tenant"></a>テナントごとの保持ラベルの最大数

テナントごとに最大 1,000 の保持ラベルがサポートされます。

## <a name="maximum-number-of-policies-per-tenant"></a>テナントごとのポリシーの最大数

1 つのテナントに最大 10,000 のポリシー (任意の構成) を含めることができます。 この最大値はデータ保持のため複数の異なるポリシーを包含します。またコンプライアンスのための他のポリシー、例えばDLP、情報バリア、電子情報開示、訴訟保持、インプレース保持、機密度ラベル等も同様です。 ただし、この最大値は次の値を除外します。

- クラウド添付ファイル用でない場合の、SharePoint および OneDrive の自動ラベル付けポリシー。
- 公開済みの SharePoint と OneDrive のポリシーに、保持のみではなく削除のみ、または保持してから削除するラベルを付けます。
- [メッセージング レコード管理 (MRM)](/exchange/security-and-compliance/messaging-records-management/messaging-records-management) からの Exchange 保持ポリシー。

この ポリシー 10,000個の制限内では、ワークロード毎のデータ保持ポリシーの最大数にもいくつかの制限があります。

- Exchange (任意の構成): 1,800
  - メールボックスあたり: パフォーマンスに影響を与える前に推奨される最大値は 25 です。 50 はサポートされている制限です。
- SharePoint または OneDrive: (自動的に含まれるすべてのサイト): 13
- SharePoint または OneDrive (含まれるまたは除外される特定の場所): 2,600

> [!NOTE]
> Exchange と SharePoint のこれらの最大数は、保持に限定されませんが、eDiscovery 保留、訴訟保留、インプレース保留などの他の種類の保留ポリシーと共有されます。

Microsoft Teams と Yammer のデータ保持ポリシーでは、データ保持目的でメールボックスを使用しますが、Exchange Online のポリシーの最大数は、Teams と Yammer のデータ保持ポリシーを含みません。

## <a name="maximums-for-adaptive-policy-scopes"></a>アダプティブ ポリシー スコープの最大数

保持のためにポリシーに追加できる[アダプティブ ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)の数に制限はありません。ただし、各アダプティブ スコープを定義するクエリには、以下のとおり最大数にいくつかの制限があります:

- 属性値またはプロパティ値の文字列の長さ: 200
- グループのない場合またはグループ内の属性またはプロパティの数: 10
- グループの数: 10
- 高度なクエリの文字数: 10,000

グループ内の属性またはプロパティのグループ化はサポートされていません。 つまり、単一のアダプティブ スコープでサポートされるプロパティまたは属性の最大数は 100 です。

## <a name="maximum-number-of-items-per-policy"></a>ポリシーごとのアイテムの最大数

> [!IMPORTANT]
> [アダプティブ ポリシー スコープではなく静的ポリシー スコープ](retention.md#adaptive-or-static-policy-scopes-for-retention)を使用する場合にのみ適用できます。

静的スコープと省略可能な構成を使用して、特定のユーザー、特定の Microsoft 365 グループ、特定のサイトを含めるか、または除外する場合に、ポリシーごとに注意すべき制限事項がいくつかあります。

静的スコープに保持するポリシーごとのアイテムの最大数は以下のとおりです。

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

ただし、複数のポリシー結果を所有すると管理費が高くなります。 包含と除外を使用して複数のポリシーを作成して管理するよりも、アダプティブ スコープを使用することを検討してください。

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>最大数を超えないようにするために複数のポリシーを使用する例

以下の例は静的スコープの場合であり、保持ポリシーの場所だけを指定できず、前のセクションで説明した最大数を考慮しなければならない場合の設計ソリューションをいくつか提供しています。

交換例は、以下のとおりです。

- **要件**: 40,000 以上のユーザー メールボックスがある組織では、ほとんどのユーザーは 7 年間メールを保持する必要がありますが、特定のユーザーのサブセット (425) は 5 年間だけメールを保持する必要があります。

- **ソリューション**: Exchange メールの保持期間が 7 年のアイテム保持ポリシーを 1 つ作成し、ユーザーのサブセットを除外します。 次に、Exchange メールの第 2 のアイテム保持ポリシーを作成し、保持期間を 5 年として、ユーザーのサブセットを含めます。

    どちらの場合も、含まれる数と除外される数は、1 つのポリシーに対して指定されたメールボックスの最大数を下回っており、ユーザーのサブセットは、最初のポリシーから明示的に除外する必要があります。というのは、2 番目のポリシーよりも [長い保持期間](retention.md#the-principles-of-retention-or-what-takes-precedence) があるからです。ユーザーのサブセットに長いアイテム保持ポリシーが必要な場合は、最初のポリシーから除外する必要はありません。

    このソリューションでは、新規に組織に加入したユーザーがいる場合は、そのユーザーのメールボックスは自動的に 7 年間最初のポリシーに含まれ、サポートされている最大数に影響はありません。 しかし、5 年間の保持期間を必要とする新規ユーザーは、対象数と除外数に追加され、この制限は最大 1,000 です。

SharePoint の例は、以下のとおりです。

- **要件**: ある組織では、数千の SharePoint サイトがありますが、10 年の保持期間が必要なのは 2,000 サイトのみで、8,000 サイトでは 4 年の保持期間が必要です。

- **ソリューション**: 特定の 100 サイトを含む保持期間 10 年の SharePoint 用アイテム保持ポリシーを 20 個作成し、特定の 100 サイトを含む保持期間 4 年の SharePoint 用アイテム保持ポリシーを 80 個作成します。

    すべての SharePoint サイトを保持する必要はなく、特定のサイトを指定したアイテム保持ポリシーを作成する必要があります。 アイテム保持ポリシーは指定した 100 サイト以上には対応していないため、2 つの保持期間に対応したポリシーを複数作成する必要があります。 これらのアイテム保持ポリシーには、含まれるサイトの最大数が含まれているため、次に保持が必要な新しいサイトは、保持期間に関係なく、新しいアイテム保持ポリシーが必要になります。

## <a name="maximum-number-of-items-for-disposition"></a>処理するアイテムの最大数

[コンテンツの処理](disposition.md)については、注意すべきいくつかの制限があります。

- テナントあたりの最大数:
  - 1,600 万個のアイテムのうち、処理確認状態が「保留中の処理」または「承認済みの処理」のいずれかであるもの
  - 1,600 万個のアイテムがレコードとして自動的に処理されるものとしてマークされました (処理確認なし)

- 各保持ラベルの最大数:
  - 各保持ラベルのステージごとに 1,000,000 アイテムの処理が保留中
  - アイテムが処理されてから最大 7 年間の処理の証明。その期間の保持ラベルごとに 1,000,000 アイテムの制限があります。

    レコードとしてマークされているアイテムについて、この制限である 1,000,000 を超える処理の証明が必要な場合は、[Microsoft サポート](../admin/get-help-support.md)に連絡してください。
