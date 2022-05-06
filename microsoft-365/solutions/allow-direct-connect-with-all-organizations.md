---
title: すべての外部組織で共有チャネルを有効にする
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
description: 他のすべてのMicrosoft 365およびAzure Active Directory組織と共有チャネルを有効にする方法について説明します。
ms.openlocfilehash: 601bfaa825afdaf9ec5addb4b7c7e21804b07cb7
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716041"
---
# <a name="enable-shared-channels-with-all-external-organizations"></a>すべての外部組織で共有チャネルを有効にする

Teamsでは共有チャネルを外部で共有することが既定で有効になっていますが、[B2B 直接接続](/azure/active-directory/external-identities/b2b-direct-connect-overview)のテナント間アクセス設定Azure Active Directory外部でチャネルを共有するように構成する必要もあります。 既定では、これらの設定はすべての組織をブロックするように設定されています。

B2B 直接接続の既定の設定を変更して、すべての組織を許可できます。 これにより、ユーザーは、共同作業する組織ごとに個別の構成を作成しなくても、共有チャネルで共同作業できます。 (共同作業を行う組織でも、B2B 直接接続設定を構成する必要があることに注意してください)。

組織に他の組織とのコラボレーションを制限する要件がない場合は、すべての組織を既定で有効にすると、各組織を個別に管理する時間と複雑さが節約できます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

## <a name="allow-users-to-invite-people-in-other-organizations-to-participate-in-shared-channels"></a>ユーザーが他の組織のユーザーを招待して共有チャネルに参加できるようにする

既定では、ユーザーが他の組織のユーザーを招待して共有リソース (Teamsの共有チャネルなど) を使用できるようにすることができます。

ユーザーが B2B 直接接続参加者を既定で招待できるようにするには
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. [ **既定の設定]** タブの [ **受信アクセス設定**] で、[ **受信の既定値の編集]** を選択します。
1. **B2B 直接接続** タブを選択します。
1. [ **ユーザーとグループ** ] タブの [ **アクセスの状態**] で、[ **アクセスを許可** する] を選択します。
1. [ **外部アプリケーション** ] タブの [ **アクセスの状態**] で、[ **アクセスを許可する**] を選択します。
1. **[保存]** を選択します。
1. [ **信頼設定** ] タブを選択します。
1. 多要素認証、準拠デバイス、またはハイブリッド Azure AD参加しているデバイスを他の組織から信頼するかどうかを選択します。
1. **[保存]** を選択します。
1. **[既定の設定]** ブレードを閉じます。

## <a name="allow-users-to-participate-in-shared-channels-in-other-organizations"></a>ユーザーが他の組織の共有チャネルに参加できるようにする

既定では、ユーザーが外部組織によってホストされているリソース (Teamsの共有チャネルなど) へのアクセスを許可できます。

既定でユーザーが他の組織からリソースにアクセスできるようにするには
1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. [ **既定の設定** ] タブの [ **送信アクセス設定**] で、[ **送信の既定値の編集]** を選択します。
1. **B2B 直接接続** タブを選択します。
1. [ **ユーザーとグループ** ] タブの [ **アクセスの状態**] で、[ **アクセスを許可** する] を選択します。
1. [ **外部アプリケーション** ] タブの [ **アクセスの状態**] で、[ **アクセスを許可する**] を選択します。
1. **[保存]** を選択します。
1. **[既定の設定]** ブレードを閉じます。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B 直接接続のクロス テナント アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

