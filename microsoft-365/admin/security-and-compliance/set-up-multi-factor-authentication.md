---
title: ユーザーの多要素認証を設定する
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
- adminvideo
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 組織向けに多要素認証を設定する方法について説明します。
monikerRange: o365-worldwide
ms.openlocfilehash: 32e429f2d24c8754603c3ab32b060a9b7656df4e
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085511"
---
# <a name="set-up-multifactor-authentication-for-microsoft-365"></a>Microsoft 365 Business Premium の多要素認証を設定する

YouTube で [Microsoft 365 Small Business ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

多要素認証とは、Microsoft 365 にサインインするために、あなたとあなたの従業員が複数の方法を提供する必要があることを意味します。これは、ビジネスを保護する最も簡単な方法の 1 つです。 [多要素認証 (MFA) および Microsoft 365 のサポート](multi-factor-authentication-microsoft-365.md)を理解して、多要素認証を組織に設定し、展開します。 

> [!IMPORTANT]
> 2019 年 10 月 21 日以降にサブスクリプションまたは試用版を購入した場合、サインインすると MFA を要求するメッセージが表示され、[セキュリティの既定](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)の設定は、サブスクリプションに対して自動的に有効になります。

> [!TIP]
> このトピックの手順に関するヘルプが必要な場合は、[Microsoft Small Business スペシャリストとの協働](https://go.microsoft.com/fwlink/?linkid=2186871)を検討してください。 Business Assist を使用すると、オンボーディングから日常使用まで、ビジネスを成長させながら従業員とともに一日中いつでも中小企業の専門家にアクセスできます。

## <a name="watch-turn-on-multifactor-authentication"></a>ウォッチ: 多要素認証を有効にする

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2197909) で、このビデオや他のビデオを確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2MuO3?autoplay=false]

1. <a href="https://admin.microsoft.com/ " target="_blank">https://admin.microsoft.com</a> の Microsoft 365 管理センターに移動します。
1. **[すべて表示]** を選択してから、**Azure Active Directory 管理センター** を選択します。
1. **[Azure Active Directory]**、**[プロパティ]**、**[セキュリティの既定値の管理]** の順に選択します。
1. **[セキュリティの既定値群の有効化]** で **[はい]**、**[保存]** の順に選択します。

## <a name="before-you-begin"></a>はじめに

- MFA を管理するには、グローバル管理者である必要があります。 詳細については、「[管理者の役割について](../add-users/about-admin-roles.md)」を参照してください。
- 従来のユーザーごとの MFA をオンにしている場合は、[従来のユーザーごとの MFA をオフにします](#turn-off-legacy-per-user-mfa)。
- Windows デバイスで Office 2013 クライアントを使用している場合は、[Office 2013 クライアントの最新のライセンス認証をオンにします](./enable-modern-authentication.md)。
- 高度: Active Directory フェデレーション サービス (AD FS) を使用しているサードパーティのディレクトリ サービスがある場合は、Azure MFA Server をセットアップします。 詳細については、「[Azure AD Multifactor Authentication およびサード パーティ製 VPN ソリューションでの高度なシナリオ](/azure/active-directory/authentication/howto-mfaserver-nps-vpn)」を参照してください。

### <a name="turn-off-legacy-per-user-mfa"></a>従来のユーザーごとの MFA をオフにする

以前にユーザーごとの MFA をオンにしている場合は、セキュリティの既定値が有効になる前にオフにする必要があります。

1. Microsoft 365 管理センターで、左側のナビゲーションの **[ユーザー]** \> **[アクティブ ユーザー]** の順に選択します。
1. **[アクティブ ユーザー]** ページで、**[多要素認証]** を選択します。
1. 多要素認証ページで、各ユーザーを選択し、その多要素認証ステータスを **[無効]** に設定します。

## <a name="turn-security-defaults-on-or-off"></a>セキュリティの既定値をオンまたはオフにする

ほとんどの組織では、セキュリティの既定値により、適切なレベルのサインイン セキュリティが提供されます。 詳細については、[「セキュリティの既定値とは?」](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) を参照してください。

サブスクリプションが新しい場合は、セキュリティの既定値が自動的にオンになります。

Azure ポータル内の Azure Active Directory (Azure AD) の **プロパティ** ウィンドウで、セキュリティの既定値を有効または無効にします。

1. グローバル管理者の資格情報を使用して、[MIcrosoft 365 管理センター](https://admin.microsoft.com) にサインインします。
2. 左側のナビゲーションで、**[すべて表示]** を選択し、**[管理センター]** の **[Azure Active Directory]** を選択します。
3. **Azure Active Directory 管理センター** で、**[Azure Active Directory]** \> **[プロパティ]** の順に選択します。
4. ページの下部で、**[セキュリティの既定値の管理]** を選択します。
5. セキュリティの規定値を有効にするには **[はい]** を選び、セキュリティの規定値を無効にするには **[いいえ]** を選んで、**[保存]** を選択します。

[条件付きアクセスのベースライン ポリシー](/azure/active-directory/conditional-access/concept-baseline-protection) を使用している場合は、セキュリティの既定値の使用に移行する前に、オフにするように求めるメッセージが表示されます。

1. [条件付きアクセス ポリシー ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) へ移動します。
2. 各ベースライン ポリシーで [**オン**] を選択し、 [**ポリシーを有効にする**] を [**オフ**] に設定します。
3. [[Azure Active Directory] のプロパティ ページ](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) にアクセスします。
4. ページの下部で、[**セキュリティの既定値の管理**] を選択します。
5. セキュリティの規定値を有効にするには [**はい**] を選び、セキュリティの規定値を無効にするには [**いいえ**] を選んで [**保存**] を選択します。

## <a name="use-conditional-access-policies"></a>条件付きアクセス ポリシーを使用する

より細かいサインイン セキュリティを必要としている組織の場合、条件付きアクセス ポリシーを使用すると、より詳細に制御できます。 条件付きアクセスを使用すると、ユーザーがアプリケーションまたはサービスへのアクセスを許可される前に、サインイン イベントに反応し、追加のアクションを要求するポリシーを作成し定義できます。

> [!IMPORTANT]
> 条件付きアクセス ポリシーを有効にする前に、ユーザーごとの MFA とセキュリティの既定値をオフにします。

条件付きアクセスは、Azure AD Premium P1 を購入したお客様、またはこれを含むライセンス (Microsoft 365 Business Premium、Microsoft 365 E3 など) で利用できます。詳細については、「[条件付きアクセス ポリシーを作成する](/azure/active-directory/authentication/tutorial-enable-azure-mfa)」を参照してください。

リスクベースの条件付きアクセスは、Azure AD Premium P2 ライセンス、またはこれを含むライセンス (Microsoft 365 E5 など) を通じて利用できます。詳細については、「 [リスクベースの条件付きアクセス](/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)」を参照してください。

Azure AD P1 および P2 の詳細については、「[Azure Active Directory の料金](https://azure.microsoft.com/pricing/details/active-directory/)」をご覧ください。

### <a name="turn-on-modern-authentication-for-your-organization"></a>組織の先進認証をオンにする

ほとんどのサブスクリプションでは、先進認証が自動的にオンになりますが、2017 年 8 月より前にサブスクリプションを購入した場合、多要素認証などの機能を Outlook などの Windows クライアントで機能させるには、先進認証をオンにする必要があります。

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理センター</a> で、左側のナビゲーションの **[設定]** \> **[組織の設定]** の順に選択します。
2. **[サービス]** タブで、**[先進認証]** を選択し、**[先進認証]** ウィンドウで、**[先進認証を有効にする]** が選択されていることを確認します。**[変更を保存]** を選択します。

## <a name="next-steps"></a>次の手順

- [追加の検証手法を登録する方法](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [機能: 多要素認証](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [登録後のサインインの方法](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [追加の検証手法を変更する方法](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)

## <a name="related-content"></a>関連コンテンツ

[多要素認証を設定する](set-up-multi-factor-authentication.md) (ビデオ)\

[スマートフォンの多要素認証を有効にする](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14) (記事)\

[セキュリティの既定値と多要素認証](/microsoft-365/business-premium/m365bp-conditional-access) (記事)