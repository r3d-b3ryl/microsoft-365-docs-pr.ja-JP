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
description: 組織外のユーザーに MFA や準拠デバイスなどの条件付きアクセス チェックに合格する必要がある方法について説明します。
ms.openlocfilehash: 181ee77e6b8a8d491294c9a5d3f8ec9202c9f9c1
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716033"
---
# <a name="require-conditional-access-for-people-outside-your-organization"></a>組織外のユーザーに条件付きアクセスを要求する

組織外のユーザーに対して、次の条件付きアクセス オプションを要求できます。

- 多要素認証
- 準拠デバイス
- ハイブリッド Azure AD参加しているデバイス

Azure AD B2B ダイレクト接続 (Teams の共有チャネルなど) を使用する場合は、これらのオプションに対して他の組織からの条件付きアクセス設定を信頼できます。

## <a name="planning-considerations-for-conditional-access"></a>条件付きアクセスの計画に関する考慮事項

多要素認証は、任意の外部アカウントで使用できます。 組織が他の Azure AD 組織からの多要素認証を信頼しない場合は、組織内のリソースにアクセスするときに、それらの組織のユーザーが多要素認証を実行する必要があります。 サード パーティの電子メール アドレス (Microsoft がホストしていない) を持つユーザーには、多要素認証を求めるメッセージが常に表示されます。

[デバイスを **準拠としてマーク** する必要がある] および [ハイブリッド Azure AD **する**] オプションには、デバイスで管理されているデバイスがAzure AD。 これらのオプションを有効にした場合、組織外のユーザーは、組織または信頼できる組織によって管理されているデバイスを使用している必要があります。 管理対象デバイスのないユーザーは、次の情報を含めてブロックされます。

- 第三者または消費者の電子メール アドレスを持つユーザー
- デバイスをMicrosoft 365しないAzure AD組織のユーザー
- 組織が条件付Microsoft 365を信頼Azure AD管理対象デバイスを必要とする組織のユーザーまたは組織のユーザー。

多くの外部コラボレーション シナリオがブロックされる可能性Azure ADデバイスに準拠しているデバイスまたはハイブリッド デバイスを必要とする場合は注意が必要です。 すべてのパートナー組織がデバイスを管理し、組織が設定を信頼している必要があります。

## <a name="set-up-conditional-access-requirements-for-people-outside-your-organization"></a>組織外のユーザーに条件付きアクセス要件を設定する

組織外のユーザーに条件付きアクセスを要求するには、次の操作を行います。

1. [他の組織から信頼する条件付きアクセス設定を選択します](#choose-conditional-access-settings-to-trust-from-other-organizations)。
1. [組織外のユーザーに条件付きアクセスを設定します](#set-up-conditional-access-for-people-outside-your-organization)。

## <a name="choose-conditional-access-settings-to-trust-from-other-organizations"></a>他の組織から信頼する条件付きアクセス設定を選択する

条件付きアクセス設定は、他のすべての組織および組織Microsoft 365信頼Azure AD、指定した組織からのみ信頼できます。

> [!NOTE]
> テナント間のアクセス設定の変更は、有効に 2 時間かかる場合があります。

### <a name="trust-conditional-access-settings-from-all-azure-active-directory-organizations"></a>すべての組織からの条件付きアクセスAzure Active Directory信頼する

すべての組織からの条件付きアクセス設定を信頼する場合は、次の手順に従います。

すべての組織から条件付きアクセス設定Azure Active Directoryするには
1. グローバル管理者または[セキュリティAzure Active Directory](https://aad.portal.azure.com)アカウントを使用してサインインして、アカウントにサインインします。
1. [ **外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー) **] を選択します**。
1. [既定の **設定] タブを** 選択します。
1. [ **受信アクセス設定] で、[** 受信 **の既定値の編集] を選択します**。
1. [信頼の **設定] タブを** 選択します。
1. 条件付きアクセス ポリシーで他の組織から受け入れる設定を選択します。
1. [保存 **] を** 選択し、[既定の **設定] ブレードを閉** じます。

### <a name="trust-conditional-access-settings-from-a-specific-organization"></a>特定の組織からの条件付きアクセス設定を信頼する

特定の組織からの条件付きアクセス設定を信頼する場合は、次の手順に従います。

特定の組織からの条件付きアクセス設定を信頼するには
1. グローバル管理者または[セキュリティAzure Active Directory](https://aad.portal.azure.com)アカウントを使用してサインインして、アカウントにサインインします。
1. [ **外部 ID] を選択** し、[テナント間アクセス設定 (プレビュー) **] を選択します**。
1. 条件付き **アクセス設定を信頼** する組織の受信アクセス設定を選択します。
1. [信頼の **設定] タブを** 選択します。
1. [設定の **カスタマイズ] オプションを** 選択します。
1. 条件付きアクセス ポリシーで他の組織から受け入れる設定を選択します。
1. [保存 **] を** 選択し、[既定の **設定] ブレードを閉** じます。

## <a name="set-up-conditional-access-for-people-outside-your-organization"></a>組織外のユーザーに条件付きアクセスを設定する

組織外のユーザーに対して条件付きアクセス ポリシーを設定すると、次の影響を受ける。

- ゲスト アカウントを使用しているユーザー (Azure AD B2B コラボレーション ユーザー)
- 共有チャネルTeams外部参加者 (Azure AD B2B ダイレクト接続ユーザー)

> [!IMPORTANT]
> 組織 **外の全員** が、組織または信頼できる **Microsoft 365** または Azure AD 組織によって管理されているデバイスを使用している場合にのみ、[準拠するデバイスを必須とする] または [ハイブリッド Azure AD 参加デバイスを要求する] を選択します。

組織外のユーザーに条件付きアクセスを設定するには
1. [Azure条件付きアクセスポリシー](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade)に移動する。
1. **[条件付きアクセス|ポリシー]** ブレードで、**[新しいポリシー]** をクリックします。
1. **[名前]** フィールドに名前を入力します。
1. **[割り当て]** の下の **[ユーザーとグループ]** をクリックします。
1. **[ユーザーとグループ]** ブレードで、**[ユーザーとグループの選択]** を選択し、**[すべてのゲストと外部ユーザー]** チェック ボックスをオンにします。
1. **[割り当て]** の下の **[クラウド アプリまたはアクション]** をクリックします。
1. **[クラウド アプリまたは操作]** ブレードで、**[対象]** タブの **[すべてのクラウド アプリ]** を選択します。
1. **[アクセス制御]** で、**[許可]** をクリックします。
1. [許可 **] ブレード** で、組織外のユーザーに必要なオプションを選択し、[選択] をクリック **します**。
1. **[新規]** ブレードの **[ポリシーの有効化]** で、**[オン]** をクリックして、**[作成]** をクリックします。

## <a name="related-topics"></a>関連項目

[チュートリアル: B2B ゲストに多要素認証を適用する](/azure/active-directory/external-identities/b2b-tutorial-require-mfa)
