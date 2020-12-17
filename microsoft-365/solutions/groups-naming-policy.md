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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Microsoft 365 グループの名前付けポリシーを作成する方法について説明します。
ms.openlocfilehash: 9bc0a4c7e1ae6ad532c97b442a2bc50880a942fc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698677"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 グループの名前付けポリシー

グループの名前付けポリシーを使用して、組織内のユーザーによって作成されたグループに対して一貫した名前付け戦略を適用できます。 名前付けポリシーにより、お客様とユーザーがグループの機能、メンバーシップ、地域、グループの作成者を特定できるようになります。 名前付けポリシーは、アドレス帳のグループの分類にも役立ちます。 ポリシーを使用して、特定の単語をグループの名前やエイリアスで使われないようにブロックすることができます。

名前付けポリシーは、すべてのグループワークロード (Outlook、Microsoft Teams、SharePoint、Planner、Yammerなど) 全体で作成されるグループに適用されます。 グループ名とグループのエイリアスの両方に適用されます。 名前付けポリシーは、ユーザーによるグループの作成時、または既存のグループのグループ名やエイリアスの編集時に適用されます。

> [!TIP]
> Microsoft 365 グループの名前付けポリシーは、Microsoft 365 グループにのみ適用されます。 Exchange Online で作成された配布グループには適用されません。 配布グループの名前付けポリシーを作成するには、「配布グループの名前付け [ポリシーを作成する」を参照してください](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)。

グループの名前付けポリシーは、次の機能で構成されています。

- **プレフィックスサフィックスの名前付** けポリシー : プレフィックスまたはサフィックスを使用して、グループの名前付け規則を定義できます (例: "US \_ My Group \_ Engineering")。 プレフィックス/サフィックスは、固定文字列、またはグループを作成しているユーザーに基づいて置換される [Department] などのユーザー属性のいずれかにすることができます。

- **カスタムのブロックする単語**: ユーザーが作成したグループでブロックされる、組織に固有のブロックする単語のセットをアップロードできます。 (例: "CEO, Payroll, HR")。

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft 365 グループの Azure AD 名前付けポリシーを使用するには、1 つ以上の Microsoft 365 グループのメンバーである一意のユーザー (ゲストを含む) ごとに Azure Active Directory Premium P1 ライセンスまたは Azure AD Basic EDU ライセンスを所有している必要がありますが、必ずしも割り当てない必要があります。

これは、グループの名前付けポリシーを作成する管理者にも必要です。

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix名前付けポリシー

プレフィックスとサフィックスは、固定文字列またはユーザー属性のいずれかにすることができます。

### <a name="fixed-strings"></a>固定文字列

GAL 内のグループを区別し、グループ ワークロードの左側のナビゲーションに役立つ短い文字列を使用できます。 一般的なプレフィックスサフィックスの一部は、'Grp \_ Name' 、 ' \# Name'、 ' \_ Name' のようなキーワードです。

### <a name="attributes"></a>属性

属性を使って、[Department] のようにグループを作成したユーザー、および [Country] のように作成された場所を識別するのに役立てることができます。

例:

- Policy = "GRP [GroupName] [Department]"
- User's department = Engineering
- Created group name = "GRP My Group Engineering"

サポートされている Azure Active Directory (Azure AD) の属性は、[Department]、[Company]、[Office]、[StateOrProvince]、[CountryOrRegion]、および [Title] です。

- サポートされていないユーザー属性は固定文字列と見なされます (例: [postalCode])。

- 拡張属性とカスタム属性はサポートされません。

組織のすべてのユーザーに対して、値が設定された属性を使用することをお勧めします。長い値が設定された属性は使用しないでください。

### <a name="things-to-look-out-for"></a>お気に入り情報

- ポリシーを作成するときは、プレフィックスとサフィックスの合計文字数は 53 文字に制限されます。

- プレフィックスとサフィックスには、グループ名とグループのエイリアスでサポートされている特殊文字を含めることができます。 プレフィックスとサフィックスにグループ エイリアスで使用できない特殊文字が含まれている場合は、グループ名にのみ適用されます。 そのため、この場合は、グループ名に適用されているプレフィックスとサフィックスは、グループのエイリアスに適用されているものとは異なります。

  > [!NOTE]
  > ピリオド (.) またはハイフン (-) は、名前の先頭または末尾を除き、グループ名の任意の場所で使用できます。 グループ名の先頭または末尾を含め、グループ名の任意の場所でアンダースコア (_) を使用できます。

- 365 の接続されたYammer Officeを使用している場合は、名前付けポリシーで次の文字を使用しないようにしてください。 @、 \# \[ , \] \<, and \> . これらの文字が名前付けポリシーに含Yammerユーザーはグループを作成できません。

> [!Tip]
> - 短い文字列をサフィックスとして使用します。
> - 値が指定された属性を使用します。
> - クリエイティブすぎず、名前の長さの合計は最大 264 文字です。
> - 使用制限する組織固有の禁止単語をアップロードします。

## <a name="custom-blocked-words"></a>カスタムのブロックする単語

ブロックされた単語のリストをコンマ区切りで入力できます。これは、グループの名前とエイリアスでブロックされます。

サブ文字列検索は実行されます。具体的には、エラーをトリガーするには、ユーザーが入力した名前とカスタムのブロックする単語の完全一致が必要です。

**次の情報に注意してください**。

- ブロックする単語は、大文字と小文字を区別します。

- ユーザーがブロックする単語を入力すると、グループ クライアントによって、ブロックされた単語を含むエラー メッセージが表示されます。

- ブロックする単語で使用する文字に制限はありません。

- ブロックする単語として設定できる単語は 5,000 語に制限されています。

## <a name="admin-override"></a>管理者による上書き

一部の管理者は、これらのブロックする単語と目的の名前付け規則を持つグループを作成できるよう、すべてのグループ ワークロードとエンドポイントで、これらのポリシーから除外されます。 グループの名前付けポリシーの適用から除外される管理者の役割リストは次のとおりです。

- 全体管理者

- パートナー レベル 1 のサポート

- パートナー レベル 2 のサポート

- ユーザー アカウント管理者

## <a name="how-to-set-up-the-naming-policy"></a>名前付けポリシーを設定する方法

名前付けポリシーを設定するには:

1. [Azure Active Directory の [管理] で](https://aad.portal.azure.com)、[**グループ**] を **クリックします**。
2. [設定 **] で**、[名前付けポリシー] **をクリックします**。
3. [グループの **名前付けポリシー] タブを選択** します。
4. [ **現在のポリシー**] で、プレフィックスまたはサフィックスの両方を必要とするか選択し、適切なチェック ボックスをオンにします。
5. 行ごとに **[属性]** **と [文字列** ] から選択し、属性または文字列を指定します。
6. 必要なプレフィックスとサフィックスを追加した後、[保存] をクリック **します**。

![Azure Active Directory のグループ名前付けポリシー設定のスクリーンショット](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>関連項目

[グループコラボレーション ガバナンスの計画のステップ バイ ステップ](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[コラボレーション ガバナンス計画を作成する](collaboration-governance-first.md)

[グループ設定を構成するための Azure Active Directory コマンドレット](https://go.microsoft.com/fwlink/?linkid=868341)
