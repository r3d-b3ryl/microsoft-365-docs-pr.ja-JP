---
title: 組織外のユーザーに条件付きアクセスを要求する
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
description: MFA や準拠デバイスなどの条件付きアクセス チェックに合格するよう組織外のユーザーに要求する方法について説明します。
ms.openlocfilehash: a9a48bd891810530fba4f78824f675d2b0f0556e
ms.sourcegitcommit: c33af120921d3c4fb5c362dac3e74f0ab3d1e58d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249615"
---
# <a name="require-conditional-access-for-people-outside-your-organization"></a>組織外のユーザーに条件付きアクセスを要求する

組織外のユーザーには、次のいずれかの条件付きアクセス オプションを要求できます。

- 多要素認証
- 準拠しているデバイス
- ハイブリッド Azure AD参加しているデバイス

Azure AD B2B 直接接続 (Teamsの共有チャネルなど) を使用する場合は、これらのオプションについて他の組織からの条件付きアクセス設定を信頼することを選択できます。 条件付きアクセス ポリシーは、共有チャネルと関連付けられているSharePoint サイトの [ファイル] タブへのアクセスにのみ使用されることに注意してください。

## <a name="planning-considerations-for-conditional-access"></a>条件付きアクセスの計画に関する考慮事項

多要素認証は、任意の外部アカウントで使用できます。 組織が他のAzure AD組織からの多要素認証を信頼していない場合は、組織内のリソースにアクセスするときに、それらの組織のユーザーが多要素認証を実行する必要があります。 サード パーティの電子メール アドレス (Microsoft によってホストされていない) を持つユーザーは、常に多要素認証を求められます。

[**デバイスに準拠をマークする必要があります**] オプションと[**ハイブリッド Azure AD参加済みデバイスを必要とする]** オプションでは、Azure ADで管理されているデバイスが必要です。 これらのオプションを有効にすることを選択した場合、組織外のユーザーは、組織または信頼できる組織によって管理されているデバイスを使用している必要があります。 管理対象デバイスを持たないユーザーは、次のようなブロックされます。

- サード パーティまたはコンシューマーの電子メール アドレスを持つユーザー
- デバイスを管理していないMicrosoft 365またはAzure AD組織のユーザー
- 組織が条件付きアクセス設定を信頼していないマネージド デバイスを必要とする、Microsoft 365またはAzure AD組織のユーザー。

準拠デバイスまたはハイブリッド Azure AD参加済みデバイスを必要とする場合は、多くの外部コラボレーション シナリオがブロックされるため、注意を払う必要があります。 すべてのパートナー組織がデバイスを管理し、組織が設定を信頼していることを確認します。

## <a name="set-up-conditional-access-requirements-for-people-outside-your-organization"></a>組織外のユーザーに条件付きアクセス要件を設定する

組織外のユーザーに条件付きアクセスを要求するには、次の操作を行います。

1. [他の組織から信頼する条件付きアクセス設定を選択します](#choose-conditional-access-settings-to-trust-from-other-organizations)。
1. [組織外のユーザーに条件付きアクセスを設定します](#set-up-conditional-access-for-people-outside-your-organization)。

## <a name="choose-conditional-access-settings-to-trust-from-other-organizations"></a>他の組織から信頼する条件付きアクセス設定を選択する

他のすべてのMicrosoft 365およびAzure AD組織からの条件付きアクセス設定を信頼するか、指定した組織からのみ信頼するかを選択できます。

> [!NOTE]
> クロス テナント アクセス設定の変更が有効になるまでに最大 2 時間かかる場合があります。

### <a name="trust-conditional-access-settings-from-all-azure-active-directory-organizations"></a>すべてのAzure Active Directory組織から条件付きアクセス設定を信頼する

すべての組織から条件付きアクセス設定を信頼する場合は、次の手順に従います。

すべてのAzure Active Directory組織から条件付きアクセス設定を信頼するには
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. [ **既定の設定** ] タブを選択します。
1. **[受信アクセス設定**] で、[**受信の既定値の編集]** を選択します。
1. [ **信頼設定** ] タブを選択します。
1. 条件付きアクセス ポリシーが他の組織から受け入れる設定を選択します。
1. **[保存] を** 選択し、[**既定の設定]** ブレードを閉じます。

### <a name="trust-conditional-access-settings-from-a-specific-organization"></a>特定の組織からの条件付きアクセス設定を信頼する

特定の組織から条件付きアクセス設定を信頼する場合は、次の手順に従います。

特定の組織から条件付きアクセス設定を信頼するには
1. 全体管理者またはセキュリティ管理者のアカウントを使用して、[Azure Active Directory](https://aad.portal.azure.com) にサインインします。
1. **[外部 ID]** を選択し、**[クロス テナント アクセス設定 (プレビュー)]** を選択します。
1. 条件付き **アクセス** 設定を信頼する組織の受信アクセス設定を選択します。
1. [ **信頼設定** ] タブを選択します。
1. [ **設定のカスタマイズ]** オプションを選択します。
1. 条件付きアクセス ポリシーが他の組織から受け入れる設定を選択します。
1. **[保存] を** 選択し、[**既定の設定]** ブレードを閉じます。

## <a name="set-up-conditional-access-for-people-outside-your-organization"></a>組織外のユーザーに条件付きアクセスを設定する

組織外のユーザーに条件付きアクセス ポリシーを設定すると、次の影響を受けます。

- ゲスト アカウントを使用しているユーザー (B2B コラボレーション ユーザー Azure AD)
- Teams共有チャネルの外部参加者 (Azure AD B2B 直接接続ユーザー)

> [!IMPORTANT]
> 組織外のすべてのユーザーが、組織または信頼できる **Microsoft 365またはAzure AD** 組織によって管理されているデバイスを使用している場合にのみ、デバイスを **準拠としてマーク** するか、[ハイブリッド Azure AD参加済みデバイスを要求する] を選択します。

組織外のユーザーに条件付きアクセスを設定するには
1. [Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。
1. **[条件付きアクセス|ポリシー]** ブレードで、**[新しいポリシー]** をクリックします。
1. **[名前]** フィールドに名前を入力します。
1. **[割り当て]** の下の **[ユーザーとグループ]** をクリックします。
1. **[ユーザーとグループ]** ブレードで、**[ユーザーとグループの選択]** を選択し、**[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。
1. **[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。
1. **[クラウド アプリまたは操作]** ブレードで、**[対象]** タブの **[すべてのクラウド アプリ]** を選択します。
1. **[アクセス制御]** で、**[許可]** をクリックします。
1. [ **付与** ] ブレードで、組織外のユーザーに必要なオプションを選択し、[ **選択**] をクリックします。
1. **[新規]** ブレードの **[ポリシーの有効化]** で、**[オン]** をクリックして、**[作成]** をクリックします。

## <a name="related-topics"></a>関連項目

[チュートリアル: B2B ゲストに多要素認証を適用する](/azure/active-directory/external-identities/b2b-tutorial-require-mfa)
