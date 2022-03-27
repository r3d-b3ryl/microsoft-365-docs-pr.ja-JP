---
title: ゲスト共有を特定の組織に制限する
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
description: ゲスト共有を特定の組織または組織Azure AD制限Microsoft 365説明します。
ms.openlocfilehash: 75cfe739e1cdde2e0bd959382b2444487ea726be
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716070"
---
# <a name="limit-guest-sharing-to-specific-organizations"></a>ゲスト共有を特定の組織に制限する

既定では、ユーザーは組織外のユーザーをゲストとして招待できます。 これには、Microsoft Team のチームへの招待、SharePointサイトへの招待、個々のファイルとフォルダーの共有が含まれます。

ユーザーが特定の組織からのゲストのみを招待する場合は、[B2B](/azure/active-directory/external-identities/what-is-b2b) コラボレーションのクロステナント アクセスAzure Active Directoryでこれらの組織を指定できます。

## <a name="configure-cross-tenant-access-settings"></a>テナント間アクセス設定の構成

ゲスト共有を制限する最初の手順は、既定でゲストの招待をブロックAzure ADテナント間アクセス設定の既定の設定を変更します。 次に、特定の組織に対してゲスト招待を許可できます。

> [!NOTE]
> テナント間のアクセス設定の変更は、有効に 2 時間かかる場合があります。

### <a name="set-the-default-b2b-collaboration-settings-to-block-inviting-guests"></a>招待ゲストをブロックする既定の B2B コラボレーション設定を設定する

ゲストの招待は既定で有効になっているため、特定の組織へのゲスト招待を制限するには、既定で受信 B2B コラボレーションをブロックする必要があります。

既定で受信 B2B コラボレーションをブロックするには
1. グローバル管理者または[セキュリティAzure Active Directory](https://aad.portal.azure.com)アカウントを使用してサインインして、アカウントにサインインします。
1. [ **外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー) **] を選択します**。
1. [既定の **設定] タブを** 選択します。
1. [ **受信アクセス設定] で、[** 受信 **の既定値の編集] を選択します**。
1. **[B2B コラボレーション] タブと [** ユーザーとグループ **] タブを選択** します。
1. [アクセス **の状態] で、[** アクセスの **ブロック] を選択します**。
1. [外部アクセス **] タブを選択** します。
1. [アクセス **の状態] で、[** アクセスの **ブロック] を選択します**。
1. **[保存]** を選択します。
1. [既定の **設定] ブレードを閉** じます。

### <a name="add-the-organization-where-you-want-to-allow-guest-invitations"></a>ゲストの招待を許可する組織を追加する

次に、ユーザーがテナント間アクセス リストにゲストを招待Azure AD組織を追加します。

組織を追加するには
1. [[Azure Active Directory](https://aad.portal.azure.com)で、[**外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー)] **を選択します**。
1. [組織 **の設定] を選択します**。
1. [組織 **の追加] を選択します**。
1. [組織 **の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力します。
1. 検索結果で組織を選択し、[追加] を **選択します**。
1. 組織が [組織の設定] **リストに表示** されます。

この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

### <a name="configure-inbound-settings-for-the-organization-to-allow-all-users"></a>組織の受信設定を構成して、すべてのユーザーを許可する

組織を追加したら、組織の受信設定を更新して、B2B コラボレーション ユーザーをゲストとして招待できる必要があります。 ユーザーがゲストを招待できる組織ごとにこの操作を行います。

1. [[Azure Active Directory](https://aad.portal.azure.com)で、[**外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー)] **を選択します**。
1. 変更する組織の受信アクセス リンクを選択します。
1. [ **B2B コラボレーション] タブで、[** 設定のカスタマイズ] **を選択します**。
1. [アクセス **の状態] で、[** アクセスを **許可する] を選択します**。
1. [ **ターゲット] で**、すべてのユーザーを許可するを選択します。
1. [保存 **] を** 選択し、[ **送信アクセス設定] ブレードを閉** じます。

## <a name="turn-off-one-time-passcode-authentication"></a>1 回のパスコード認証をオフにする

B2B のコラボレーションを特定の組織に限定した後でも、他の組織のユーザーとファイルやフォルダーを共有できます。ディレクトリ内のゲスト アカウントは与えされません。

他の組織との完全な共有を防ぐ場合は、パスコード機能を無効にする必要Azure AD。 これにより、組織外のユーザーが共有ファイルまたはフォルダーに認証用の 1 回のパスコードを送信できません。

メールのワンタイム パスコード機能を無効にするには
1. Azure AD の全体管理者として [Azure ポータル](https://portal.azure.com/) にサインインします。
1. ナビゲーション ウィンドウで、**[Azure Active Directory]** を選択します。
1. [ **外部 ID] [** > **すべての ID プロバイダー] を選択します**。
1. [**メールのワン** タイム パスコード] を選択し、[ゲストのメールワンタイム パスコード] で、[ゲストのメールワンタイムパスコードを無効にする] を選択します (機能が以前に有効、無効、またはプレビュー中にオプトインされた場合はいいえ)。
1. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B ダイレクト接続のテナント間アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[組織から招待できるユーザーを制限する](limit-invitations-from-specific-organization.md)

[ユーザーがゲスト アカウントを持つ組織を制限する](limit-organizations-where-users-have-guest-accounts.md)