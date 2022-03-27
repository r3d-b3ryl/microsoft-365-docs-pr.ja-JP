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
description: ユーザーがゲスト アカウントを使用できる組織を指定する方法について学習します。
ms.openlocfilehash: 00db14560c491461435e41e30c106c2554d9ad61
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716036"
---
# <a name="limit-organizations-where-users-can-have-guest-accounts"></a>ユーザーがゲスト アカウントを持つ組織を制限する

既定では、他Microsoft 365組織Azure Active Directoryゲストとして組織に参加するユーザーを招待できます。 これには、Microsoft Team のチームへの招待、SharePointサイトへの招待、個々のファイルとフォルダーの共有が含まれます。

ユーザーが特定の組織のゲストとしてのみ参加する場合は、[B2B](/azure/active-directory/external-identities/what-is-b2b) コラボレーションのクロステナント アクセスAzure Active Directoryでこれらの組織を指定できます。

> [!NOTE]
> テナント間のアクセス設定の変更は、有効に 2 時間かかる場合があります。

## <a name="set-the-default-b2b-collaboration-settings-to-block-users-from-being-guests"></a>既定の B2B コラボレーション設定を設定して、ユーザーのゲストをブロックする

ゲストとしての参加は既定で有効になっているため、特定の組織へのゲスト参加を制限するには、既定で送信 B2B コラボレーションをブロックする必要があります。

既定で送信 B2B コラボレーションをブロックするには
1. グローバル管理者または[セキュリティAzure Active Directory](https://aad.portal.azure.com)アカウントを使用してサインインして、アカウントにサインインします。
1. [ **外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー) **] を選択します**。
1. [既定の **設定] タブを** 選択します。
1. [ **送信アクセス設定] で、[** 送信の **既定値の編集] を選択します**。
1. **[B2B コラボレーション] タブと [** ユーザーとグループ **] タブを選択** します。
1. [アクセス **の状態] で、[** アクセスの **ブロック] を選択します**。
1. [外部アクセス **] タブを選択** します。
1. [アクセス **の状態] で、[** アクセスの **ブロック] を選択します**。
1. **[保存]** を選択します。
1. [既定の **設定] ブレードを閉** じます。

## <a name="add-an-organization"></a>組織の追加

次に、ユーザーがゲストとして共同作業を許可する組織を、テナント間アクセス リストAzure AD追加します。

組織を追加するには
1. [[Azure Active Directory](https://aad.portal.azure.com)で、[**外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー)] **を選択します**。
1. [組織 **の設定] を選択します**。
1. [組織 **の追加] を選択します**。
1. [組織 **の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力します。
1. 検索結果で組織を選択し、[追加] を **選択します**。
1. 組織が [組織の設定] **リストに表示** されます。

この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

## <a name="configure-the-organizations-outbound-setting-to-allow-all-users"></a>組織の送信設定を構成して、すべてのユーザーを許可する

組織を追加したら、組織の送信設定を更新して、B2B コラボレーション ユーザーをゲストとして追加する必要があります。 ユーザーをゲストとして追加する組織ごとにこの操作を行います。

ユーザーが組織内の B2B コラボレーション ゲストを許可するには
1. [[Azure Active Directory](https://aad.portal.azure.com)で、[**外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー)] **を選択します**。
1. 変更する組織の送信アクセス リンクを選択します。
1. [ **B2B コラボレーション] タブで、[** 設定のカスタマイズ] **を選択します**。
1. [アクセス **の状態] で、[** アクセスを **許可する] を選択します**。
1. [ **ターゲット] で**、すべてのユーザーを許可するを選択します。
1. [保存 **] を** 選択し、[ **送信アクセス設定] ブレードを閉** じます。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B ダイレクト接続のテナント間アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[組織から招待できるユーザーを制限する](limit-invitations-from-specific-organization.md)

[ゲスト共有を特定の組織に制限する](limit-guest-sharing-to-specific-organization.md)