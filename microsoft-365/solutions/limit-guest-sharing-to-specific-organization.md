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
description: ゲスト共有を特定のAzure ADまたはMicrosoft 365組織に制限する方法について説明します。
ms.openlocfilehash: 75cfe739e1cdde2e0bd959382b2444487ea726be
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716070"
---
# <a name="limit-guest-sharing-to-specific-organizations"></a>ゲスト共有を特定の組織に制限する

既定では、ユーザーは組織外のユーザーをゲストとして招待できます。 これには、Microsoft Team のチームへの招待、サイトのSharePoint、個々のファイルとフォルダーの共有が含まれます。

ユーザーが特定の組織からのゲストのみを招待する場合は、[B2B コラボレーション](/azure/active-directory/external-identities/what-is-b2b)のAzure Active Directoryテナント間アクセス設定でこれらの組織を指定できます。

## <a name="configure-cross-tenant-access-settings"></a>クロステナント アクセス設定を構成する

ゲスト共有を制限する最初の手順は、既定でゲストの招待をブロックするように、Azure ADテナント間アクセス設定の既定の設定を変更することです。 その後、特定の組織に対するゲスト招待を許可できます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

### <a name="set-the-default-b2b-collaboration-settings-to-block-inviting-guests"></a>招待ゲストをブロックするように既定の B2B コラボレーション設定を設定する

ゲストの招待は既定で有効になっているため、特定の組織へのゲスト招待を制限するには、既定で受信 B2B コラボレーションをブロックする必要があります。

既定で受信 B2B コラボレーションをブロックするには
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. [ **既定の設定** ] タブを選択します。
1. **[受信アクセス設定**] で、[**受信の既定値の編集]** を選択します。
1. **[B2B コラボレーション**] タブと [**ユーザーとグループ**] タブを選択します。
1. **[アクセスの状態**] で、[**アクセスのブロック**] を選択します。
1. [ **外部アクセス** ] タブを選択します。
1. **[アクセスの状態**] で、[**アクセスのブロック**] を選択します。
1. **[保存]** を選択します。
1. **[既定の設定]** ブレードを閉じます。

### <a name="add-the-organization-where-you-want-to-allow-guest-invitations"></a>ゲストの招待を許可する組織を追加する

次に、ユーザーがAzure ADテナント間アクセス リストにゲストを招待できるようにする組織を追加します。

組織を追加する方法
1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. **[組織設定]** を選択します。
1. **[組織の追加]** を選択します。
1. **[組織の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力します。
1. 検索結果から組織を選択して、**[追加]** を選択します。
1. 組織が **[組織設定]** リストに表示されます。

この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

### <a name="configure-inbound-settings-for-the-organization-to-allow-all-users"></a>すべてのユーザーを許可するように組織の受信設定を構成する

組織を追加したら、B2B コラボレーション ユーザーをゲストとして招待できるように、組織の受信設定を更新する必要があります。 これは、ユーザーがゲストを招待できるようにする組織ごとに行います。

1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. 変更する組織の受信アクセス リンクを選択します。
1. **B2B コラボレーション** タブで、[設定の **カスタマイズ**] を選択します。
1. **[アクセスの状態**] で、[**アクセスを許可する**] を選択します。
1. [ **ターゲット]** で、すべてのユーザーを許可することを選択します。
1. **[保存]** を選択し、**[送信アクセス設定]** ブレードを閉じます。

## <a name="turn-off-one-time-passcode-authentication"></a>ワンタイム パスコード認証を無効にする

B2B コラボレーションを特定の組織に制限した後も、他の組織のユーザーとファイルやフォルダーを共有できます。ディレクトリ内のゲスト アカウントは付与されません。

他の組織との完全な共有を禁止する場合は、Azure ADでワンタイム パスコード機能を無効にする必要があります。 これにより、組織外のユーザーが、共有ファイルまたはフォルダーに認証用のワンタイム パスコードを送信できなくなります。

電子メールワンタイム パスコード機能を無効にするには
1. Azure AD の全体管理者として [Azure ポータル](https://portal.azure.com/) にサインインします。
1. ナビゲーション ウィンドウで、**[Azure Active Directory]** を選択します。
1. **[External IdentitysAll** > **] ID プロバイダーを選択します**。
1. [ **電子メールのワンタイム パスコード**] を選択し、[ **ゲストのワンタイム パスコードを電子メールで送信** する] で [ **ゲストの電子メール ワンタイム パスコードを無効にする** ] を選択します (プレビュー中に機能が以前に有効、無効、またはオプトインされた場合は **いいえ** )。
1. **[保存]** を選択します。

## <a name="related-topics"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B 直接接続のクロス テナント アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[組織が招待することのできるユーザーを制限する](limit-invitations-from-specific-organization.md)

[ユーザーがゲスト アカウントを持つ組織を制限する](limit-organizations-where-users-have-guest-accounts.md)