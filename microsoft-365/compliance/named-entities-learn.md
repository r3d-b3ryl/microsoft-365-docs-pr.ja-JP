---
title: 名前付きエンティティの詳細 (プレビュー)
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
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 名前付きエンティティが、データ損失防止ポリシーを使用して、人の名前、物理的な住所、医療用語を含む機密アイテムを検出する方法について説明します。
ms.openlocfilehash: 002905264d789e7ebe0b163a80fe033c028a6b4b
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110849"
---
# <a name="learn-about-named-entities-preview"></a>名前付きエンティティの詳細 (プレビュー)

> [!IMPORTANT]
> 名前付きエンティティ機能が展開され、テナントが利用可能なときにテナントに表示されます。 コンテンツ エクスプローラーとデータ損失防止 (DLP) ポリシー作成フローでそれらを確認します。 

*名前付きエンティティは* 機密情報 [の種類 (SIT)](sensitive-information-type-learn-about.md) です。 これらは複雑な辞書とパターン ベースの分類子であり、ユーザー名、物理アドレス、医療条件を検出するために使用できます。 これらの情報は、コンプライアンス センターの [データ> **機密情報>で確認できます**。 次に、SIT を使用できる場所の一覧を示します。

- [データ損失防止ポリシー (DLP)](dlp-learn-about-dlp.md) 
- [機密ラベル](sensitivity-labels.md)
- [インサイダー リスク管理](insider-risk-management-solution-overview.md)
- [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security)

DLP は、組織のニーズに合わせてカスタマイズできる事前構成された DLP ポリシーである拡張ポリシー テンプレートで、名前付きエンティティを特別に使用します。 また、空白[のテンプレートから独自の DLP](create-test-tune-dlp-policy.md) [](create-a-dlp-policy-from-a-template.md)ポリシーを作成し、名前付きエンティティ SIT を条件として使用することもできます。

<!-- There are many other SITs that detect strings like social security, credit card, or bank account numbers to identify sensitive items. For more information, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md).-->



## <a name="examples-of-named-entity-sits"></a>名前付きエンティティの ST の例

名前付きエンティティの STには、バンドルとバンドル解除の *2 つのフレーバーがあります。*

バンドルされた名前付きエンティティの ST は、すべての可能な一致を検出します。 機密性の高いアイテムを検出するために、DLP ポリシーの広範な条件として使用します。

Unbundled 名前付きエンティティの T は、単一の国のように、より狭いフォーカスを持っています。 検出範囲が狭い DLP ポリシーが必要な場合は、それらを使用します。
 
名前付きエンティティの SIT の例を次に示します。 これらの 52 件はすべて、コンプライアンス センターの [データ> **機密情報>で確認できます**。

|名前付きエンティティ |[説明]  |バンドル/バンドル解除  |
|---------|---------|---------|
|すべての完全な名前    |完全な名前のすべての可能な一致を検出します         |   バンドル      |
|すべての物理アドレス    |物理アドレスのすべての可能な一致を検出します     | バンドル |
|すべての医療条件    |は、医療条件のすべての可能な一致を検出します |バンドル |
|オーストラリアの物理アドレス |  オーストラリアの物理アドレスに関連するパターンを検出します。 |unbundled |
|血液検査の用語     |血液検査に関連する用語 ('hCG' など) を検出します。 英語の用語のみ。      |unbundled |
|ブランドの薬名     |'Tylenol' などのブランド薬の名前を検出します。 英語の用語のみ。         |unbundled |

## <a name="examples-of-enhanced-dlp-policies"></a>拡張 DLP ポリシーの例

名前付きエンティティの SIT を使用する拡張 DLP ポリシーの例を次に示します。 これらの 10 件はすべて、コンプライアンス センターの [データ損失防止>作成> **で確認できます**。 拡張テンプレートは、DLP および自動ラベル付けで使用できます。

|ポリシー カテゴリ  |テンプレート  |[説明]  |
|---------|---------|---------|
|財務的|米国の Gramm-Leach-Bliley 法 (GLBA) 拡張         |グラム リーチ ブライリー法 (GLBA) の対象となる情報 (社会保障番号やクレジット カード番号など) の存在を検出する際に役立ちます。 この拡張テンプレートは、ユーザーのフルネームである米国/英国も検出することで、元の名前を拡張します。 パスポート番号、米国の運転免許証番号、米国の物理アドレス。         |
| 医療と健康   |オーストラリアの健康記録法 (HRIP 法) 拡張         |オーストラリアで一般的に保健医療記録情報プライバシー (HRIP) 法の対象になると見なされる情報 (医療口座番号や納税者番号など) の存在を検出する際に役立ちます。 この拡張テンプレートは、ユーザーの完全な名前、医療条件、オーストラリアの物理的な住所も検出することで、元の情報を拡張します。         |
|プライバシー   |一般データ保護規則 (GDPR) 拡張         | EU (EU) 内の個人の個人情報の存在を検出し、GDPR のプライバシー義務を満たすのに役立ちます。 この拡張テンプレートは、EU 内の国のユーザーのフルネームと物理アドレスを検出します。        |


## <a name="next-steps"></a>次の手順

- [データ損失防止ポリシーで名前付きエンティティを使用する (プレビュー)](named-entities-use.md)


## <a name="for-further-information"></a>詳細については、次の情報を参照してください。
<!--- [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [機密情報の種類の詳細](sensitive-information-type-learn-about.md)
- [カスタムの機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)
- [PowerShell でカスタム機密情報の種類を作成する](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [データ損失防止ポリシー (DLP)](data-loss-prevention-policies.md) 
- [機密ラベル](sensitivity-labels.md)
- [保持ラベル](retention.md)
- [通信コンプライアンス](communication-compliance.md)
- [自動ラベル付けポリシー](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
- [テンプレートからの DLP ポリシーの作成](create-a-dlp-policy-from-a-template.md) 
