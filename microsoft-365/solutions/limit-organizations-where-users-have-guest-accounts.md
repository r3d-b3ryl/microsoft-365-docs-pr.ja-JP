---
title: ユーザーがゲスト アカウントを持つ組織を制限する
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
description: ユーザーがゲスト アカウントを持つ組織を指定する方法について説明します。
ms.openlocfilehash: 00db14560c491461435e41e30c106c2554d9ad61
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716036"
---
# <a name="limit-organizations-where-users-can-have-guest-accounts"></a>ユーザーがゲスト アカウントを持つ組織を制限する

既定では、他のMicrosoft 365およびAzure Active Directory組織は、ユーザーを招待して、組織にゲストとして参加させることができます。 これには、Microsoft Team のチームへの招待、サイトのSharePoint、個々のファイルとフォルダーの共有が含まれます。

ユーザーを特定の組織のゲストとしてのみ参加させる場合は、[B2B コラボレーション](/azure/active-directory/external-identities/what-is-b2b)のAzure Active Directoryテナント間アクセス設定でこれらの組織を指定できます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

## <a name="set-the-default-b2b-collaboration-settings-to-block-users-from-being-guests"></a>既定の B2B コラボレーション設定を設定して、ユーザーがゲストになるのをブロックする

ゲストとしての参加は既定で有効になっているため、ゲスト参加を特定の組織に制限するには、既定で送信 B2B コラボレーションをブロックする必要があります。

既定で送信 B2B コラボレーションをブロックするには
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. [ **既定の設定** ] タブを選択します。
1. [ **送信アクセス設定**] で、[ **送信の既定値の編集]** を選択します。
1. **[B2B コラボレーション**] タブと [**ユーザーとグループ**] タブを選択します。
1. **[アクセスの状態**] で、[**アクセスのブロック**] を選択します。
1. [ **外部アクセス** ] タブを選択します。
1. **[アクセスの状態**] で、[**アクセスのブロック**] を選択します。
1. **[保存]** を選択します。
1. **[既定の設定]** ブレードを閉じます。

## <a name="add-an-organization"></a>組織を追加する

次に、ユーザーがゲストとして共同作業できるようにする組織を、Azure ADテナント間アクセス リストに追加します。

組織を追加する方法
1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. **[組織設定]** を選択します。
1. **[組織の追加]** を選択します。
1. **[組織の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力します。
1. 検索結果から組織を選択して、**[追加]** を選択します。
1. 組織が **[組織設定]** リストに表示されます。

この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

## <a name="configure-the-organizations-outbound-setting-to-allow-all-users"></a>すべてのユーザーを許可するように組織の送信設定を構成する

組織を追加したら、B2B コラボレーション ユーザーをゲストとして追加できるように、組織の送信設定を更新する必要があります。 これは、ユーザーをゲストとして追加できるようにする組織ごとに行います。

ユーザーが組織内の B2B コラボレーション ゲストにアクセスできるようにするには
1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. 変更する組織の送信アクセス リンクを選択します。
1. **B2B コラボレーション** タブで、[設定の **カスタマイズ**] を選択します。
1. **[アクセスの状態**] で、[**アクセスを許可する**] を選択します。
1. [ **ターゲット]** で、すべてのユーザーを許可することを選択します。
1. **[保存]** を選択し、**[送信アクセス設定]** ブレードを閉じます。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B 直接接続のクロス テナント アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[組織が招待することのできるユーザーを制限する](limit-invitations-from-specific-organization.md)

[ゲスト共有を特定の組織に制限する](limit-guest-sharing-to-specific-organization.md)