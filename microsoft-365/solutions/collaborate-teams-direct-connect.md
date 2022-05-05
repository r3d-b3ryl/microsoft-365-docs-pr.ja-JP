---
title: 共有チャネルで外部の参加者と共同作業する
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
recommendations: false
description: 組織外のユーザーとのコラボレーションのために、Microsoft Teams で共有チャネルを有効にする方法について説明します。
ms.openlocfilehash: 392b2326e3166b5f813f96edc2a21c360919cfa6
ms.sourcegitcommit: b3f5fe84a319741583954ef8ff2ec9ec6da69bcf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2022
ms.locfileid: "65217482"
---
# <a name="collaborate-with-external-participants-in-a-shared-channel"></a>共有チャネルで外部の参加者と共同作業する

ユーザーが[共有チャネル](/MicrosoftTeams/shared-channels)で組織外のユーザーと共同作業を行うことができるようにするには、共同作業を行う組織ごとに B2B 直接接続を構成する必要があります (または、[外部組織すべてとの共有チャネルを有効](/microsoft-365/solutions/allow-direct-connect-with-all-organizations)にできます)。

Teams で別の組織と共有チャネルを有効にする場合:

- 組織内のチーム所有者は、共有チャネルに参加するよう他の組織のユーザーを招待できます。
- 組織のカスタム (基幹業務) アプリを共有チャネルで利用できます。外部の参加者は、それらのアプリにアクセスできるようになります。
- 組織のアプリ リストを共有チャネルで利用できます。外部の参加者は、それらのアプリにアクセスできるようになります。

> [!NOTE]
> 共有チャネルはプレビュー中で、[Microsoft Teams パブリック プレビュー](/MicrosoftTeams/public-preview-doc-updates)が構成されている必要があります。 チャネルを他の組織と共有する場合は、それらの組織でも Teams パブリック プレビューが構成されている必要があります。

## <a name="enable-shared-channels-in-teams"></a>Teams で共有チャネルを有効にする

Teams で、共有チャネルは既定で有効になっています。 この手順に従って、設定を確認します。

共有チャネルを構成する方法
1. [Teams 管理センター](https://admin.teams.microsoft.com/)で **[Teams]** を展開し、**[Teams ポリシー]** を選択します。
1. 共有チャネルを有効にするポリシーを選択し、**[編集]** を選択します。
1. 有効にするオプションを選択します。
    - チーム所有者が共有チャネルを作成できるようにするには、**[共有チャネルを作成]** をオンにします。
    - チームの所有者が組織外のユーザーと共有チャネルを共有できるようにするには、**[外部ユーザーを共有チャネルに招待する]** をオンにします。
    - ユーザーを他の組織の共有チャネルに招待できるようにするには、**[外部共有チャネルに参加]** をオンにします。
1. **[適用]** を選択します。

外部チャネルの参加者が会議に参加するには、外部アクセスを有効にする必要があります。 これは、チャネルで外部参加者のプレゼンスを確認できるようにするためにも必要です。

外部アクセスを有効にするには
1. [Teams 管理センター](https://admin.teams.microsoft.com/) で、**［ユーザー］** を展開し、**［外部アクセス］** を選択します。
1. **Teams および外部組織の Skype for Business ユーザー** で、共同作業を行う組織がブロックされていないことを確認します。

## <a name="configure-cross-tenant-access-settings-in-azure-ad"></a>Azure AD のクロス テナント アクセス設定を構成する

Azure AD B2B 直接接続は既定で無効になっています。 共有チャネルで他の組織のユーザーとの共同作業を有効にするには、次の手順を実行する必要があります。

1. [組織を追加します](#add-an-organization)。
1. 組織の[受信設定を構成](#configure-inbound-settings)して、組織のユーザーが共有チャネルへの招待を受けることができるようにします。
1. 組織の[送信設定を構成](#configure-outbound-settings)して、ユーザーが他の組織の共有チャネルへの招待を受けることができるようにします。

この構成の一環として、**Office 365** アプリケーションが有効になります。これには、Teams と、SharePoint などの Teams 統合サービスが含まれます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

### <a name="add-an-organization"></a>組織を追加する

共有チャネルに参加させる各組織を追加します。

組織を追加する方法
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. **[組織設定]** を選択します。
1. **[組織の追加]** を選択します。
1. **[組織の追加]** ウィンドウで、組織の完全なドメイン名 (またはテナント ID) を入力し、Enter キーを押します。
1. **[追加]** を選択します。
1. 組織が組織リストに表示されます。この時点で、この組織のすべてのアクセス設定は既定の設定から継承されます。

### <a name="configure-inbound-settings"></a>受信設定を構成する

外部の参加者を招待する組織ごとに、この手順に従います。

組織の受信設定を構成する方法
1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. 変更する組織の受信アクセス リンクを選択します。
1. **[B2B 直接接続]** タブで、**[設定のカスタマイズ]** を選択します。
1. 外部 **[外部ユーザーとグループ]** タブで、**[アクセスを許可]** と **[すべての外部ユーザーとグループ]** を選択します。 (秘密保持契約書に署名したユーザーとグループなど、特定のユーザーとグループにアクセスを限定する場合、**［外部のユーザーとグループを選択 (Select external users and groups)]** を選ぶことができます)。
1. **[アプリケーション]** タブで、**[アクセスを許可]** と **[アプリケーションの選択]** を選択します。
1. **[アプリケーションの追加]** を選択します。
1. **Office 365** アプリケーションを選択して、**[選択]** を選択します。
1. **[保存]** を選択し、**[送信アクセス設定]** ブレードを閉じます。

### <a name="configure-outbound-settings"></a>送信設定を構成する

ユーザーを参加させる外部の共有チャネルの組織ごとに、この手順を実行します。

組織の送信設定を構成する方法
1. [[Azure Active Directory]](https://aad.portal.azure.com) で、**[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. 変更する組織の送信アクセス リンクを選択します。
1. **[B2B 直接接続]** タブで、**[設定のカスタマイズ]** を選択します。
1. **[外部ユーザーとグループ]** タブで、**[アクセスを許可]** を選択し、すべてのユーザーの **[適用先]** を設定します。
1. **[外部アプリケーション]** タブで、**[アクセスを許可]** と **[外部アプリケーションの選択]** を選択します。
1. **[アプリケーションの追加]** を選択します。
1. **Office 365** アプリケーションを選択して、**[選択]** を選択します。
1. **[保存]** を選択し、**[はい]** を選択して確認し、**[送信アクセス設定]** ブレードを閉じます。

## <a name="see-also"></a>関連項目

[B2B 直接接続の概要](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[B2B 直接接続のクロス テナント アクセス設定を構成する](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[組織が招待することのできるユーザーを制限する](limit-invitations-from-specific-organization.md)

[共有チャネルの制限](/MicrosoftTeams/shared-channels#shared-channel-limits)
