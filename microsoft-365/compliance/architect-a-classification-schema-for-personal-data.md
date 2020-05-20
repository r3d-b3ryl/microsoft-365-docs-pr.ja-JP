---
title: 個人データの分類スキーマを設計する
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: overview
ms.collection:
- Strat_O365_Enterprise
- Ent_O365
- GDPR
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
description: 組織が一般データ保護規則 (GDPR) 計画の一環としてラベルを実装するかどうかを決定します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 17484e56206ba8f32db3c779623f2f8d7ed57496
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035169"
---
# <a name="architect-a-classification-schema-for-personal-data"></a>個人データの分類スキーマを設計する

このシリーズの前の記事では、GDPR の対象となる個人データの識別に機密情報の種類を使用することに焦点を置いていました。機密情報の種類は分類の 1 形式であり、これが、必要な分類すべてである場合もあります。ただし、多数の組織ではラベルを使用した幅広いデータ ガバナンス戦略を取り入れています。このトピックを使用して、GDPR 計画の一環としてラベルを実装するかどうかを決定してください。実装する場合、このトピックは多少のガイダンスと例を提供します。

注: 組織の分類スキーマを定義してポリシー、ラベル、条件を構成するには、慎重な計画と準備が必要です。これは IT 部門が主導するプロセスではないことを認識することが必要です。法務およびコンプライアンス チームと連携を図り、組織のデータ用に適切な分類およびラベル付けスキーマを作成します。

## <a name="decide-if-youre-using-labels-in-addition-to-sensitive-data-types"></a>機密データの種類に加えてラベルを使用するかどうかを決定する

Microsoft 365 では、2 つある方法のいずれかを使用して個人情報を分類できます。いずれの方法も GDPR 保護に使用できます。機密情報の種類だけを使用して分類することを決定した場合、このトピックの残りの部分はスキップできます。

次のいずれかのオプションを選んでください

### <a name="option-1-use-only-microsoft-365-sensitive-information-types"></a>オプション 1: Microsoft 365 の機密情報の種類だけを使用する

- 機密情報の種類は GDPR やその他の規制の対象となる個人データの識別と保護に適しています。

- これらは、組織でまだラベルを使用する広範なデータ ガバナンス計画がない場合、またはその実装が準備段階の場合に簡単に使用できます。

- これらは DLP ルールと連携します (保持ラベルも同様です)。

- 機密情報の種類は Cloud App Security とも連携するため、他の SaaS アプリでも機密データを検出することができます。

### <a name="option-2-use-sensitive-information-types--retention-labels"></a>オプション 2: 機密情報の種類と保持ラベルを使用する

- GDPR の対象となる個人データにラベルを自動的に適用するには、機密情報の種類が必要になるため、必須になります。

- 保持ラベルを使用すると、GDPR の対象となる個人データを、組織の広範なデータ ガバナンス計画に含めることができます。

## <a name="develop-a-label-schema-that-includes-personal-data"></a>個人データを含むラベル スキーマを開発する

技術的な機能を使用してラベルと保護を適用する前に、まずは組織全体で連携して分類スキーマを定義します。組織内に既に分類スキーマがあるかもしれません。その場合は、個人データをより簡単に追加できます。このトピックでは、分類スキーマの例を 1 つ紹介します。必要な場合は、この例を出発点として使用できます。

### <a name="getting-started"></a>はじめに

まず、実装するラベルの数と名前を決定します。これは、どのテクノロジを使用するか、どのようにラベルを適用するかといった点を意識せずに決定してください。このスキーマは、オンプレミスやその他のクラウド サービスに存在するデータを含め、組織全体で汎用的に適用します。

### <a name="recommendations"></a>推奨事項 

ポリシー、ラベル、条件を設計および実装するには、次の推奨事項に従う必要があります。

- 既存の分類スキーマを使用する (ある場合) &ndash; 多くの組織では既に何らかの形でデータ分類を使用しています。既存のラベル スキーマを慎重に評価し、可能であればそのまま使用します。エンド ユーザーが認識できる使い慣れたラベルを使用すると、導入が円滑に進みます。

- 既定のポリシーとラベルから開始する &ndash; すべてのソリューションでは、事前定義されたポリシーとラベルが用意されています。それらを組織の法務および業務要件に照らして慎重に評価し、新しいものを作成するのではなく、それらを使用することを検討します。

- 少ない数から始める &ndash; 作成できるラベルの数に実質的な制限はありません。ただし、ラベルとサブ ラベルが多数ある場合、導入にマイナスの影響を与えます。多過ぎる選択肢は、選択肢がないのとほとんど変わりません。

- シナリオとユース ケースを使用する &ndash; 組織内の一般的なユース ケースを特定し、想定するラベルと分類の構成が実際に機能するかどうかを GDPR に由来するシナリオを使用して確認します。

- 新しいラベルに対する要求をすべて検証する &ndash; 各シナリオまたはユース ケースには新しいラベルが本当に必要か、既にあるラベルを使用できないかを確認します。ラベルの数を最小限に抑えることで、導入を促進できます。

- 主要部門でサブラベル使用する &ndash; 一部の部門では、特定のラベルを必要とする特殊なニーズがあります。これらのラベルを既存のラベルのサブ ラベルとして定義し、組織全体ではなく、ユーザー グループに割り当てる範囲限定ポリシーを使用することを検討します。

- 範囲限定ポリシーの使用を検討 &ndash; ポリシーの対象をユーザーのサブセットに限定すると、「ラベルのオーバーロード」を防止できます。範囲限定ポリシーを使用すると、ロールまたは部門固有の (サブ) ラベルを、その特定の部門に所属する従業員のみに割り当てられます。

- わかりやすいラベル名を使用する &ndash; ラベル名には専門用語、規格、略語を使用しないことが推奨されます。導入を促進するために、エンド ユーザーが認識できる名前を付けます。PII、PCI、HIPAA、LBI、MBI、HBI といったラベルではなく、「非業務」、「公開」、「一般」、「社外秘」、「極秘」などの名前の使用を検討してください。

### <a name="example-classification-schema"></a>分類スキーマの例

<table>
<thead>
<tr class="header">
<th align="left"><strong>ラベル名</strong></th>
<th align="left"><strong>説明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">個人</td>
<td align="left">ビジネス以外のデータ (個人使用のみ)。</td>
</tr>
<tr class="even">
<td align="left">公開</td>
<td align="left">公開使用向けに明確に準備、承認されているビジネス データ。</td>
</tr>
<tr class="odd">
<td align="left">顧客データ</td>
<td align="left">個人を特定できる情報を含むビジネス データ。例としては、クレジット カード番号、銀行口座番号、社会保障番号などがあります。</td>
</tr>
<tr class="even">
<td align="left">人事データ</td>
<td align="left">従業員番号や給与データなど、Contoso 社の社員の人事管理データ。</td>
</tr>
<tr class="odd">
<td align="left">社外秘</td>
<td align="left">権限のないユーザーと共有すると、ビジネスに損害を与える可能性のある機密性の高いビジネス データ。例としては、契約書、セキュリティ レポート、予測サマリー、販売取引データなどがあります。</td>
</tr>
<tr class="even">
<td align="left">非常に機密性の高い社外秘</td>
<td align="left">権限のないユーザーと共有すると、ビジネスに損害を与える可能性のある非常に機密性の高いビジネス データ。例としては、従業員情報と顧客情報、パスワード、ソース コード、発表前の財務レポートなどがあります。</td>
</tr>
</tbody>
</table>

## <a name="define-a-taxonomy-and-search-criteria-for-each-label"></a>各ラベルの分類と検索条件を定義する

組織の分類スキーマを作成したら、次にこのデータを検索するための分類と検索条件を作成します。個人データの場合、この作業は、機密情報の種類を特定し、組織の環境に合わせて機密情報の種類をカスタマイズまたは新規作成した際に既に完了しています。

次の表には、組織用のスキーマ、分類、および検索条件の例を示します。ラベルは機密性の低いものから高いものの順に並べられ、複数のラベル条件と一致するデータが適切なラベルに割り当てられるようにしています。

注: 構成の例は例示のためのものであり、展開のガイダンスや参照情報として意図されたものではありません。

ここで重要な点は、GDPR 準拠のための個人データの分類に費やす作業が、組織全体の目的と一致している必要があるということです。

### <a name="example-schema-taxonomy-and-search-criteria"></a>スキーマ、分類、および検索条件の例

<table>
<thead>
<tr class="header">
<th align="left"><strong>ラベル</strong></th>
<th align="left"><strong>分類</strong></th>
<th align="left"><strong>メソッド</strong></th>
<th align="left"><strong>検索構文</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">個人</td>
<td align="left">エンド ユーザーにより手動で「個人」とラベル付けされたドキュメント。</td>
<td align="left">手動</td>
<td align="left">エンド ユーザーにより手動で「個人」とラベル付けされたドキュメント。</td>
</tr>
<tr class="even">
<td align="left">パブリック</td>
<td align="left">「Approved for Public Release ##/####」という大文字/小文字を区別しない語句を含み、# が任意の数字を示すドキュメント。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Approved for Public Release*</p>
<p>RegEx — (?i)(\bApproved for Public Release \d{2}\/\d{4}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">顧客データ</td>
<td align="left">EU 市民データのための機密情報の種類。</td>
<td align="left">機密情報の種類</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">人事 — 従業員データ</td>
<td align="left">CONTOSO-9##### という形式で大文字/小文字を区別する従業員 ID を含み、# が任意の数字を示すドキュメント。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — CONTOSO-9*</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="odd">
<td align="left">人事 — 給与データ</td>
<td align="left">キーワード (大文字/小文字を区別しない)「Contoso 」と、キーワード (大文字/小文字を区別しない)「Salary」または「Compensation」を含むドキュメント</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso AND (Salary OR Compensation)</p>
<p>RegEx — (\bCONTOSO-9\d{5}\b)</p></td>
</tr>
<tr class="even">
<td align="left">Confidential</td>
<td align="left">語句 (大文字/小文字を区別しない)「Contoso Confidential」を含むドキュメント。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Confidential</p>
<p>RegEx — (?i)(\bContoso Confidential\b)</p></td>
</tr>
<tr class="odd">
<td align="left">非常に機密性の高い社外秘</td>
<td align="left">語句 (大文字/小文字を区別する)「Contoso Secret」または「Secret-C####」を含み、# が任意の数字を示すドキュメント。</td>
<td align="left"><p>KQL</p>
<p>RegEx</p></td>
<td align="left"><p>KQL — Contoso Secret OR Secret-C*</p>
<p>RegEx — (?i)(\bContoso Secret\b)|(\bSecret-C\d{4}\b)</p></td>
</tr>
</tbody>
</table>
