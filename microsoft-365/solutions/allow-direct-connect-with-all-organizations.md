---
title: すべての外部組織との共有チャネルを有効にする
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
description: 他のすべての組織や組織と共有チャネルを有効にするMicrosoft 365をAzure Active Directoryします。
ms.openlocfilehash: 601bfaa825afdaf9ec5addb4b7c7e21804b07cb7
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716041"
---
# <a name="enable-shared-channels-with-all-external-organizations"></a>すべての外部組織との共有チャネルを有効にする

共有チャネルを外部で共有する場合は、Teams で既定で有効になっていますが、Azure Active Directory の [B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview) ダイレクト接続のテナント間アクセス設定も、チャネルを外部で共有するように構成する必要があります。 既定では、これらの設定は、すべての組織をブロックする設定になっています。

B2B ダイレクト接続の既定の設定を変更して、すべての組織を許可できます。 これにより、ユーザーは、共同作業する組織ごとに個別の構成を作成する必要がなくても、共有チャネルで共同作業できます。 (共同作業を行う組織では、B2B 直接接続の設定も構成する必要があります。

組織に他の組織とのコラボレーションを制限する要件が存在しない場合、既定ですべての組織を有効にすると、各組織を個別に管理する時間と複雑さを節約できます。

> [!NOTE]
> テナント間のアクセス設定の変更は、有効に 2 時間かかる場合があります。

## <a name="allow-users-to-invite-people-in-other-organizations-to-participate-in-shared-channels"></a>ユーザーが他の組織のユーザーに共有チャネルへの参加を許可する

既定では、ユーザーが他の組織のユーザーに共有リソース (共有チャネルなど) を招待Teamsできます。

ユーザーが既定で B2B ダイレクト接続参加者を招待するには
1. グローバル管理者または[セキュリティAzure Active Directory](https://aad.portal.azure.com)アカウントを使用してサインインして、アカウントにサインインします。
1. [ **外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー) **] を選択します**。
1. [既定の **設定] タブ** の [ **受信アクセス設定] で、[** 受信の既定値 **の編集] を選択します**。
1. **[B2B 直接接続] タブを選択** します。
1. [ユーザーと **グループ] タブの** [アクセスの状態] **で、[** アクセスを許可する] **を選択します**。
1. [外部アプリケーション **] タブの** [アクセスの状態] **で、[** アクセスを許可する] **を選択します**。
1. **[保存]** を選択します。
1. [信頼の **設定] タブを** 選択します。
1. 多要素認証、準拠デバイス、またはハイブリッド デバイスを信頼して、他のAzure ADデバイスを信頼する場合に選択します。
1. **[保存]** を選択します。
1. [既定の **設定] ブレードを閉** じます。

## <a name="allow-users-to-participate-in-shared-channels-in-other-organizations"></a>他の組織の共有チャネルへのユーザーの参加を許可する

既定では、ユーザーが外部組織によってホストされているリソース (Teamsの共有チャネルなど) にアクセスできます。

ユーザーが既定で他の組織からリソースにアクセスするには
1. [[Azure Active Directory](https://aad.portal.azure.com)で、[**外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー)] **を選択します**。
1. [既定の **設定] タブ** の [送信 **アクセス設定] で、[** 送信の既定値 **の編集] を選択します**。
1. **[B2B 直接接続] タブを選択** します。
1. [ユーザーと **グループ] タブの** [アクセスの状態] **で、[** アクセスを許可する] **を選択します**。
1. [外部アプリケーション **] タブの** [アクセスの状態] **で、[** アクセスを許可する] **を選択します**。
1. **[保存]** を選択します。
1. [既定の **設定] ブレードを閉** じます。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B ダイレクト接続のテナント間アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

