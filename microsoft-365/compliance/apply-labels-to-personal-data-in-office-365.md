---
title: 個人データにラベルを適用する
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: Office のラベルを一般データ保護規則 (GDPR) 保護計画の一部として使用する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a7bea2abeaec7a858b3cfc693603c46c0f2a416a
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126818"
---
# <a name="apply-labels-to-personal-data"></a>個人データにラベルを適用する

 GDPR 保護計画の一環として、分類ラベルを使用している場合は、このトピックを使用します。 

Microsoft 365 で個人データを保護するためにラベルを使用している場合は、[保持ラベル](retention.md#retention-labels)を使用することをお勧めします。 保持ラベルを使用すると、次のことができます。
- アドバンスト データ ガバナンスを使用して、機密情報の種類やその他の基準に基づいてラベルを自動的に適用できます。
- データ損失防止機能を備えた保持ラベルを使用して、保護を適用できます。 
- 電子情報開示とコンテンツの検索でラベルを使用できます。 

現在、Cloud App Security は保持ラベルをサポートしていません。ただし、Microsoft 365 の機密情報を Cloud App Security と併用して、別の SaaS アプリにある個人データを監視することはできます。

[機密ラベル](sensitivity-labels.md)は現在、オンプレミスのファイル、その他のクラウド サービスのファイル、プロバイダーにラベルを適用する場合に推奨されています。 また、営業秘密ファイルなどのデータ保護用の Azure Information Protection 暗号化を必要とする Microsoft 365 のファイルにも推奨されます。

現時点では、GDPR の対象となるデータを含む Microsoft 365 のファイルに対して Azure Information Protection を使用して暗号化を適用することは、推奨されていません。 現在、Microsoft 365 サービスでは AIP で暗号化されたファイルへの読み取りはできません。 そのため、サービスでこれらのファイル内の機密データを検索することはできません。

保持ラベルは Exchange Online のメールに適用できます。これらのラベルは Microsoft 365 のデータ損失防止と連動することができます。 

![Microsoft 365 のラベルと Azure Information Protection のラベル](../media/Apply-labels-to-personal-data-in-Office-365-image1.png)


この図について:

-   SharePoint Online および OneDrive for Business では、個人データや厳しく規制された営業秘密ファイルに保持ラベルを使用します。
-   Microsoft 365 の機密情報の種類を Microsoft 365 内と Cloud App Security で使用して、別の SaaS アプリにある個人データを監視できます。
-   厳しく規制された営業秘密ファイル、Exchange Online 電子メール、他の SaaS サービスのファイル、オンプレミスのデータセンターのファイル、他のクラウド プロバイダーのファイルには、機密ラベルを使用します。


## <a name="use-retention-labels-and-sensitive-information-types-across-microsoft-365-for-information-protection"></a>情報を保護するために Microsoft 365 全体で保持ラベルと機密情報の種類を使用する

次の図は、ラベル ポリシー、データ損失防止ポリシー、Cloud App Security ポリシーで保持ラベルと機密情報の種類を使用する方法を示しています。

![Office のラベルと機密情報の種類](../media/Apply-labels-to-personal-data-in-Office-365-image2.png)

次の表では、図での例と同じものを見やすいように記載しています。

<table>
<thead>
<tr class="header">
<th align="left"><strong>分類の要素</strong></th>
<th align="left"><strong>ラベル ポリシー — 2 つの例</strong></th>
<th align="left"><strong>データ損失防止ポリシー — 2 つの例</strong></th>
<th align="left"><strong>すべての SaaS アプリの Cloud App Security ポリシー — 1 つの例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">保持ラベル。 例: 個人、公開、顧客のデータ、人事データ、社外秘、非常に機密性の高い社外秘</td>
<td align="left"><p>Auto apply this label . . .</p>
<p>顧客データ</p>
<p>. . . to documents that match these sensitive information types . . .</p>
<p>&lt;機密情報の種類の例の一覧&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;保護の定義&gt;</p>
<p>. . . to documents with this label . . .</p>
<p>顧客データ</p></td>
<td align="left"><p>Alert when files with these attributes . . .</p>
<p>1 つまたは複数の属性を選択します: 定義済みの PII 属性、Microsoft 365 の機密情報の種類、秘密度ラベル (AIP)、カスタム式</p>
<p>。 。 。 組織外で共有された際に警告します</p><p>注: 現在、保持ラベルは Cloud App Security ではサポートされていません。</td>
</tr>
<tr class="even">
<td align="left">Sensitive information types. Examples: Belgium National Number, Credit Card Number, Croatia Identity Cart Number, Finland National ID</td>
<td align="left"><p>Publish these labels for users to manually apply . . .</p>
<p>&lt;ラベルの選択&gt;</p>
<p>. . . to these locations . . .</p>
<p>&lt;すべての場所、あるいは特定の場所を選択&gt;</p></td>
<td align="left"><p>Apply this protection . . .</p>
<p>&lt;保護の定義&gt;</p>
<p>. . . to documents that match these sensitive information types&gt;</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="prioritize-auto-apply-label-policies"></a>自動適用ラベル ポリシーの優先順位付け

For personal data that is subject to GDPR, Microsoft recommends auto-applying labels by using the sensitive information types you curated for your environment. It is important that auto-apply label policies are well designed and tested to ensure the intended behavior occurs.

The order that auto-apply policies are created and whether users are also applying these labels affect the result. So, it's important to carefully plan the roll-out. Here's what you need to know.

### <a name="one-label-at-a-time"></a>一度に 1 つのラベルを適用する

ドキュメントに割り当てることができるラベルの数は 1 つのみです。

### <a name="older-auto-apply-policies-win"></a>優先されるのは古いポリシー

If there are multiple rules that assign an auto-apply label and content meets the conditions of multiple rules, the label for the oldest rule is assigned. For this reason, it's important to plan the label policies carefully before configuring them. If an organization requires a change to the priority of the label policies, they'll need to delete and recreate them.

### <a name="manual-user-applied-labels-trump-auto-applied-labels"></a>自動適用ラベルよりもユーザーが手動で適用したラベルが優先される

Manual user applied labels trump auto-applied labels. Auto-apply policies can't replace a label that is already applied by a user. Users can replace labels that are auto-applied.

### <a name="auto-assigned-labels-can-be-updated"></a>自動的に割り当てられたラベルは更新可能

自動的に割り当てられたラベルは、新しいラベル ポリシーにより、または既存のポリシーを更新することによって最新の状態にすることができます。

ラベルを実装する際に重要な点:

- 自動適用ポリシーが作成される順序の優先順位付けを行います。

- Allowing enough time for labels to be automatically applied before rolling these out for users to manually apply. It can take up to seven days for the labels to be applied to all content that matches the conditions.

### <a name="example-priority-for-creating-the-auto-apply-policies"></a>自動適用ポリシー作成の優先順位の例

<table>
<thead>
<tr class="header">
<th align="left"><strong>ラベル</strong></th>
<th align="left"><strong>自動適用ポリシーの作成順序の優先順位</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">人事 — 従業員データ</td>
<td align="left">1</td>
</tr>
<tr class="even">
<td align="left">顧客データ</td>
<td align="left">2</td>
</tr>
<tr class="odd">
<td align="left">非常に機密性の高い社外秘</td>
<td align="left">3</td>
</tr>
<tr class="even">
<td align="left">人事 — 給与データ</td>
<td align="left">4</td>
</tr>
<tr class="odd">
<td align="left">社外秘</td>
<td align="left">5</td>
</tr>
<tr class="even">
<td align="left">公開</td>
<td align="left">6</td>
</tr>
<tr class="odd">
<td align="left">個人</td>
<td align="left">自動適用ポリシーなし</td>
</tr>
</tbody>
</table>

## <a name="create-labels-and-auto-apply-label-policies"></a>ラベルおよび自動適用ラベル ポリシーの作成

セキュリティ センターまたはコンプライアンス センターで、ラベルおよびポリシーを作成します。

<table>
<thead>
<tr class="header">
<th align="left"><strong>手順</strong></th>
<th align="left"><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンプライアンス チームのメンバーにアクセス許可を与えます。</p></td>
<td align="left"><p>Members of your compliance team who will create labels need permissions to use the security center and/or the compliance center. Go to Permissions in the security center or the compliance center and modify the members of the Compliance Administrator group.</p>
<p>「<a href="https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center">ユーザーにセキュリティ センターやコンプライアンス センターへのアクセス権を付与する</a>」を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>保持ラベルを作成します。</p></td>
<td align="left">セキュリティ センターまたはコンプライアンス センターの [分類] に移動し、[保持ラベル] を選択して、使用している環境のラベルを作成します。</td>
</tr>
<tr class="odd">
<td align="left"><p>ラベルの自動適用ポリシーを作成します。</p></td>
<td align="left">Go to Classification in security center or the compliance center, choose Label policies, and create the policies for auto-applying labels. Be sure to create these policies in the prioritized order.</td>
</tr>
</tbody>
</table>

次の図は、顧客データ ラベル用の自動適用ラベルを作成する方法を示しています。

![顧客データのラベルの作成と適用](../media/Apply-labels-to-personal-data-in-Office-365-image3.png)

この図について:

- "顧客データ" ラベルが作成されます。

- GDPR の必要な機密情報の種類 (ベルギーの国民番号、クレジット カード番号、クロアチアの身分証明書番号、フィンランドの国民 ID) が記載されています。

- 自動適用ポリシーを作成すると、ポリシーに追加する機密情報の種類のいずれかを含むファイルに、"顧客データ" ラベルが割り当てられます。
