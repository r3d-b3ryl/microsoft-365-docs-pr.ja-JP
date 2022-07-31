---
title: ゲストを招待できるユーザーを制限する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 組織にゲストを招待できるユーザーを制限する方法について説明します。
ms.openlocfilehash: d8eb9452abb76916940d10fa042dae479358568a
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "66993689"
---
# <a name="limit-who-can-invite-guests"></a>ゲストを招待できるユーザーを制限する

組織内でゲストを招待できるユーザーを制限できます。 ゲスト アカウントは、チーム、SharePoint サイト、ファイル、フォルダーを組織外のユーザーと共有するために使用できます。

ビジネス プロセスでゲストと共有できるユーザーを制限する必要がある場合、またはユーザーがゲストと共有する前にトレーニングを完了する必要がある場合は、Azure Active Directory のゲスト招待者ロールを使用して共有できるユーザーを制限できます。

## <a name="create-a-security-group-for-people-allowed-to-invite-guests"></a>ゲストの招待を許可されたユーザーのセキュリティ グループを作成する

最初の手順は、ゲストの招待を許可されるユーザーのセキュリティ グループを作成することです。 Azure AD ロールを許可するようにこのグループを必ず構成し、ゲスト招待者ロールに割り当てます。

ゲスト招待者のセキュリティ グループを作成するには
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[Active Directory**] ページで[**グループ**]、[**新しいグループ**] の順に選択します。
1. **[グループの種類**] で [**セキュリティ**] を選択します。
1. **グループ名を入力します。** 
1. 必要に応じて、グループの説明を追加します。
1. **Azure AD ロールをグループに割り当てることができる場合は**、[**はい**] を選択します。
1. グループの所有者とメンバーを追加します。
1. [ **ロール]** で、[ **選択されているロールなし] を選択します**。
1. **ゲスト招待者** ロールを検索して選択し、[選択] を選択 **します**。
1. [ **作成**] を選択し、ロールを割り当てることができるグループが必要であることを確認します。 グループが作成され、メンバーを追加する準備が整いました。

## <a name="configure-external-collaboration-settings"></a>外部コラボレーション設定を構成する

セキュリティ グループを作成し、ゲストを招待できるようにするユーザーを追加したら、次の手順では、ゲスト招待者ロールを持つユーザーのみがゲストを招待できるように Azure AD 外部コラボレーション設定を構成します。

この設定に関係なく、グローバル管理者は常にゲストを招待できます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

ゲスト招待をゲスト招待者ロールに制限するように Azure AD を構成するには
1. [Azure Active Directory](https://aad.portal.azure.com/) で、[**外部 ID**] を選択します。
1. [ **外部コラボレーション設定]** を選択します。
1. [ **ゲストの招待設定]** で、[ **特定の管理者ロールに割り当てられたユーザーのみがゲストを招待できる**] を選択します。
1. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

[SharePoint と OneDrive で外部で共有する特定のセキュリティ グループ内のユーザーのみを許可する](/sharepoint/manage-security-groups)

[B2B の外部コラボレーションを有効にしてゲストを招待できるユーザーを管理する](/azure/active-directory/external-identities/delegate-invitations)