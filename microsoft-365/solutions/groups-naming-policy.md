---
title: Microsoft 365 グループの名前付けポリシー
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
recommendations: false
description: Microsoft 365 グループの名前付けポリシーを作成する方法について説明します。
ms.openlocfilehash: acc521dd5be1dcf630b4801eeb914c45e765e00f
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064513"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 グループの名前付けポリシー

グループの名前付けポリシーを使用して、組織内のユーザーによって作成されたグループに一貫した名前付け戦略を適用できます。 名前付けポリシーにより、お客様とユーザーがグループの機能、メンバーシップ、地域、グループの作成者を特定できるようになります。 名前付けポリシーは、アドレス帳のグループの分類にも役立ちます。 ポリシーを使用して、特定の単語をグループの名前やエイリアスで使われないようにブロックすることができます。

名前付けポリシーは、すべてのグループ ワークロード (Outlook、Microsoft Teams、SharePoint、Planner、Yammerなど) に作成されるグループに適用されます。 グループ名とグループのエイリアスの両方に適用されます。 また、ユーザーがグループを作成するときや、既存のグループのグループ名、エイリアス、説明、またはアバターが編集されたときにも適用されます。

> [!TIP]
> Microsoft 365 グループの名前付けポリシーは、Microsoft 365 グループにのみ適用されます。 Exchange Onlineで作成された配布グループには適用されません。 配布グループの名前付けポリシーを作成するには、「配布グループの [名前付けポリシーを作成する」を](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)参照してください。

グループの名前付けポリシーは、次の機能で構成されています。

- **プレフィックスとサフィックスの名前付けポリシー**: プレフィックスまたはサフィックスを使用して、グループの名前付け規則を定義できます (例: "USMy\_ GroupEngineering\_")。 プレフィックス/サフィックスは、固定文字列、またはグループを作成しているユーザーに基づいて置換される [Department] などのユーザー属性のいずれかにすることができます。

- **カスタムブロックされた単語**: ユーザーが作成したグループでブロックされる、組織に固有のブロックされた単語のセットをアップロードできます。 (例: "CEO, Payroll, HR")。

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft 365 グループに Azure AD 名前付けポリシーを使用するには、1 つ以上の Microsoft 365 グループのメンバーである一意のユーザー (ゲストを含む) ごとに Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU ライセンスを所有している必要があります。

これは、グループの名前付けポリシーを作成する管理者にも必要です。

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix名前付けポリシー

プレフィックスとサフィックスは、固定文字列またはユーザー属性のいずれかにすることができます。

### <a name="fixed-strings"></a>固定文字列

GAL 内のグループとグループ ワークロードの左ナビゲーションでグループを区別するのに役立つ短い文字列を使用できます。 一般的なプレフィックスサフィックスの一部は、'GrpName\_' 、'Name'、'\#\_Name' などのキーワードです。

### <a name="attributes"></a>属性

属性を使って、[Department] のようにグループを作成したユーザー、および [Country] のように作成された場所を識別するのに役立てることができます。

例:

- Policy = "GRP [GroupName] [Department]"
- User's department = Engineering
- Created group name = "GRP My Group Engineering"

サポートされる Azure Active Directory (Azure AD) 属性は、[Department]、[Company]、[Office]、 [StateOrProvince]、[CountryOrRegion]、[Title] です。

- サポートされていないユーザー属性は、固定文字列 ([postalCode] など) と見なされます。

- 拡張属性とカスタム属性はサポートされません。

組織のすべてのユーザーに対して、値が設定された属性を使用することをお勧めします。長い値が設定された属性は使用しないでください。

### <a name="things-to-look-out-for"></a>探すべき点

- ポリシーを作成するときは、プレフィックスとサフィックスの合計文字数は 53 文字に制限されます。

- プレフィックスとサフィックスには、グループ名とグループのエイリアスでサポートされている特殊文字を含めることができます。 プレフィックスとサフィックスに、グループエイリアスで許可されていない特殊文字が含まれている場合、それらはグループ名にのみ適用されます。 そのため、この場合は、グループ名に適用されているプレフィックスとサフィックスは、グループのエイリアスに適用されているものとは異なります。

  > [!NOTE]
  > ピリオド (.) またはハイフン (-) は、名前の先頭または末尾を除き、グループ名内の任意の場所で許可されます。 アンダースコア (_) は、名前の先頭または末尾を含め、グループ名内の任意の場所で許可されます。

- Yammer Office 365接続されたグループを使用している場合は、名前付けポリシーで次の文字を使用しないでください。 @、 , \#, \[, \], \<, and \>. これらの文字がネーミング ポリシーに含まれている場合、通常の Yammer ユーザーはグループを作成できません。

> [!Tip]
> - 短い文字列をサフィックスとして使用します。
> - 値が指定された属性を使用します。
> - あまりクリエイティブにしないでください。名前の合計の長さは最大 264 文字です。
> - 使用制限する組織固有の禁止単語をアップロードします。

## <a name="custom-blocked-words"></a>カスタム ブロックされた単語

ブロックされた単語のリストをコンマ区切りで入力できます。これは、グループの名前とエイリアスでブロックされます。

サブ文字列検索は実行されません。具体的には、エラーをトリガーするには、ユーザーが入力した名前とカスタムブロックされた単語の間で完全に一致する必要があります。

**次の点に目を向ける必要があります**。

- ブロックする単語は、大文字と小文字を区別します。

- ユーザーがブロックする単語を入力すると、グループ クライアントによって、ブロックされた単語を含むエラー メッセージが表示されます。

- ブロックする単語で使用する文字に制限はありません。

- ブロックされた単語として設定できる単語は 5,000 個に制限されています。

## <a name="admin-override"></a>管理者による上書き

一部の管理者は、これらのブロックされた単語と目的の名前付け規則を使用してグループを作成できるように、すべてのグループのワークロードとエンドポイントにわたって、これらのポリシーから除外されます。 グループの名前付けポリシーの適用から除外される管理者の役割リストは次のとおりです。

- 全体管理者

- パートナー レベル 1 のサポート

- パートナー レベル 2 のサポート

- ユーザー アカウント管理者

## <a name="how-to-set-up-the-naming-policy"></a>名前付けポリシーを設定する方法

名前付けポリシーを設定するには:

1. [Azure Active Directory](https://aad.portal.azure.com)の [**管理**] で、[**グループ**] をクリックします。
2. **[設定**] の [**名前付けポリシー**] をクリックします。
3. [ **グループの名前付けポリシー** ] タブを選択します。
4. **[現在のポリシー**] で、プレフィックスまたはサフィックスまたはその両方を必要とするかどうかを選択し、適切なチェック ボックスをオンにします。
5. 各行の **[属性]** と **[文字列]** を選択し、属性または文字列を指定します。
6. 必要なプレフィックスとサフィックスを追加したら、[保存] をクリック **します**。

![Azure Active Directoryのグループの名前付けポリシー設定のスクリーンショット。](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>関連項目

[おすすめのコラボレーション ガバナンス計画](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[グループ設定を構成するための Azure Active Directory コマンドレット](/azure/active-directory/enterprise-users/groups-settings-cmdlets)