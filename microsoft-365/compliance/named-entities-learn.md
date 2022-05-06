---
title: 名前付きエンティティの詳細
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
description: 名前付きエンティティを使用して、データ損失防止ポリシーを使用して、人、物理的な住所、医療用語の名前を含む機密アイテムを検出する方法について説明します
ms.openlocfilehash: 6c20932216953d64abe4515b529bba66b2561647
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64973203"
---
# <a name="learn-about-named-entities"></a>名前付きエンティティの詳細

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

*名前付きエンティティ* は [機密情報の種類](sensitive-information-type-learn-about.md) (SIT) です。 これらは複雑な辞書とパターンベースの分類子であり、ユーザー名、物理アドレス、医療条件を検出するために使用できます。 これらの情報は、 **Microsoft Purview コンプライアンス ポータル>データ分類>機密情報の種類** で確認できます。 SIT を使用できる場所の一部を次に示します。


- [Microsoft Purview データ損失防止ポリシー (DLP)](dlp-learn-about-dlp.md) 
- [秘密度ラベル](sensitivity-labels.md)
- [インサイダー リスク管理](insider-risk-management-solution-overview.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Purview Information Protection](apply-sensitivity-label-automatically.md)
- [データ ライフサイクル管理](information-governance.md)
- [レコード管理](records-management.md)
- [Microsoft Purview 電子情報開示](ediscovery.md)
- [Microsoft Priva](/privacy/priva/priva-overview.md)
- [厳密なデータ一致の機密情報の種類](sit-learn-about-exact-data-match-based-sits.md)

DLP は、組織のニーズに合わせてカスタマイズできる事前構成済みの DLP ポリシーである *、拡張ポリシー テンプレート* で名前付きエンティティを特別に使用します。 [また、空のテンプレート](create-a-dlp-policy-from-a-template.md)から独自の [DLP ポリシーを作成](create-test-tune-dlp-policy.md)し、名前付きエンティティ SIT を条件として使用することもできます。

<!-- There are many other SITs that detect strings like social security, credit card, or bank account numbers to identify sensitive items. For more information, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md).-->



## <a name="examples-of-named-entity-sits"></a>名前付きエンティティ SIT の例

名前付きエンティティ SIT には、*バンドル* と *バンドル解除* の 2 種類があります

バンドルされた名前付きエンティティ SIT は、考えられるすべての一致を検出します。 機密アイテムを検出するための DLP ポリシーの広範な条件として使用します。

バンドルされていない名前付きエンティティ SIT は、単一の国のように、より狭いフォーカスを持っています。 検出範囲が狭い DLP ポリシーが必要な場合に使用します。
 
名前付きエンティティ SIT の例をいくつか次に示します。 すべての情報は、 [機密情報の種類のエンティティ定義で確認](sensitive-information-type-entity-definitions.md)できます。

|名前付きエンティティ |説明  |バンドル/バンドル解除  |
|---------|---------|---------|
|すべてのフル ネーム    |は、完全な名前の可能なすべての一致を検出します         |   バンドル      |
|すべての物理アドレス    |は、物理アドレスのすべての一致を検出します     | バンドル |
|すべての医療条件    |は、医療契約条件のすべての一致を検出します |バンドル |
|オーストラリアの物理アドレス |  オーストラリアからの物理アドレスに関連するパターンを検出します。 すべての物理アドレス SIT に含まれます。 |unbundled |
|血液検査の使用条件     |"hCG" などの血液検査に関連する用語を検出します。 英語の用語のみ。 すべての医療契約条件に含まれる SIT      |unbundled |
|ブランドの薬の名前     |"Tylenol" などのブランド薬の名前を検出します。 英語の用語のみ。 すべての医療契約条件に含まれます。         |unbundled |

## <a name="examples-of-enhanced-dlp-policies"></a>拡張 DLP ポリシーの例

名前付きエンティティ SIT を使用する拡張 DLP ポリシーの例をいくつか次に示します。 そのうちの 10 個はすべて **、Microsoft Purview コンプライアンス ポータルのデータ損失防止>ポリシーの作成>にあります**。 拡張テンプレートは、DLP と自動ラベル付けで使用できます。

|ポリシー カテゴリ  |テンプレート  |説明  |
|---------|---------|---------|
|財務的|米国グラムリーチ-ブリリー法 (GLBA) の強化         |グラム リーチ ブライリー法 (GLBA) の対象となる情報 (社会保障番号やクレジット カード番号など) の存在を検出する際に役立ちます。 この強化されたテンプレートは、ユーザーの完全な名前である米国/英国も検出することで元のテンプレートを拡張します。 パスポート番号、米国の運転免許証番号、および米国の物理アドレス。         |
| 医療と健康   |オーストラリア健康記録法 (HRIP 法) の強化         |オーストラリアで一般的に保健医療記録情報プライバシー (HRIP) 法の対象になると見なされる情報 (医療口座番号や納税者番号など) の存在を検出する際に役立ちます。 この強化されたテンプレートは、人の完全な名前、医療条件、オーストラリアの物理的な住所も検出することで、元の住所を拡張します。         |
|プライバシー   |一般的なデータ保護規則 (GDPR) の強化         | 欧州連合 (EU) 内の個人に対する個人情報の存在を検出し、GDPR プライバシーの義務を満たすのに役立ちます。 この強化されたテンプレートは、EU 内の国のユーザーの完全な名前と物理アドレスを検出します。        |


## <a name="next-steps"></a>次の手順

- [データ損失防止ポリシーで名前付きエンティティを使用する](named-entities-use.md)


## <a name="for-further-information"></a>詳細については、次の情報を参照してください。

- [機密情報の種類のエンティティ定義](sensitive-information-type-entity-definitions.md)
- [機密情報の種類について学習する](sensitive-information-type-learn-about.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
- [PowerShell でカスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [データ損失防止ポリシー (DLP)](data-loss-prevention-policies.md) 
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md)
- [通信コンプライアンス](communication-compliance.md)
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md) 
