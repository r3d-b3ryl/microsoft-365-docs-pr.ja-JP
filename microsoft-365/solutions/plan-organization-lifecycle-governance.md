---
title: Microsoft 365 グループおよび Microsoft Teams の組織およびライフサイクルのガバナンスを計画する
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Microsoft 365 のコラボレーションツールに関するリーンライフサイクルガバナンスオプション
ms.openlocfilehash: 2a2f14bf439ec69e4609d22783fb14d1d5cb8e70
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662713"
---
# <a name="plan-organization-and-lifecycle-governance-for-microsoft-365-groups-and-microsoft-teams"></a>Microsoft 365 グループおよび Microsoft Teams の組織およびライフサイクルのガバナンスを計画する

Microsoft 365 グループには、組織で必要とされるガバナンス機能を実装するための豊富なツールセットがあります。 

次のセクションでは、機能について説明し、ベストプラクティスを推奨し、ガバナンスの要件を決定するための適切な質問とそれらを満たす方法についてのガイダンスを提供します。

## <a name="control-who-can-create-microsoft-365-groups"></a>Microsoft 365 グループを作成できるユーザーを制御する

エンドユーザーは、Outlook、SharePoint、Teams、その他の環境を含む複数のエンドポイントからグループを作成できます。

![画像の説明](../media/04.png)

グループの所有者を強化し、ユーザーが作業をより簡単に実行できるようにするには、セルフサービスを強くお勧めします。 グループとチームの作成を制限すると、多くの Microsoft 365 サービスでは、サービスを機能させるためにグループを作成する必要があるため、ユーザーの生産性が低下する可能性があります。

グループを作成するには、次のガバナンスオプションを考慮します。

- グループの拡散を制限するには、グループの [有効期限ポリシー](microsoft-365-groups-expiration-policy.md) を使用して、使用されていないグループを自動的に削除します。
- グループの作成をセキュリティグループのメンバーに制限します。たとえば、すべてのフルタイムの従業員を含む [動的メンバーシップを使用](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule) します。
- グループの作成をセキュリティグループに制限し、ユーザーがセキュリティグループのメンバーになるためには、組織のグループ使用ポリシーのトレーニングを完了する必要があります。

グループを作成できるユーザーを制限する場合は、これを構成する方法については、「 [Microsoft 365 グループを作成できるユーザーを管理](manage-creation-of-groups.md) する」を参照してください。

## <a name="group-delete-restore-and-archiving"></a>グループの削除、復元、およびアーカイブ

Microsoft 365 グループが削除されると、既定では30日間保持されます。 グループを引き続き復元できるため、この 30 日の期間は "論理的な削除" と呼ばれます。 30 日後、グループおよび関連付けられているコンテンツは完全に削除され、復元することはできません。

保持ポリシーが設定されている場合、チャット、ファイル、またはメールを保持するには、グループを削除した後に、それらのアイテムを保持します。 詳細については、「 [アイテム保持ポリシーについ](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) て」を参照してください。

グループを削除するが、グループに接続された1つ以上のサービスのコンテンツを保持する場合は、「 [Archive groups, teams, And Yammer](end-life-cycle-groups-teams-sites-yammer.md) for information」を参照してください。

## <a name="group-naming-policy"></a>グループの名前付けポリシー

グループの名前付けポリシーは、次の2つの方法でグループを管理するのに役立ちます。

- プレフィックス/サフィックスの名前付けポリシーを使用すると、グループ名とそれに関連付けられた電子メールアドレスの先頭または末尾に、固定文字列または Azure AD 属性を強制することができます。 これにより、たとえば、部署名や地域をグループ名に含めることができます。
- ブロックされた単語のポリシーを使用すると、役職者の名前など、特定の単語がグループ名で使用されないようにすることができます。

グループに接続されたサービスからグループを作成すると、名前付けポリシーが適用されます。

グループの名前付けポリシーの使用を決定した場合は、「 [Microsoft 365 groups ネーミング policy](groups-naming-policy.md)」を参照してください。

## <a name="group-expiration-policy"></a>グループの有効期限ポリシー

有効期限を指定して、その期間の終わりに到達し、更新されていないすべてのグループを削除することができます。 有効期限は、グループが作成された時点、または最後に更新された日付から始まります。

グループの有効期限を設定すると、次のようになります。
- グループの所有者は、有効期限が近づくにつれてグループを更新するように通知されます。
- アクティブなグループは自動的に更新されます。
- 更新されていないグループは削除されます。
- 削除されたグループは、グループの所有者または管理者が30日以内に復元できます。

有効期限ポリシーは、使用されなくなったグループが削除されるようにすることで、グループの拡散を制限するのに適した方法です。 グループの有効期限ポリシーを作成する場合は、「 [Microsoft 365 グループの有効期限](microsoft-365-groups-expiration-policy.md)ポリシー」を参照してください。
